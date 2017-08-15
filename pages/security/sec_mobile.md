---
title: Security / Mobile
tags: [sec, mobile]
keywords: security, mobile
sidebar: wiki_sidebar
permalink: sec_mobile.html
---

## APKs

### How to reverse engineering an APK, edit the code and recompile the APK?

1. Decompile the apk:  
   `apktool d application.apk`  
2. Use [**MobSF**](https://github.com/MobSF/Mobile-Security-Framework-MobSF) or [**jadx-gui**](https://github.com/skylot/jadx) to analyze the source code.
3. Edit the desired part of the smali code extracted in step 1.
4. Rebuild the modified apk:  
   `apktool b -f -d application`  
5. Move the apk:  
   `mv application/dist/application.apk application-edited.apk`  
6. Generate a key (you will prompted to choose a password, remember it):  
   `keytool -genkey -v -keystore my-release-key.keystore -alias alias_name -keyalg RSA -keysize 2048 -validity 10000`  
7. Sign the apk:  
   `jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore my-release-key.keystore application-edited.apk alias_name`  
8. Verify the apk:  
   `jarsigner -verify -verbose -certs application-edited.apk`  
9. Zipalign the apk for optimal loading:  
   `zipalign -v 4 application-edited.apk application-edited-aligned.apk`  

<sup>References: [Decompile and recompile android APK](https://blog.bramp.net/post/2015/08/01/decompile-and-recompile-android-apk/), [apktool documentation](https://ibotpeaches.github.io/Apktool/documentation/) and [BEGINNER'S GUIDE TO SMALI CODING](https://forum.xda-developers.com/showthread.php?t=2193735)</sup>
