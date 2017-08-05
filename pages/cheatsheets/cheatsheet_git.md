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
# stages the desired file
git add new-file
# changes the last commit's message and includes staged files in that commit
git commit --amend
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
<!--  panel -->
{% include panel.html
title="View history of changes in a specific directory with diffs"
content="
`git log -p DIR`
" %}
<!-- end -->
</div>
