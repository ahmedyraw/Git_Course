# Git_Course

## Create Remote Repo
You can create Repo using Github UI then diceide if it's public or private also if you want a read me file\
1- Go to your repositories\
2- Press new, and name it\
3- Private or Public\
4- Readme file<br/><br/>
the readme file extension is md "Markdown" you can check it here\
After you finish an link will be auto generated that points for the remote repo\
[Markdown documentation](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)<br/>

## Clone Remote Repo to a Local Repo
syntax: ```git clone RepoLink```\
ex: ```git clone https://github.com/example/Git_Course.git```

## Add And Reset And Commit & Explain Progress
After you finish your Working Directory all it's content will be untracked you can check it by:
### git status
syntax: ```git status```<br/>
ouput example:
```
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        Stages.png
        css/
        index.html.txt
nothing added to commit but untracked files present (use "git add" to track)
```
This mean there are two files name css and index.html that our remote repo doesn't know anything about it,\
you must add them to staging area then commit then push them to remote area\

Working Directory & Staging Area & Local Repo are all part of Local Repo.\
Working Directory -```git add```> Staging Area -```git commit```> Local Repo -```git push```> Remote Repo\
Remote Repo -```git fetch```> Local Repo\
Local Repo -```git checkout```> Working Directory\
Local Repo -```git merge```> Working Directory

### git add
syntax: ```git add FileName or *```\
ex1: ```git add css```\
ex2: ```git add css index.html```\
ex3: ```git add *``` star is wild card means all

output example:
```
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   Stages.png
        new file:   css/main.css.txt
        new file:   index.html.txt
```

Now after all untracked files are added to Staging Area if you run ```git status``` you will see the following output:
```
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   Stages.png
        new file:   css/main.css.txt
        new file:   index.html.txt
```
All of this files are in Staging Area and are needed to go to Local Repo but what if there are some file you don't want them in the Local Repo?\
lets say you added a file name ahmed.txt run ```git status``` you will see the following output:
```
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ahmed.txt
```

### git reset
syntax: ```git reset head FileName```\
ex: ```git reset head ahmed.txt```\
now this file is only in Working Directory and remove from Staging Area but how know? run ```git status``` you will see the following output:
```
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ahmed.txt
```

### git commit
syntax: ```git commit -m "description"```\
ex: ```git commit -m "Created the main project structure."```\
output example:
```
[main 3345bd2] Created the main project structure.
 3 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 Stages.png
 create mode 100644 css/main.css.txt
 create mode 100644 index.html.txt
```
Now all the files are commited and in Local Repo\
maybe you will see the following output:
```
Author identity unknown

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.

fatal: unable to auto-detect email address (got 'anything.(none)')
```
here just run those two commands in first add your email and sceond your github/gitlab/etc.. name
```
  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"
```
now run ```git status``` to see status you will see the following output:
```
On branch main
Your branch is ahead of 'origin/main' by 1 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

if there are more files you added to working directory and you want to push them don't push the current state unitl you add them to Staging Area and commit them to Local Repo them you push.

## Push Local Changes To Remote Repository
now everhing is commited in Local Repo
### git branch
syntax: ```git branch```\
output example:
```
* main
```
will list all branches that are in Local Repo, main -> origin, main is Local Repo, origin is Remote Repo "github, gitlab, etc.."
### git remote
syntax: ```git remote -v```\
output example:
```
origin  https://github.com/ahmedyraw/Git_Course.git (fetch)
origin  https://github.com/ahmedyraw/Git_Course.git (push)
```
will return the origin "Remote Repo"
### git push
syntax: ```git push RemoteRepoName BranchName```\
ex: ```git push origin main```\
output example:
```
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 24 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (10/10), 373.75 KiB | 31.15 MiB/s, done.
Total 10 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (3/3), done.
To https://github.com/ahmedyraw/Git_Course.git
   c739d2c..5b14288  main -> main
```
if you go to your repository and relode it you will see N commits try browse it also you will see the description with each commit.\
lets now edit the main.css file located in css folder after editing the file run ```git status``` you will see the following output:
```
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   css/main.css.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
you need to do the following:
```
git add css\main.css
git commit -m "Modified the css file"
git push origin main
```
sometime your push will be rejected as this:
```
To https://github.com/ahmedyraw/Git_Course.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'https://github.com/ahmedyraw/Git_Course.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```
all what you need to do is:
```
git pull origin main --rebase
git rebase --continue
git push origin main
```
