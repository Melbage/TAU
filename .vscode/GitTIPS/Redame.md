# Command and command line tools 

## Configure VS Code to view the .git folder structure in the Explorer view. 
command P and sreach for open work space. either select the JSON one or setting option then ;
JSON file 
{
    "files.exclude": {
        "**/.git": false
    }
}
or remove the **/.git from your setting screen and save.


## Using the command line. 
 git init will create a new git repo where you are. In Vscode you can now see this. 
 -- set my user name
  git config user.name pcarter
 -- set my email 
  git config user.email pec1909@yahoo.co.uk

 These are used when saving the code.
  git -l --local 
 displays all my local setting for git. 
 as am on mac I have set the core. 
 added the following as am on mac system.
  git config core.autocrlf input
  git config core.safecrlf warn
 set my default editor .(vscode)
  git config core.editor "code --wait"

 created a .gitignore file at my root along with amaking the root a workspace of rth project. added the following to .gitignore, as these are on mac system.
 **/.DS_Store

to show that I have untracked files.
    git status 
        On branch master

        No commits yet

        Untracked files:
        (use "git add <file>..." to include in what will be committed)

            .vscode/

        nothing added to commit but untracked files present (use "git add" to track)
to see what branch and commits 
    got log
        fatal: your current branch 'master' does not have any commits yet
to add all the files from the folder
 git add .

 then compare the output again.
    git status
        On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   .gitignore
        new file:   .vscode/GitTIPS/Redame.md
        new file:   .vscode/settings.json
        new file:   TAU.code-workspace

to see all the files and the hash details for files. 
    git ls-files --stage
        100644 6a3e68da15877a8e092804b0413c24b39bda11c0 0       .gitignore
100644 e69de29bb2d1d6434b8b29ae775ad8c2e48c5391 0       .vscode/GitTIPS/Redame.md
100644 82cf781942a97be1545c546040b99d891702846e 0       .vscode/settings.json
100644 876a1499c09dc083612f43c53c0ae71b9c30c5b1 0       TAU.code-workspace

to add a comment
    git commit 
this will open the default editor (vscode) add comment and exit editor. the follwing is displayed. 
        [master (root-commit) 7fb33f0] initalized project  #Initial commit
        4 files changed, 14 insertions(+)
        create mode 100644 .gitignore
        create mode 100644 .vscode/GitTIPS/Redame.md
        create mode 100644 .vscode/settings.json
        create mode 100644 TAU.code-workspace

checking the status
    git status
        On branch master
        nothing to commit, working tree clean   

Will look now to link this with GITHUB. 
Git push will falt due to there not being a repo in git hub. therefore you need to create a repo on git and copy  the URL to the repo.
    git remote add origin <URL> 
then GIT Push
    git push --set-upstrem origin master
        You may get askef for username and password.
changed user to be melbage and create a repo in git called TAU.
after doing that tried to write it to the github.
base) Users-MacBook-Pro:TAU paulcarter$ git remote add origin git@github.com:Melbage/TAU.git
fatal: remote origin already exists.
(base) Users-MacBook-Pro:TAU paulcarter$ git push --set-upstream origin master
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch master
nothing to commit, working tree clean
does not look good. ;-((
<<<<<<< HEAD

in the end I did 
    git remote set-url origin https://github.com/Melbage/TAU.git
    git remote add origin https://github.com/Melbage/TAU.git
    git branch -M main
    git push -u origin main

=======
    
<<<<<<< HEAD
>>>>>>> 1bb5b61b463b7aeaafe819fe8fc85c0f20677a41
=======
Now opened up a second copy of the files. I have cloned the https://github.com/Melbage/TAU.git git repo. 

>>>>>>> aa36f39a532afdc3c0e281eb4406b1cafe7c3c5d

Work from yesterday as Tubby@melbage.
(base) Users-MacBook-Pro:TAU paulcarter$ git remote add origin git@github.com:Melbage/TAU.git
fatal: remote origin already exists.
(base) Users-MacBook-Pro:TAU paulcarter$ git push --set-upstream origin master
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch master
nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   .vscode/GitTIPS/Redame.md

no changes added to commit (use "git add" and/or "git commit -a")
(base) Users-MacBook-Pro:TAU paulcarter$ git commit -am"added more comments"
[master 9740d09] added more comments
 1 file changed, 108 insertions(+)
(base) Users-MacBook-Pro:TAU paulcarter$ git remote add origin git@github.com:Melbage/TAU.git
fatal: remote origin already exists.
(base) Users-MacBook-Pro:TAU paulcarter$ git remote add origin https://github.com/Melbage/TAU.gitfatal: remote origin already exists.
(base) Users-MacBook-Pro:TAU paulcarter$ git remote set-url origin https://github.com/Melbage/TAU.git
(base) Users-MacBook-Pro:TAU paulcarter$ git remote add origin https://github.com/Melbage/TAU.gitfatal: remote origin already exists.
(base) Users-MacBook-Pro:TAU paulcarter$ git remote add origin https://github.com/Melbage/TAU.gitfatal: remote origin already exists.
(base) Users-MacBook-Pro:TAU paulcarter$ git branch -M main
(base) Users-MacBook-Pro:TAU paulcarter$ git push -u origin main
Counting objects: 13, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (9/9), done.
Writing objects: 100% (13/13), 2.53 KiB | 2.53 MiB/s, done.
Total 13 (delta 0), reused 0 (delta 0)
To https://github.com/Melbage/TAU.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
(base) Users-MacBook-Pro:TAU paulcarter$ git log
commit 8b6ae81c330f9bb524e4f2b0c3095801c250adae (HEAD -> main)
Author: melbage <tubby@melbage.co.uk>
Date:   Mon Jan 4 18:44:35 2021 +0000

    changes to readme file.

commit 9740d09ad78c1411007f39160714276129f206df
Author: melbage <tubby@melbage.co.uk>
Date:   Mon Jan 4 18:29:12 2021 +0000

    added more comments

commit 7fb33f021a4a5e43bcd13b667221239ce0da75ec
Author: pcarter <pec1909@yahoo.co.uk>
Date:   Sun Jan 3 22:12:56 2021 +0000

    initalized project
     #Initial commit
(base) Users-MacBook-Pro:TAU paulcarter$ git statusOn branch main
Your branch and 'origin/main' have diverged,
and have 1 and 2 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both modified:   .vscode/GitTIPS/Redame.md

no changes added to commit (use "git add" and/or "git commit -a")
(base) Users-MacBook-Pro:TAU paulcarter$ git mergeerror: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 2 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both modified:   .vscode/GitTIPS/Redame.md

no changes added to commit (use "git add" and/or "git commit -a")
(base) Users-MacBook-Pro:TAU paulcarter$ git stash
.vscode/GitTIPS/Redame.md: needs merge
.vscode/GitTIPS/Redame.md: needs merge
.vscode/GitTIPS/Redame.md: unmerged (4259db286178aeaf8f1032c276bf1bd40ee97337)
.vscode/GitTIPS/Redame.md: unmerged (c31fe1916b1948b6879fa3223d330b489bd3e8c1)
.vscode/GitTIPS/Redame.md: unmerged (d55736f60016b90c252bb9860ce83ed9446f0a54)
fatal: git-write-tree: error building trees
Cannot save the current index state
(base) Users-MacBook-Pro:TAU paulcarter$ git stash list
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 2 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both modified:   .vscode/GitTIPS/Redame.md

no changes added to commit (use "git add" and/or "git commit -a")
(base) Users-MacBook-Pro:TAU paulcarter$ git reflog
8b6ae81 (HEAD -> main) HEAD@{0}: commit: changes to readme file.
9740d09 HEAD@{1}: Branch: renamed refs/heads/master to refs/heads/main
9740d09 HEAD@{3}: commit: added more comments
7fb33f0 HEAD@{4}: commit (initial): initalized project
(base) Users-MacBook-Pro:TAU paulcarter$ git merge
error: Merging is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
(base) Users-MacBook-Pro:TAU paulcarter$ git commit -m" merge test"
U       .vscode/GitTIPS/Redame.md
error: Committing is not possible because you have unmerged files.
hint: Fix them up in the work tree, and then use 'git add/rm <file>'
hint: as appropriate to mark resolution and make a commit.
fatal: Exiting because of an unresolved conflict.
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 2 and 1 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git pull origin
Auto-merging .vscode/GitTIPS/Redame.md
CONFLICT (content): Merge conflict in .vscode/GitTIPS/Redame.md
Automatic merge failed; fix conflicts and then commit the result.
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch and 'origin/main' have diverged,
and have 2 and 1 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)

        both modified:   .vscode/GitTIPS/Redame.md

no changes added to commit (use "git add" and/or "git commit -a")
(base) Users-MacBook-Pro:TAU paulcarter$ git commit -am"test2"
[main fa4ee17] test2
(base) Users-MacBook-Pro:TAU paulcarter$ git merge
Already up to date.
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git pull origin
Already up to date.
(base) Users-MacBook-Pro:TAU paulcarter$ git push
Counting objects: 15, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (12/12), done.
Writing objects: 100% (15/15), 1.65 KiB | 1.65 MiB/s, done.
Total 15 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
To https://github.com/Melbage/TAU.git
   aa36f39..fa4ee17  main -> main
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git reflog
fa4ee17 (HEAD -> main, origin/main) HEAD@{0}: commit (merge): test2
fb3235d HEAD@{1}: commit (merge): Merge branch 'main' of https://github.com/Melbage/TAU into main
8b6ae81 HEAD@{2}: commit: changes to readme file.
9740d09 HEAD@{3}: Branch: renamed refs/heads/master to refs/heads/main
9740d09 HEAD@{5}: commit: added more comments
7fb33f0 HEAD@{6}: commit (initial): initalized project
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git push
To https://github.com/Melbage/TAU.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/Melbage/TAU.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
(base) Users-MacBook-Pro:TAU paulcarter$ git pull
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 5 (delta 1), reused 5 (delta 1), pack-reused 0
Unpacking objects: 100% (5/5), done.
From https://github.com/Melbage/TAU
   fa4ee17..5b76d07  main       -> origin/main
Merge made by the 'recursive' strategy.
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is ahead of 'origin/main' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git push
Counting objects: 2, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 357 bytes | 357.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/Melbage/TAU.git
   5b76d07..ac1b78e  main -> main
(base) Users-MacBook-Pro:TAU paulcarter$ git reflog
ac1b78e (HEAD -> main, origin/main) HEAD@{0}: pull: Merge made by the 'recursive' strategy.
f29692f HEAD@{1}: commit: accepts git json change
fa4ee17 HEAD@{2}: commit (merge): test2
fb3235d HEAD@{3}: commit (merge): Merge branch 'main' of https://github.com/Melbage/TAU into main
8b6ae81 HEAD@{4}: commit: changes to readme file.
9740d09 HEAD@{5}: Branch: renamed refs/heads/master to refs/heads/main
9740d09 HEAD@{7}: commit: added more comments
7fb33f0 HEAD@{8}: commit (initial): initalized project
(base) Users-MacBook-Pro:TAU paulcarter$ git reflog
ac1b78e (HEAD -> main, origin/main) HEAD@{0}: pull: Merge made by the 'recursive' strategy.
f29692f HEAD@{1}: commit: accepts git json change
fa4ee17 HEAD@{2}: commit (merge): test2
fb3235d HEAD@{3}: commit (merge): Merge branch 'main' of https://github.com/Melbage/TAU into main
8b6ae81 HEAD@{4}: commit: changes to readme file.
9740d09 HEAD@{5}: Branch: renamed refs/heads/master to refs/heads/main
9740d09 HEAD@{7}: commit: added more comments
7fb33f0 HEAD@{8}: commit (initial): initalized project
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

