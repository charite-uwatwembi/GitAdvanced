# Part 1
## Initial commits

```bash
charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ touch test{1..4}.md
git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"  
```

##  Missing filesfix

```bash
$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

no changes added to commit (use "git add" and/or "git commit -a")

$ git log
commit f8fe744b28eec1fc11b618f3017eeb1d7f9f1d18 (HEAD -> main)
Author: Beyla Irakoze <beylaruz@gmail.com>
Date:   Mon May 20 18:04:25 2024 +0200

    chore: Create third and fourth files

commit 8c6f71040a038c7f677efe45b80837b8f7e1db6e
Author: Beyla Irakoze <beylaruz@gmail.com>
Date:   Mon May 20 18:04:22 2024 +0200

    chore: Create another file

commit d43353b2f04e6d62a11825c5df3c8658a51158c6
Author: Beyla Irakoze <beylaruz@gmail.com>
Date:   Mon May 20 18:04:21 2024 +0200

    chore: Create initial file

commit f4b68f980b96895157f2d4aee81b68555c3766d9 (origin/main, origin/HEAD)
Author: Beyla Ruzindana Irakoze <142901020+beylar@users.noreply.github.com>
Date:   Mon May 20 18:02:20 2024 +0200

    Initial commit

```
## staging/adding test4.md and amending the commit message 
```bash
$ git add test4.md & git commit --amend
[1] 1561
[main 5950ba5] chore: Create fourth files        
 Date: Mon May 20 18:04:25 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
[1]+  Done                    git add test4.md

$ git rebase -i
Stopped at 3fe93ab...  chore: Create another file
You can amend the commit now, with

  git commit --amend

Once you are satisfied with your changes, run

  git rebase --continue

  $ git commit --amend
[detached HEAD d5a60f7] chore: Create second file
 Date: Mon May 20 19:21:47 2024 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md

 $ git rebase --continue
Successfully rebased and updated refs/heads/main.
```
## Editing Commit History:

```bash
$ git rebase -i HEAD~3
[detached HEAD 0fe95f3] chore: Create initial file
 Date: Tue May 21 08:55:11 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

$ git log
commit 5b89fe19b4e4e7706f9500bd94c3680e9d28423e (HEAD -> main)
Author: Beyla Irakoze <beylaruz@gmail.com>
Date:   Tue May 21 08:55:16 2024 +0200

    chore: Create fourth files

commit 0fe95f35a975d06ef3967004a375d36e4a7954e1
Author: Beyla Irakoze <beylaruz@gmail.com>
Date:   Tue May 21 08:55:11 2024 +0200

    chore: Create initial file

    chore: Create second file
```
## Splitting a Commit:
```bash
$ git reset HEAD~

$ git add test3.md & git commit -m "Create third files"
[1] 581
[main 0c94a37] Create third files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
[1]+  Done                    git add test3.md

$ git add test4.md & git commit -m "Create fourth files"
[1] 598
[main 437a4e8] Create fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md
[1]+  Done                    git add test4.md

$ git rebase -i HEAD~3
[detached HEAD 8482af7] Create third and fourth files
 Date: Tue May 21 10:41:32 2024 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.

$ git log
commit 8482af71de1e0211449029de0646ce1060769711 (HEAD -> main)
Author: Beyla Irakoze <beylaruz@gmail.com>
Date:   Tue May 21 10:41:32 2024 +0200

    Create third and fourth files

commit 0fe95f35a975d06ef3967004a375d36e4a7954e1
Author: Beyla Irakoze <beylaruz@gmail.com>
Date:   Tue May 21 08:55:11 2024 +0200

    chore: Create initial file

    chore: Create second file

commit 42aa524481bf3ae39e804e76f16e706cfaf77642 (origin/main, origin/HEAD)
Author: Beyla Ruzindana Irakoze <142901020+beylar@users.noreply.github.com>
Date:   Tue May 21 08:52:02 2024 +0200

    Initial commit

```

## Dropping a acommit 

```bash
$ touch unwanted.txt

$ git add unwanted.txt & git commit -m "Unwanted text"
[1] 748
[main a92dfa6] Unwanted text
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 unwanted.txt
[1]+  Done                    git add unwanted.txt
charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ ls
test1.md  test2.md  test3.md  test4.md  unwanted.txt

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git add unwanted.txt && git commit -m "Unwanted commit"
[main b48734a] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git rebase -i
fatal: invalid upstream 'refs/remotes/origin/main'

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git log
commit b48734aab308cdfe925124ee57a3acb0a26f4299 (HEAD -> main)
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 11:13:11 2024 +0200

    Unwanted commit

commit c0d894c2cf5e160dfd8f18efe47c9c2cda219a5f
pick 085b24d chore: Create second file
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:56:56 2024 +0200

    Create third and fouth files

commit 085b24d81e594654408bc54d14f6cb7760a59531
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git rebase -i
fatal: invalid upstream 'refs/remotes/origin/main'

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git rebase -i HEAD~3
Successfully rebased and updated refs/heads/main.

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git rebase -i
fatal: invalid upstream 'refs/remotes/origin/main'

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git log
commit b48734aab308cdfe925124ee57a3acb0a26f4299 (HEAD -> main)
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 11:13:11 2024 +0200

    Unwanted commit

commit c0d894c2cf5e160dfd8f18efe47c9c2cda219a5f
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:56:56 2024 +0200

    Create third and fouth files

commit 085b24d81e594654408bc54d14f6cb7760a59531
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git reset --hard HEAD~1
HEAD is now at c0d894c Create third and fouth files

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git log
commit c0d894c2cf5e160dfd8f18efe47c9c2cda219a5f (HEAD -> main)
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:56:56 2024 +0200

    Create third and fouth files

commit 085b24d81e594654408bc54d14f6cb7760a59531
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

    chore: Create second file

commit 897dbc951eb42e7b09a731223d5b80f5da1c3db7
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
```
## Reordering Commits:
```bash
$ git log
commit c0d894c2cf5e160dfd8f18efe47c9c2cda219a5f (HEAD -> main)
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:56:56 2024 +0200

    Create third and fouth files

commit 085b24d81e594654408bc54d14f6cb7760a59531
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

    chore: Create second file


commit 897dbc951eb42e7b09a731223d5b80f5da1c3db7
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git rebase -i HEAD~3
fatal: invalid upstream 'HEAD~3'

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/main.

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git log
commit 29ae585837afbc1a4d6a13e212a2a371b8280263 (HEAD -> main)
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

    chore: Create second file

commit e9c5e5709e93e008e941b75e38020362e1eb01ee
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:56:56 2024 +0200

    Create third and fouth files

commit 897dbc951eb42e7b09a731223d5b80f5da1c3db7
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
```
## Cherry-Picking Commits:

```bash
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git branch
* ft/branch
  main

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ touch test5.md

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git add test5.md 

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git commit -m "Implemented Test 5"
[ft/branch ffd0a46] Implemented Test 5
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git log
commit ffd0a467c2c8027e630aeaba44b5d86066913dc0 (HEAD -> ft/branch)
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 11:48:41 2024 +0200

    Implemented Test 5

commit 29ae585837afbc1a4d6a13e212a2a371b8280263 (main)
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

    chore: Create second file

commit e9c5e5709e93e008e941b75e38020362e1eb01ee
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:56:56 2024 +0200

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git log
commit ffd0a467c2c8027e630aeaba44b5d86066913dc0 (HEAD -> ft/branch)
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 11:48:41 2024 +0200

    Implemented Test 5

commit 29ae585837afbc1a4d6a13e212a2a371b8280263 (main)
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

    chore: Create second file

commit e9c5e5709e93e008e941b75e38020362e1eb01ee
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:56:56 2024 +0200

    Create third and fouth files

commit 897dbc951eb42e7b09a731223d5b80f5da1c3db7
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

    chore: Create initial file

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git checkout main
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git branch
  ft/branch
* main

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git cherry-pick ffd0a467c2c8027e630aeaba44b5d86066913dc0
[main 7cfa395] Implemented Test 5
 Date: Tue May 21 11:48:41 2024 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git log
commit 7cfa39540ee3e84d6115223713f8231bdf9f95f6 (HEAD -> main)
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 11:48:41 2024 +0200

    Implemented Test 5

commit 29ae585837afbc1a4d6a13e212a2a371b8280263
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

    chore: Create second file

commit e9c5e5709e93e008e941b75e38020362e1eb01ee
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:56:56 2024 +0200

    Create third and fouth files

commit 897dbc951eb42e7b09a731223d5b80f5da1c3db7
Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
Date:   Tue May 21 10:40:17 2024 +0200

    chore: Create initial file

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git branch
  ft/branch
* main

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
```
## Visualizing Commit History (Bonus):
```bash
$ git log --graph
* commit 7cfa39540ee3e84d6115223713f8231bdf9f95f6 (HEAD -> main)
| Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
| Date:   Tue May 21 11:48:41 2024 +0200
|
|     Implemented Test 5
|
* commit 29ae585837afbc1a4d6a13e212a2a371b8280263
| Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
| Date:   Tue May 21 10:40:17 2024 +0200
|
|     chore: Create second file
|
* commit e9c5e5709e93e008e941b75e38020362e1eb01ee
| Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
| Date:   Tue May 21 10:56:56 2024 +0200
|
|     Create third and fouth files
|
* commit 897dbc951eb42e7b09a731223d5b80f5da1c3db7
  Author: charite-uwatwembi <c.uwatwembi@alustudent.com>
  Date:   Tue May 21 10:40:17 2024 +0200

      chore: Create initial file

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
```
## Understanding Reflogs (Bonus):
```bash
$ git reflog
7cfa395 (HEAD -> main) HEAD@{0}: cherry-pick: Implemented Test 5
29ae585 HEAD@{1}: checkout: moving from ft/branch to main
ffd0a46 (ft/branch) HEAD@{2}: commit: Implemented Test 5
29ae585 HEAD@{3}: checkout: moving from main to ft/branch
29ae585 HEAD@{4}: rebase (finish): returning to refs/heads/main
29ae585 HEAD@{5}: rebase (pick): chore: Create second file
e9c5e57 HEAD@{6}: rebase (pick): Create third and fouth files
897dbc9 HEAD@{7}: rebase (start): checkout HEAD~2
c0d894c HEAD@{8}: rebase (finish): returning to refs/heads/main
c0d894c HEAD@{9}: rebase (start): checkout HEAD~2
c0d894c HEAD@{10}: reset: moving to HEAD~1
b48734a HEAD@{11}: rebase (finish): returning to refs/heads/main
b48734a HEAD@{12}: rebase (start): checkout HEAD~3
b48734a HEAD@{13}: commit: Unwanted commit
c0d894c HEAD@{14}: rebase (finish): returning to refs/heads/main
c0d894c HEAD@{15}: rebase (squash): Create third and fouth files
78bd666 HEAD@{16}: rebase (start): checkout HEAD~3
84df39c HEAD@{17}: commit: Create fourth file
78bd666 HEAD@{18}: reset: moving to HEAD~
7e7a8db HEAD@{19}: rebase (finish): returning to refs/heads/main
7e7a8db HEAD@{20}: rebase (start): checkout HEAD~3
7e7a8db HEAD@{21}: commit: Create fourth file
78bd666 HEAD@{22}: commit: Create third file
085b24d HEAD@{23}: reset: moving to HEAD~
0cfc48e HEAD@{24}: rebase (finish): returning to refs/heads/main
0cfc48e HEAD@{25}: rebase: fast-forward
085b24d HEAD@{26}: rebase: fast-forward

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$

```
# Part2
## Feature Branch Creation:
```bash
charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git branch
  ft/branch
* ft/new-feature
  main
```

## Working on the Feature Branch:
```bash
charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ touch feature.txt

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$  git add feature.txt && git commit -m "Implemented core functionality for new feature"
[ft/new-feature 527e2bc] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

```
## Switching Back and Making More Changes:
```bash
charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git checkout main 
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git branch
  ft/branch
  ft/new-feature
* main

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ touche readme.txt
bash: touche: command not found

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ touch readme.txt

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git add readme.txt && git commit -m "Updated project Readme"
[main d7da6df] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

```
## Local vs. Remote Branches:
```bash

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git branch
  ft/branch
  ft/new-feature
* main

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git merge ft/new-feature
Merge made by the 'ort' strategy.
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git push origin main
Enumerating objects: 17, done.
Counting objects: 100% (17/17), done.
Delta compression using up to 8 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (17/17), 1.46 KiB | 298.00 KiB/s, done.
Total 17 (delta 7), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (7/7), done.
To https://github.com/charite-uwatwembi/GitAdvanced2.git
 * [new branch]      main -> main

```
## Branch Deletion
```bash
charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git branch -d ft/new-feature
Deleted branch ft/new-feature (was 527e2bc).
```

## Creating a Branch from a Commit
```bash

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git log -1 --pretty=format:%H HEAD~2
7cfa39540ee3e84d6115223713f8231bdf9f95f6

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$  git checkout -b ft/new-branch-from-commit 7cfa39540ee3e84d6115223713f8231bdf9f95f6
Switched to a new branch 'ft/new-branch-from-commit'
```

## Branch Merging
```bash
charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$  git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git branch
  ft/branch
  ft/new-branch-from-commit
* main

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git merge ft/new-branch-from-commit
Already up to date.

```
## Branch Rebasing:
```bash
harite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.
```
##  Renaming Branches
```bash
charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git branch
  ft/branch
* ft/improved-branch-name
  main

```
## Checking Out Detached HEAD:
```bash
charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git checkout d7da6df615ad76fa151ed4c9e0e0e29b4f2089a1
Note: switching to 'd7da6df615ad76fa151ed4c9e0e0e29b4f2089a1'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at d7da6df Updated project readme
```

# Part3
## Stashing Changes:

```bash
charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git stash
Saved working directory and index state WIP on main: c096427 Merge branch 'ft/new-feature'
```
## Retrieving Stashed Changes:
```bash

charite@DESKTOP-1JCVV8Q /d/Study/Studies/the_gym/GitAdvanced2
$ git stash pop
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (09ff8a80fbe45bc12326929ad2dc5882c52250b0)

```
## Branch Merging Conflicts (Continued):
```bash
```
## Resolving Merge Conflicts with a Merge Tool:
```bash
```
## Understanding Detached HEAD State:
```bash
```
## Ignoring Files/Directories:
```bash
```
## Working with Tags:
```bash
```
## Listing and Deleting Tags:
```bash
```
## Pushing Local Work to Remote Repositories:
```bash
```
# The End !
