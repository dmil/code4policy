# Git Reference

Today we won't be using branching or forking, but we will be making regular use of github.

![](https://www.evernote.com/shard/s150/sh/3a1357b6-6250-432c-b5be-6bc0a895b97f/0a90b7cfc659e426/res/930e27c8-7194-484b-84f5-d411e15c2bc5/skitch.jpg?resizeSmall&width=832)

# Getting Started
This gets a repository from github down to your computer for the first time

```
git clone git@github.com:dmil/mehta-simple-website.git
```
# Every Morning
Grab any work that has been done on your github repo since you last pulled

```
git pull
```

# Workflow

Following is a workflow for commiting new changes to your local git repository

```
git status
git diff
git add <filename>
git status
git commit -m "present tense commit message"
```

push the latest changes to github

```
git push
```