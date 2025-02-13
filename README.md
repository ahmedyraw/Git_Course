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

## Clone it
syntax: ```git clone RepoName```\
ex: ```git clone https://github.com/example/Git_Course.git```

## Add And Reset And Commit & Explain Progress
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
