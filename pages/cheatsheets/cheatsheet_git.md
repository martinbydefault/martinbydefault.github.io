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
title="How to update deleted remote branches?"
content="
`git remote prune origin`
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
title="Ignore local changes to tracked files (we have that with local modifications to config files)"
content="
`git update-index --skip-worktree <file>`
(This only works if you don't pull again from master)

<sub>*Reference: [StackOverflow](https://stackoverflow.com/a/13631525)*</sub>
" %}
<!-- end -->
<!--  panel -->
{% include panel.html
title="Undo last commit"
content="
```bash
# undo last commit and leave changes unstaged
git reset HEAD~
# undo last commit and leave changes staged
git reset --soft HEAD~
# undo last commit and undo changes (WARNING: This is permanent)
git reset --hard HEAD~
```
<sub>*Reference: [How to undo the last commits in Git?](https://stackoverflow.com/questions/927358/how-to-undo-the-last-commits-in-git)*</sub>

" %}
<!-- end -->
<!--  panel -->
{% include panel.html
title="Revert file permission changes in local git repository"
content="
```bash
git diff -p \
    | grep -E '^(diff|old mode|new mode)' \
    | sed -e 's/^old/NEW/;s/^new/old/;s/^NEW/new/' \
| git apply
```

<sub>*Reference: [Gist](https://gist.github.com/jtdp/5443498)*</sub>
" %}
<!-- end -->
<!--  panel -->
{% include panel.html
title="View history of changes in a specific directory with diffs"
content="
`git log -p DIR`
" %}
<!-- end -->
<!--  panel -->
{% include panel.html
title="View changes between branches (optionally in a specific directory)"
content="
`git diff master..yourbranch path/to/folder`
" %}
<!-- end -->
<!--  panel -->
{% include panel.html
title="Change commit author at one specific commit"
content="
1. Go to the commit immediately before the commit you want to edit: `git rebase -i <earliercommit>`
2. In the list of commits being rebased, change the text from **pick** to **edit** next to the hash of the one you want to modify.
3. Then do one of the following:
    * `git commit --amend --author="Author Name <email@address.com>"`
    * `git commit --amend --reset-author --no-edit`
4. Finally end the rebase: `git rebase --continue`


<sub>*Reference: [Gist](https://stackoverflow.com/a/3042512)*</sub>
" %}
<!-- end -->
<!--  panel -->
{% include panel.html
title="How to set git user and email per directory"
content="
**1.** Install [`ondir`](http://swapoff.org/ondir.html) (on a Mac: `brew install ondir`, other OSs need to install it from the linked page).  
**2.** Put these functions into your shell profile (e.g. .profile, .zshrc):

```bash
# ondir configuration
cd() {
builtin cd \"$@\" && eval \"`ondir \"$OLDPWD\" \"$PWD\"`\"
}
pushd() {
builtin pushd \"$@\" && eval \"`ondir \"$OLDPWD\" \"$PWD\"`\"
}
popd() {
builtin popd \"$@\" && eval \"`ondir \"$OLDPWD\" \"$PWD\"`\"
}
eval \"`ondir /`\"
```
**3.** Configure ondir by putting these lines into `~/.ondirrc` (adapt it to whatever you need):

```bash
enter ~/dev/work
export GIT_AUTHOR_NAME='Name at work'
export GIT_AUTHOR_EMAIL='email@work.com'
export GIT_COMMITTER_NAME='Name at work'
export GIT_COMMITTER_EMAIL='email@work.com'
echo 'Switched to git user/email settings for \"work\".'

leave ~/dev/work
unset GIT_AUTHOR_NAME
unset GIT_AUTHOR_EMAIL
unset GIT_COMMITTER_NAME
unset GIT_COMMITTER_EMAIL
echo 'Switched back to global git user/email settings.'
```
**4.** Now when you cd to ~/dev/work, git config user.name will still show the global git user name, but for commits, the environment variable will be used (check with echo $GIT_AUTHOR_NAME).  
Don't forget to source the changed shell profile to your current shell session.  
<sub>*Reference: [How to set git user and email per directory](https://makandracards.com/makandra/19549-how-to-set-git-user-and-email-per-directory)*</sub>
" %}
<!-- end -->
</div>
