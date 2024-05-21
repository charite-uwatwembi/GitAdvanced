```bash
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