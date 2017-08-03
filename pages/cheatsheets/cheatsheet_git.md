---
title: Cheatsheets / GIT
tags: [cheatsheet, git]
keywords: cheatsheet, git
last_updated: Aug 1, 2017
sidebar: wiki_sidebar
permalink: cheatsheet_git.html
toc: false
---

<div class="panel-group">
<!--  panel -->
{% include panel.html
title="How to add a file to the last commit? / How to edit last commit's message?"
content="
```bash
git add new-file # stages the desired file
git commit --amend # changes the last commit's message and includes staged files in that commit
```
" %}
<!-- end -->
<!--  panel -->
{% include panel.html
title="Change remote URL"
content="
```bash
# view existing remote URL
git remote -v
# change existing remote URL
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git

```
<sub>*Reference: [Github](https://help.github.com/articles/changing-a-remote-s-url/)*</sub>
" %}
<!-- end -->
</div>
