# Git and Github

## Install Git

### Windows 10
1. Enable [Bash on Ubuntu on Windows](http://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/)
2. Open the "Bash on Ubuntu on Windows"
3. Follow Ubuntu instructions

### Mac
1. Install the [Homebrew](http://brew.sh/) Package Manager
2. Open Terminal, update brew and install git

```
brew update
brew install git
```

### Ubuntu

1. Install Git

```
sudo apt-get install git
```

## Set up git

```
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR EMAIL ADDRESS"
```

## What is Git?

Keeping track of file versions is hard.
![](http://petapixel.com/assets/uploads/2015/07/psdrevisioning.jpg)

#### So what is Git, and why does it help us?
Above all else, Git is a fast and **distributed** version control system, that allows you to efficiently handle projects large and small.

Here are some problems we face as developers, and how git solves them:

#### Reverting to past versions

Git allows us to make save points at any time. These save points are called 'commits'. Once a save point is made, it's permanent, and allows us to go back to that save point at any time. From there, we can see what the code looked like at that point, or even start building off that version.

#### Keeping track of what each version 'meant'

Every commit has a description (commit message), which allows us to describe what changes were made between the current and previous commit. This is usually a description of what features were added or what bugs were fixed.

Additionally, git supports tagging, which allows us to mark a specific commit as a specific version of our code (e.g. '2.4.5').

#### Comparing changes to past versions

It's often important to see content of the actual changes that were made. This can be useful when:

* tracking down when and how a bug was introduced
* understanding the changes a team member made so you can stay up-to-date with progress
* reviewing code as a team for correctness or quality/style

Git allows us to easily see these changes (called a `diff`) for any given commit.

#### Fearlessness in making changes

In developing software, we often want to experiment in adding a feature or
refactoring (rewriting) existing code. Because git makes it easy to go back to a
known good state, we can experiment without worrying that we'll be unable to
undo the experimental work.

#### Three components of a git repository

1. The working directory
  - `git init` creates a git repo inside current working directory
  - `git init name_of_repo` creates a new folder and a git repo inside that
  - `git status`
2. The staging area
  - `git add .` adds changes from the working directory to the staging area
  - `git add <filename>` adds changes to filenames specified from the working directory to the staging area
3. The repo or commit
  - `git commit -m "commit message"` adds changes in staging area to the repository
  - `git log` shows

Section borrowed from [AlJohri](https://github.com/AlJohri/DAT-DC-12/blob/master/notebooks/intro-git.ipynb)

## Try It (Together)

1. Initialize a git repo inside your `python-playground/` folder.

	``` 
	git init 
	```

2. Add each file as a separate commit.

	```
	git add README.md
	git commit -m "add a README describing what this  repository is for."
	
	git add hello.py
	git commit -m "add a hello world python script"
	```

4. Show me the git log

	```
	git log
	```

## Try It

1. Navigate to your `~/Development/` folder in the terminal
2. Create a directory called `dhrumil-simple-website/` (BUT USE YOUR OWN NAME!!!!)
3. Create a new page called `index.html` with the `touch` command
4. In a text editor, add this simple HTML code.

	```
	<!DOCTYPE html>
	<html>
	<body>

	<h1>Hello,World</h1>

	</body>
	</html>
	```
	
4. Double click on that file to view it in a web browser (you can refresh the page to view it again after you add new code)

5. Commit to github what you have so far.

6. Add a heading and paragraph tag

	```
	<!DOCTYPE html>
	<html>
	<body>
	
	<h1>Hello,World</h1>
	<h2>My First Subheading</h2>
	
	<p>My first paragraph.</p>
	
	</body>
	</html>
	```
7. Commit this with a meaningful commit message.
8. Show me the git log

## Branching

See Branches

```
git branch
```

Create a new Branch

```
git checkout -b <branchname>
```

Delete Branches

```
git branch -D <branchname>
```

More on Branches

http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade-2#/4/13

### Try It (Together)
1. Look at the branches in your git repo

	```
	git branch
	```

2. in `python-playground/` create a new branch called `add-comments`

	```
	git checkout -b add-comments
	```
	
2. make sure you're on that branch

	```
	git branch
	```

2. open up your `hello.py` script and add a comment before each line of code so that it looks like this
	
	```
	# This python program demonstrates how to print a string.
	print "Hello World"
	```

3. commit the change in your new branch

	```
	git commit -m "added comments to python code"
	```
4. notice how this change doesn't exist in your "master" branch.

### Branches IRL (In Real Life)

Branches are frequently used to develop features on a project. People can work independently in branches and then issue a pull request back into master. That pull request is reviewed and merged into the branch.

Branches in one of our projects

[https://github.com/fivethirtyeight/general-forecast](https://github.com/fivethirtyeight/general-forecast)

https://projects.fivethirtyeight.com/2016-election-forecast/

Branches in a public repository

[https://github.com/18F/web-design-standards](https://github.com/18F/web-design-standards)

### Pull Requests (from branch)

For example #471, 468, 461 in #general-forecast

## Try It 
1. in `myname-simple-website/` create a new branch called `linkedin-link`
2. in this new branch, put a link to your linked in page at the bottom  of your simple website

	```
	<a href src="https://www.linkedin.com/in/dhrumilmehta">  find me on linked in! </a>
	```

3. commit the change to the branch

## Git, Conceptually

Under the Hood:

* [https://www.sbf5.com/~cduan/technical/git/](https://www.sbf5.com/~cduan/technical/git/)

How it works:

* [https://cs61.seas.harvard.edu/wiki/2012/Git](https://cs61.seas.harvard.edu/wiki/2012/Git)
* [http://www.eecs.harvard.edu/~cs161/resources/git.html](http://www.eecs.harvard.edu/~cs161/resources/git.html)

Git for Knowledge Workers:

* [https://git-scm.com/video/what-is-version-control](https://git-scm.com/video/what-is-version-control)
* [https://git-scm.com/video/quick-wins](https://git-scm.com/video/quick-wins)

Additional Resources:
	
* [http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade-2#/4/21](http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade-2#/4/21)

## Git, for things other than code
* Auditing system for changes on a file
* For collaboratively editing a text document
* [For drafting government web design standards!](https://github.com/18F/web-design-standards)
* [Drafting](https://github.com/twitter/innovators-patent-agreement) and [collaborating on](https://github.com/twitter/innovators-patent-agreement/issues) legal documents

## Github and Open Source
https://government.github.com/
https://government.github.com/community/

## Tour of Github.com

http://github.com/dmil/

* Your Github Page
* Social Features

## Set up SSH Keys
### Setting up the keys for GitHub

Follow these instructions. Remember, if you're using "Bash on Ubuntu on Windows" then use the "linux" instructions.
[https://help.github.com/articles/generating-an-ssh-key/](https://help.github.com/articles/generating-an-ssh-key/)

### What is SSH?

Videos:

* [What is SSH](https://www.youtube.com/watch?v=zlv9dI-9g1U)
* [Cryptography 101](https://www.youtube.com/watch?v=fNC3jCCGJ0o)
* [What is Cryptography](https://www.youtube.com/watch?v=68Pqir_moqA)

Images below sourced from [David Brumly at Carnegie Mellon University](https://www.youtube.com/watch?v=fNC3jCCGJ0o)

![](https://www.evernote.com/shard/s150/sh/ceba42f8-128c-478b-b857-2b033294a4df/f70388b235260b5a/res/6eaede67-b674-4c28-9306-5b8414d849ae/skitch.png?resizeSmall&width=832)

![](https://www.evernote.com/shard/s150/sh/a5150f27-e630-48fb-8794-a1342cfe5076/0c664f25dd396804/res/51319142-13b1-45cd-af94-1cb7177b5bda/skitch.png?resizeSmall&width=832)

![](https://www.evernote.com/shard/s150/sh/d2a42614-b368-4536-ada4-f2f641832ec9/b13ba0462deb7322/res/bb33443a-bfe6-4002-b98a-d0aa87c73bf9/skitch.png?resizeSmall&width=832)

![](https://www.evernote.com/shard/s150/sh/5614e630-0ea0-4a55-ba14-cf679593fee6/99133c73ac3eca6f/res/30c2aa9c-6fe1-4fae-b8ff-d5b631209b99/skitch.png?resizeSmall&width=832)


#### Key Terms
* **github** - a service that hosts git remote repositories, and provides a web app to interact / collaborate on them
* **remote** - another repository that can be syncronized with a remote
* **upstream** - the name for a remote read-only repository
* **origin** - the name for a remote read-and-write repository
* **clone**  - download an entire remote repository, to be used as a local repository
* **fetch**  - downloading the set of changes (commits) from a remote repository
* **pull**   - fetching changes and merging them into the current branch

## Try It (together)
1. Create a blank github repo for your `python-playground`
2. Set the remote on your local repo to this new repo on github
3. Push your repo up to github

## Try It
1. Create a [blank github repo](https://github.com/new) for your `dhrumil-simple-website` if you haven't already.
2. Set the remote on your local repo to this new repo on github
3. Push your repo up to github

## Try It (optional)
1. cd into your directory `~/Development/universe`
2. run `pwd` and `ls` to remind yourself where you are and what is there
3. intitialize a git repository in the folder

	```
	git init
	```
4. add all of the files in this folder to the staging area. The way to add all the files rather than one at a time is:
	```
	git add .
	```
5. commit this data with the commit message "create a folder structure that represents the universe"
	```
	git commit -m "create a folder structure that represents the universe"
	```
6. do a `git log` to make sure you committed properly and a `git status` to make sure there are no new changes
7. Create a [blank github repo](https://github.com/new) called "universe"
8. set your remotes (follow the instructions in the new github repository)  
9. check out your repository by refereshing the page in github

## Serving static websites from GitHub

Together we will go through how to serve up your simple website.

## Collaboration with Branches on GitHub

### Try It

1. Clone my simple website
2. Checkout a branch for yourself
	
	```
	git checkout -b dhrumils-branch
	```

3. Inside that branch, convert your name into a link to your github

	so for example instead of 
	```
	<li> Mehta, Dhrumil </li>
	```
	
	I would write
	```
	<li> <a href="http://github.com/dmil"> Mehta, Dhrumil </a> </li>
	```
4. Commit that change
5. Issue a pull request back to the `master` branch with your change.

## Forking

Draw on the board, forking vs branching

http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade-2#/4/17

### Key Terms

* **fork** - make a copy of a remote repo on github.
* **merge**  - taking two histories, merge one into the other
* **push**   - sending changes to a remote repository and merging them into the specified branch
* **pull request** - ask the upstream maintainer to pull in changes from origin.
* **merge conflict** - when two commits conflict, and thus can't be merged automatically

## Pull requests from a fork

### Open source collaboration.

https://github.com/tj/git-extras/pull/356

### Backbone forms example

Github Issue

https://github.com/powmedia/backbone-forms/issues/537

Pull Request (From a Fork)

https://github.com/powmedia/backbone-forms/pull/538

## Try It (together)

1. Find another partner, and fork their simple webpage into your github.
2. Clone your fork onto your local computer
3. Put an endorsement on their webpage as the last item on the site.

	```
	<h2> Endorsements </h2>
	
	<p> You are a really cool person. - Dhrumil</p>
	```
4. commit this endorsement and push it to your fork in github
5. issue a pull request back to that person's github repo

## Try It

Put an endorsement on someone else's site using the same method, forking and open source collaboration.

## Finally

1. Create a "github page" for yourself [https://pages.github.com/](https://pages.github.com/) - follow the instructions for a "User"
2. Chose Jekyll Theme to instantly make it look good
https://github.com/blog/2295-new-theme-chooser-for-github-pages
2. (optional) - buy a domain for yourself at [http://namecheap.com](http://namecheap.com). When we get to the "DevOps" lesson, you'll learn how to connect your new domain to either a static or dynamic webpage.
