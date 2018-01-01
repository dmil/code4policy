# Git 3: Basics

## What is SSH?

Videos:

* [What is SSH](https://www.youtube.com/watch?v=zlv9dI-9g1U)
* [Cryptography 101](https://www.youtube.com/watch?v=fNC3jCCGJ0o)
* [What is Cryptography](https://www.youtube.com/watch?v=68Pqir_moqA)

Images below sourced from [David Brumly at Carnegie Mellon University](https://www.youtube.com/watch?v=fNC3jCCGJ0o)

![](https://www.evernote.com/shard/s150/sh/ceba42f8-128c-478b-b857-2b033294a4df/f70388b235260b5a/res/6eaede67-b674-4c28-9306-5b8414d849ae/skitch.png?resizeSmall&width=832)

![](https://www.evernote.com/shard/s150/sh/a5150f27-e630-48fb-8794-a1342cfe5076/0c664f25dd396804/res/51319142-13b1-45cd-af94-1cb7177b5bda/skitch.png?resizeSmall&width=832)

![](https://www.evernote.com/shard/s150/sh/d2a42614-b368-4536-ada4-f2f641832ec9/b13ba0462deb7322/res/bb33443a-bfe6-4002-b98a-d0aa87c73bf9/skitch.png?resizeSmall&width=832)

![](https://www.evernote.com/shard/s150/sh/5614e630-0ea0-4a55-ba14-cf679593fee6/99133c73ac3eca6f/res/30c2aa9c-6fe1-4fae-b8ff-d5b631209b99/skitch.png?resizeSmall&width=832)

## Components of a Git Repository

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

## Tour of Github.com

http://github.com/dmil/

* Your Github Page
* Social Features

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

