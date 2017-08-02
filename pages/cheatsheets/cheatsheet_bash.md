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

**sips -- scriptable image processing system** <sup>[Only in MacOS]</sup>  
*Scale an image (preserve ratio) to a specific size*  
`sips -Z 128 image.png --out output.png`

*Convert to another format*  
`sips -s format png icon.icns --out icon.png`  
`sips -s format icns icon.png --out icon.icns`

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
