---
title: Fonts
tags: [fonts]
keywords: fonts, font
sidebar: wiki_sidebar
permalink: fonts.html
summary: A list of cool fonts I found.
---

## Cool fonts

* {% include font.html
href="https://fonts.googleapis.com/css?family=Francois+One"
link="https://fonts.google.com/specimen/Francois+One"
family="Francois One"
name="Francois"
%}

## Add fonts to linux
Add fonts to linux (and make the avaliable when using `xfontsel`):   
- Exec these commands (where local is the folder where the fonts files are):

```
cd /usr/share/fonts/local/
mkfontscale
mkfontdir
```
- Update font cache and then: `xset +fp /usr/share/fonts/local`
- Use `xlsfonts` to view all fonts
- Also you can use `fc-list` and serach fonts with `grep`: `fc-list | grep -i "font name"`
