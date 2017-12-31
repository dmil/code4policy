# Git 4: Branching

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
