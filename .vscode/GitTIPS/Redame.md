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

Work yesterday as pec1909@Melbage
The default interactive shell is now zsh.
To update your account to use zsh, please run `chsh -s /bin/zsh`.
For more details, please visit https://support.apple.com/kb/HT208050.
(base) Users-MacBook-Pro:GITTest paulcarter$ pwd
/Users/paulcarter/Documents/Labs/GITTest
(base) Users-MacBook-Pro:GITTest paulcarter$ git clone https://github.com/Melbage/TAU.git
Cloning into 'TAU'...
remote: Enumerating objects: 18, done.
remote: Counting objects: 100% (18/18), done.
remote: Compressing objects: 100% (13/13), done.
remote: Total 18 (delta 1), reused 12 (delta 0), pack-reused 0
Unpacking objects: 100% (18/18), done.
(base) Users-MacBook-Pro:GITTest paulcarter$ git log
fatal: Not a git repository (or any of the parent directories): .git
(base) Users-MacBook-Pro:GITTest paulcarter$ pwd
/Users/paulcarter/Documents/Labs/GITTest
(base) Users-MacBook-Pro:GITTest paulcarter$ ls
TAU
(base) Users-MacBook-Pro:GITTest paulcarter$ cd TAU
(base) Users-MacBook-Pro:TAU paulcarter$ git log
commit 1bb5b61b463b7aeaafe819fe8fc85c0f20677a41 (HEAD -> main, origin/main, origin/HEAD)
Author: Melbage <68875651+Melbage@users.noreply.github.com>
Date:   Mon Jan 4 18:41:27 2021 +0000

    Update Redame.md

commit 9740d09ad78c1411007f39160714276129f206df
Author: melbage <tubby@melbage.co.uk>
Date:   Mon Jan 4 18:29:12 2021 +0000

    added more comments

commit 7fb33f021a4a5e43bcd13b667221239ce0da75ec
Author: pcarter <pec1909@yahoo.co.uk>
Date:   Sun Jan 3 22:12:56 2021 +0000

    initalized project
     #Initial commit
(base) Users-MacBook-Pro:TAU paulcarter$ git commit -am"testing git commit"
[main aa36f39] testing git commit
 1 file changed, 2 insertions(+)
(base) Users-MacBook-Pro:TAU paulcarter$ git push
Counting objects: 5, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 580 bytes | 580.00 KiB/s, done.
Total 5 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Melbage/TAU.git
   1bb5b61..aa36f39  main -> main
(base) Users-MacBook-Pro:TAU paulcarter$ git log
commit aa36f39a532afdc3c0e281eb4406b1cafe7c3c5d (HEAD -> main, origin/main, origin/HEAD)
Author: Melbage <tubby@Melbage.co.uk>
Date:   Mon Jan 4 22:33:57 2021 +0000

    testing git commit

commit 1bb5b61b463b7aeaafe819fe8fc85c0f20677a41
Author: Melbage <68875651+Melbage@users.noreply.github.com>
Date:   Mon Jan 4 18:41:27 2021 +0000

    Update Redame.md

commit 9740d09ad78c1411007f39160714276129f206df
Author: melbage <tubby@melbage.co.uk>
Date:   Mon Jan 4 18:29:12 2021 +0000

    added more comments

commit 7fb33f021a4a5e43bcd13b667221239ce0da75ec
Author: pcarter <pec1909@yahoo.co.uk>
Date:   Sun Jan 3 22:12:56 2021 +0000

    initalized project
     #Initial commit
(base) Users-MacBook-Pro:TAU paulcarter$ git branch -l -a
* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git config -l --local
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
remote.origin.url=https://github.com/Melbage/TAU.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.main.remote=origin
branch.main.merge=refs/heads/main
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is behind 'origin/main' by 3 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git pull
Updating aa36f39..fa4ee17
Fast-forward
 .vscode/GitTIPS/Redame.md | 21 +++++++++++++++++++--
 1 file changed, 19 insertions(+), 2 deletions(-)
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git commit -a 
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git reflogfa4ee17 (HEAD -> main, origin/main, origin/HEAD) HEAD@{0}: pull: Fast-forward
aa36f39 HEAD@{1}: commit: testing git commit
1bb5b61 HEAD@{2}: clone: from https://github.com/Melbage/TAU.git
(base) Users-MacBook-Pro:TAU paulcarter$ pwd
/Users/paulcarter/Documents/Labs/GITTest/TAU
(base) Users-MacBook-Pro:TAU paulcarter$ ls -la
total 16
drwxr-xr-x   6 paulcarter  staff  192 Jan  4 22:27 .
drwxr-xr-x   3 paulcarter  staff   96 Jan  4 22:27 ..
drwxr-xr-x  16 paulcarter  staff  512 Jan  4 22:58 .git
-rw-r--r--   1 paulcarter  staff   12 Jan  4 22:27 .gitignore
drwxr-xr-x   4 paulcarter  staff  128 Jan  4 22:27 .vscode
-rw-r--r--   1 paulcarter  staff   60 Jan  4 22:27 TAU.code-workspace
(base) Users-MacBook-Pro:TAU paulcarter$ 
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git reflog
5b76d07 (HEAD -> main, origin/main, origin/HEAD) HEAD@{0}: commit: accept pec changes
fa4ee17 HEAD@{1}: pull: Fast-forward
aa36f39 HEAD@{2}: commit: testing git commit
1bb5b61 HEAD@{3}: clone: from https://github.com/Melbage/TAU.git
(base) Users-MacBook-Pro:TAU paulcarter$ git status
On branch main
Your branch is behind 'origin/main' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)

nothing to commit, working tree clean
(base) Users-MacBook-Pro:TAU paulcarter$ git pull
Updating 5b76d07..ac1b78e
Fast-forward
(base) Users-MacBook-Pro:TAU paulcarter$ git reflog
ac1b78e (HEAD -> main, origin/main, origin/HEAD) HEAD@{0}: pull: Fast-forward
5b76d07 HEAD@{1}: commit: accept pec changes
fa4ee17 HEAD@{2}: pull: Fast-forward
aa36f39 HEAD@{3}: commit: testing git commit
1bb5b61 HEAD@{4}: clone: from https://github.com/Melbage/TAU.git
(base) Users-MacBook-Pro:TAU paulcarter$ git branch -M Master
(base) Users-MacBook-Pro:TAU paulcarter$ git reflog
ac1b78e (HEAD -> Master, origin/main, origin/HEAD) HEAD@{0}: Branch: renamed refs/heads/main to refs/heads/Master
ac1b78e (HEAD -> Master, origin/main, origin/HEAD) HEAD@{2}: pull: Fast-forward
5b76d07 HEAD@{3}: commit: accept pec changes
fa4ee17 HEAD@{4}: pull: Fast-forward
aa36f39 HEAD@{5}: commit: testing git commit
1bb5b61 HEAD@{6}: clone: from https://github.com/Melbage/TAU.git
(base) Users-MacBook-Pro:TAU paulcarter$ git reflog