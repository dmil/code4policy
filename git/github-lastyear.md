# Git and Github

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
