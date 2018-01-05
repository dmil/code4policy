# Git 4: Branching

## Why branches?

When using Git, branches are a part of your everyday development process. Git branches are effectively a pointer to a snapshot of your changes. When you want to add a new feature or fix a bug—no matter how big or how small—you spawn a new branch to encapsulate your changes. This makes it harder for unstable code to get merged into the main code base, and it gives you the chance to clean up your future's history before merging it into the main branch.

There are many different use cases for branches ranging from the aforementioned "feature branches", "release branches", dev/test/qa branches, and more.

## How do branches work?

When creating a new repository, git by default starts with a `master` branch which is what we have been using until now. When we create branches, we are branching *off of* the most recent commit on the master branch.

![](https://wac-cdn.atlassian.com/dam/jcr:746be214-eb99-462c-9319-04a4d2eeebfa/01.svg)

The diagram above visualizes a repository with two isolated lines of development, one for a little feature, and one for a longer-running feature. By developing them in branches, it’s not only possible to work on both of them in parallel, but it also keeps the main master branch free from questionable code.

After developing a feature, it needs to be merged back into the master branch. We will do this using a [Pull Request](https://help.github.com/articles/about-pull-requests/).

## How does merging work?

![](https://wac-cdn.atlassian.com/dam/jcr:86eba9ec-9391-45ea-800a-948cec1f2ed7/Branch-2.png)

When creating a branch, the head of the branch splits off of a common base as seen in the picture above. This is why we refer to Git as a *non-linear workflow*. There are three new commits on the feature branch and 2 new commits directly on the master branch.

![](https://wac-cdn.atlassian.com/dam/jcr:83323200-3c57-4c29-9b7e-e67e98745427/Branch-1.png)

When come time to merge, the difference between the 2 new commits on the master branch and the new code in the feature branch is resolved in what is referred to as a **merge commit**. Git tries to be as smart as possible when merging code but occasionally there are changes that cannot automatically be merged. This is when we run into a **merge conflict**. We will talk more about this in detail.

Sources:

- https://www.atlassian.com/git/tutorials/using-branches
- https://www.atlassian.com/git/tutorials/using-branches/git-merge

## Pull Requests

While there are other ways to merge branches, we will be using pull requests. When using the [shared repository model](https://help.github.com/articles/about-collaborative-development-models/) (one repository, multiple collaborators), 

- **base**: almost always the master branch. this is where you are merging on to
- **compare**: this is your feature branch. this is where you are merging from

![](https://s3.amazonaws.com/media-p.slid.es/uploads/489063/images/3229907/Comparing_master___endorsement___dmil_dhrumil-simple-website.png)

In this screenshot, I am creating a Pull Request from the `endorsement` branch (compare) to the `master` branch (base). Note that this pull request has 1 commit.

## Commands

#### List Branches

```
git branch
```

#### Create (and switch to) a new branch

The `-b` flag creates a new branch.

```
git checkout -b <branchname>
```

#### Switch branch

```
git checkout <branchname>
```

#### Delete branch

```
git branch -d <branchname>
```

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example

1. `cd` into the assignments repository (`~/Development/assignments`).

2. List the branches currently in the repository. It should just be `master` with an asterisk next to it showing that is the current active branch.

	```
	git branch
	```

3. Let's create a new branch called `add-comments`.

	```
	git checkout -b add-comments
	```

4. Run `git branch` to check that a new branch was created and it is the active branch. Your shell prompt (`PS1`) should also show the current active branch.

	```
	git branch
	```

5. Open sayhello.py in your text editor and to the best of your knowledge add comments describing what the code is doing.
	
	```python
	#!/usr/bin/env python2
	# this is a sample comment
	# add your own comments to describe what this script does
	import sys
	name = sys.stdin.read()
	print "Hello " + name + "!"
	```

6. Commit the change.

7. Run `git status` to make sure the repository is "clean" (i.e. there are no "untracked files", "unstaged changes", or "staged changes").

8. Run git log and see that your new commit is in the list.

9. Switch back to the master branch.

	```
	git checkout master
	```

10. Run `git log` again. Notice that the commit does not appear in the history of the master branch.

11. Push the changes from the feature branch.

	Remember that `origin` is the name of the `remote` on github.com. You can run `git remote -v` to see the full url of the repository. Because we are pushing to the feature branch, we specify the branch as the second *positional argument*.

	```
	git push origin add-comments
	``` 

12. Go to github.com and see the branch appear in the dropdown window. Click on it and then view the list of commits within this branch.

13. Go to the pull requests tab and create a new pull request. Leave `base` as `master` and set the `compare` branch to your new `add-comments` branch. Give it a title and a description and create the pull request.

14. Review the files changed and click the big green merge button on the bottom of the PR.

### Example Branches and PRs in the Wild

Private FiveThirtyEight repository:

- [https://github.com/fivethirtyeight/general-forecast](https://github.com/fivethirtyeight/general-forecast)
- https://projects.fivethirtyeight.com/2016-election-forecast/

Public 18F repository:

- [https://github.com/18F/web-design-standards](https://github.com/18F/web-design-standards)

Example PRs:

- For example #471, 468, 461 in #general-forecast

## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

1. In `<name>-simple-website/` create a new branch called `linkedin-link`

2. In this new branch, put a link to your LinkedIn profile at the bottom of your simple website.

	```
	<a href src="https://www.linkedin.com/in/dhrumilmehta">  Find me on LinkedIn!</a>
	```

3. Commit the change in the feature branch.

4. Create a pull request from the feature branch and merge it.

5. Check the website online and make sure it has changed.

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example

1. `cd` to the `universe` repository at `~/Development/universe`.

2. Run `git status` to make sure the repository is "clean" (i.e. there are no "untracked files", "unstaged changes", or "staged changes").

3. Run `git pull` to ensure you have the latest changes in the repository.
  
  You probably do since you're the only one working on this repository, but it's good to get in a habbit of always running `git pull` before working on anything, especialy when collaborating.

3. Create a branch called `blue-universe`.
	1. Modify the facts in `mars.txt` to add a new line "Mars is blue". Use `git diff` to ensure that you only modifeid that one line and nothing else.
	2. Commit this change to the branch.
	3. Push the branch.
	4. Create a pull request but do not merge it.

4. Check out the master branch and then create a new branch called `red-universe`.
	1. Modify the facts in `mars.txt` to add a new line "Mars is red". Use `git diff` to ensure that you only modifeid that one line and nothing else.
	2. Commit this change to the branch.
	3. Push the branch.
	4. Create a pull request but do not merge it.

5. Merge the `red-universe` pull request. Try to merge the `blue-universe` pull request and it should say the branch cannot be automatically merged. This mean's there is a merge conflict.

6. Create a branch called `the-upside-down`.
	1. Edit `united_states.txt` with the text: "Hawkins, Indiana: The Demogorgon was here."
	2. Commit this change to the branch.
	3. Push the branch.
	4. Do not merge this branch back in as [the upside down](http://strangerthings.wikia.com/wiki/The_Upside_Down) runs parallel to the real `universe`...

## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

1. Make sure the repository is clean and you are in the master branch.

2. Create a branch called `alternative-facts`.
 
3. Go back to (checkout) the `master` branch.
  1. Add two facts to `mars.txt`: "Mars has polar ice caps." and "Mars is a little more than half the size of earth."
  2. Rename `united_states.txt` to `beynation.txt`.
  2. Commit these changes to `master`.

4. Checkout the `alternative-facts` repository.
  1. Add two facts to `mars.txt`. "Mars is gaseous." and "Mars is double the size of earth."
  2. Commit these changes to `alternative-facts`.
  3. Create a pull request using `alternative-facts`.

5. Attempt to merge the pull request and try to resolve the merge conflicts.

  Note that the changes that don't conflict (such as the renamed file in `master`) will merge just fine.

## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

1. Get into your teams and come up with a team name and a product owner if you haven't already done so.

2. Have the product owner create a **blank** repository (no README) under their account with the name of the team as the name of the repo. 

3. Add the remaining team members as collaborators to the repo. This is done under the repo settings. 

4. Enable github pages on this repo with the `master` branch as the source.

5. Everyone should clone the empty repository.

5. The product owner should create an `index.html` with the name of your team and a folder called `our-team`. Commit and push this change directly to the `master` branch.

6. Everyone else should pull these changes.

7. All team memmbers, including the product owner, should create feature branches titled `add-member-<name>`. In this branch, create a file within the `our-team` foler that is titled `<name>.html`. For example, I would create `our-team/dhrumil.html`. Add some basic information about yourself to this page. Be sure to only create this one file - there should be no other changes to the repository. It's important to keep your code changes isolated when working with git to avoid unecessary merge conflicts.
	1. Commit this change to the feature branch, push it, and create a pull request.
	2. Product Lead should review and merge all of the PRs. There should be no conflicts.

