# Git 12: Workflow

## Overall Workflow

When working with branches, here is the general workflow to adhere to.

1. Before starting work:

```bash
# always start your branching from the master branch
git checkout master

# pull the latest
git pull

# create a new branch, branch-ed off of the master branch
git checkout -b my-awesome-feature

```

2. Commit changes and push to your branch in GitHub regularly.

```
git add filename1
git add filename2
git add filename3

git commit -m "descriptive message of the change i just made"

git push
```

3. Also make sure to periodically

- Check in with your teammates
- pull from master: `git pull origin master`

Pulling from master periodically is very important! This will keep your code relatively insync and prevent deferring massive merge conflicts down the line.

4. When you're done with your work make sure you've commited all your changes
  ```
  git status
  git push
  ```
  then open up github and issue a pull request back to master.

## Workflow TYpes

### Feature Branches

The feature branch workflow is where every small or large feature gets its own branch. These branches are shortlived and are quickly merged back into master. Each feature branch corresponds to a pull request and the branch is deleted after the PR is merged.

### Workflow 2: Team Member Branches

The team member workflow is where each team member gets their own branch. These branches stay alive throughout the duration of the project and can be merged back in as frequently as you like. In this approach you can only have one PR open at a given time per team member.
