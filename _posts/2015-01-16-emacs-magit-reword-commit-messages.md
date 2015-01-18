---
layout: post
title: Emacs Magit tutorial | Rewrite older commit messages
---

I recently use Emacs's git client magit often.

Although understanding magit is not easy, so I'll show you how to rewrite commit messages you already commited on a local repository. You will eventually get the same result as you do with git rebase -i command.

Let's get to it!

<img src="{{ site.baseurl }}/images/2015/01/magit1.png" width="600" height="auto">

See the above screenshot. I have 7 commits already, and then run `M-x magit-status`, the magit status buffer will appear.

<img src="{{ site.baseurl }}/images/2015/01/magit2.png" width="600" height="auto">

On the magit status buffer, press `ll` (alphabet `l` twice) to show the commit log buffer. I'd like to change commit message "commit 4" and "commit 5". Move the cursor to the line of "commit 4", press `E` to edit commits from the current commit through HEAD.

<img src="{{ site.baseurl }}/images/2015/01/magit3.png" width="600" height="auto">

git-rebase-todo buffer will appeare with 4 commits. To only change the commit messages "commit 4" and "commit 5", type `r` on each commit to turn marking `pick` to `reword`.

<img src="{{ site.baseurl }}/images/2015/01/magit4.png" width="600" height="auto">

You can also use other marking commands other than reword:

+  `p`, pick = use commit
+  `r`, reword = use commit, but edit the commit message
+  `e`, edit = use commit, but stop for amending
+  `s`, squash = use commit, but meld into previous commit
+  `f`, fixup = like "squash", but discard this commit's log message
+  `x`, exec = run command (the rest of the line) using shell

With done the marking, `C-c C-c` to start editing. If you want to cancel editing, go to the magit status buffer, press `R` in addition `A` to abort the process.

<img src="{{ site.baseurl }}/images/2015/01/magit5.png" width="600" height="auto">

Edit commit message as usual. Done with `C-c C-c` and the next commit message edit buffer is coming.

<img src="{{ site.baseurl }}/images/2015/01/magit6.png" width="600" height="auto">

See the commit log buffer when you complete all the editings, 2 commit messages changed as planned :)


Note: You would need to check those changes won't affect the shared repository when you push to it.
