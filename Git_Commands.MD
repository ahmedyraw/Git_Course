# Information
## What is Git and Github?
Git Is distributed version control system.\
Git Free and open source.\
Github is source for project and sources [GitFarm, GitLab, BitBucket].\
Github simplify using Git and provide some features.\
You can use Git without Github. Maybe with centralized server or etc..\
Git has GUI.

## Why you must learn Git?
Devs contribute to the same project.\
you can revert changes.\
You can collaborate to fix issues and create new features.\
You can solve conflicts.\
You can organize features.

## Words you will hear !
Repository (Repo) (هو المستودع الي بتحط فيه اكواد البروجكت كاملة)\
Branch (Branch from Repo)\
Local Repo\
Remote Repo (Github, Gitfarm, Gitlab, BitBucket, Server)\
Commit (Snapshot or Checkpoint in your local Repo)\
Clone (from Local or Remote)\
Push (Upload Local changes to Remote)\
Pull (you Pull changes from Remote Repo to your Local)\
Pull Request (tell other about your changes to pull it from local to remote it to their repo)

## Important Notes
Create Repository for every project.\
Create a new Branch for every feature or enhancement.\
No need to connect to Remote Repo while working on locally.\
Anyone can Push and Pull depends on permissions.

## Work Flow
Working Directory & Staging Area & Local Repo are all part of Local Repo.\
Working Directory -(git add)> Staging Area -(git commit)> Local Repo -(git push)> Remote Repo\
Remote Repo -(git fetch)> Local Repo\
Local Repo -(git checkout)> Working Directory\
Local Repo -(git merge)> Working Directory

## Content state
untracked,\
changes need to be committed\
nothing to commit, use git push

# Git Commands
```
git init
git remote add origin REMOTE_REPO_LINK

git clone REPO_LINK
git status

git add FILE_NAME
git add *
git reset head FILE_NAME
git commit -m "DESCRIPTION"

git branch
git remote -v

git push REMOTE_REPO LOCAL_REPO_BRANCH ==> 
git pull REMOTE_REPO

git help config
git config --list
git config --list --show-origin
git config -l
git config -l --show-origin
git config --global CONFIGURATION
git config --global CONFIGURATION "VALUE"
git config --global --unset CONFIGURATION
git config --global --edit

ssh-keygen -t AlgorithmType -b NumberOfBytes -C "Your Email"
cat FILE_PATH

git
```
```
git fetech origin
fet rebase
git pull REMOTE_REPO LOCAL_REPO_BRANCH -- rebase
git rebase --continue
```
