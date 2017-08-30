---
title: Cheatsheets / Bash
tags: [cheatsheet, ssh, bash]
keywords: cheatsheet, ssh, bash
sidebar: wiki_sidebar
permalink: cheatsheet_bash.html
toc: false
---

## General

<div class="panel-group">
<!--  panel -->
{% include panel.html
title="Run the same command multiple times with different parameters"
content="
`for i in a b c; do command $i; done`

You can use different kind of lists to iterate:

* `1 2 3 4 5`
* `$(Linux-Or-Unix-Command-Here)`
* `{1..5}`  

<sub>*Reference: [nixCraft - Bash For Loop Examples](https://www.cyberciti.biz/faq/bash-for-loop/)*</sub>
" %}
<!-- end -->
<!--  panel -->
{% include panel.html
title="Image manipulation"
content="
**join multiple images into one single pdf** <sup>[needs imagemagick]</sup>  
`convert 1.png 2.png out.pdf`


**join pdfs into a single file with `pdftk`**  
`pdftk file1.pdf file2.pdf file3.pdf cat output newfile.pdf`


**change resolution/size of a pdf**  
`gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/printer -dNOPAUSE -dQUIET -dBATCH -sOutputFile=output.pdf input.pdf`

Parameters:  
**dPDFSETTINGS=**/value , where values is the quality of conversion:  

* screen (screen-view-only quality, 72 dpi images)
* ebook (low quality, 150 dpi images)
* printer (high quality, 300 dpi images)
* prepress (high quality, color preserving, 300 dpi imgs)
* default (almost identical to /screen)

 <sup>Read the [docs](http://milan.kupcevic.net/ghostscript-ps-pdf/) for more info about available parameters.</sup>


**scale a PDF with `pdfjam`**  
`pdfjam --a4paper --noautoscale true --scale .71`  


**`sips` -- scriptable image processing system** <sup>[Only in MacOS]</sup>  
*Scale an image (preserve ratio) to a specific size*  
`sips -Z 128 image.png --out output.png`

*Convert to another format*  
`sips -s format png icon.icns --out icon.png`  
`sips -s format icns icon.png --out icon.icns`  


**convert from PPT to PDF using Libreoffice**  
`libreoffice --headless --invisible --convert-to pdf *.ppt`


**small script to join images (inside the same folder and named with a pattern) into a single pdf**  

```bash
read -p \"Find: \" find  
read -p \"Output: \" output
find . -name \"$find*\" | sort -n | sed 's/\ /\\ /g' | tr '\n' ' ' | sed 's/$/\ '$output'.pdf/' | xargs convert -compress jpeg

```

" %}
<!-- end -->
{% include panel.html
title="Diff with colors"
content="
if you want to `diff` two files and get colors like you get when using `git diff` you can use this:  
`git diff --no-index file1 file2`
" %}
<!-- end -->
</div>

## SSH

<div class="panel-group">
<!--  panel -->
{% include panel.html
title="Execute a multi-line script via `ssh`"
content="
```bash
cat << 'EOF' | ssh user@host
command-1
command-2
command-3
EOF
```
" %}
<!-- end -->
</div>
