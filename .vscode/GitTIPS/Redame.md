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
