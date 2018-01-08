# Git 12: Workflow

## Overall Workflow

When working with branches, here is the general workflow to adhere to.

1. Before starting work:

```
# always start your branching from the master branch
git checkout master

# pull the latest
git pull

# create a new branch, branch-ed off of the master branch
git checkout -b my-awesome-feature

```

2. Make your changes. While working...

```
# periodically commit your changes
git commit -m "making some changes in my branch"

# push the changes back up to your branch
git push

# periodically pull the latest from master back into your feature branch
git pull origin master
```

3. When you're done, create a pull request and merge your changes back into master.

Be sure to periodically pull `master` back into your branch via `git pull origin master` for long standing branches. This will keep your code relatively insync and prevent deferring massive merge conflicts down the line.

## Workflow TYpes

### Feature Branches

The feature branch workflow is where every small or large feature gets its own branch. These branches are shortlived and are quickly merged back into master. Each feature branch corresponds to a pull request and the branch is deleted after the PR is merged.

### Workflow 2: Team Member Branches

The team member workflow is where each team member gets their own branch. These branches stay alive throughout the duration of the project and can be merged back in as frequently as you like. In this approach you can only have one PR open at a given time per team member.
