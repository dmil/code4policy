# Git

Wikipedia 
> Git (/ɡɪt/[8]) is a version control system (VCS) for tracking changes in computer files and coordinating work on those files among multiple people. It is primarily used for source code management in software development,[9] but it can be used to keep track of changes in any set of files. As a distributed revision control system it is aimed at speed,[10] data integrity,[11] and support for distributed, non-linear workflows.[12]

Github

> Git is an open source program for tracking changes in text files.
> https://help.github.com/articles/github-glossary/

## What is Git?

Keeping track of file versions is hard.
![](http://petapixel.com/assets/uploads/2015/07/psdrevisioning.jpg)

#### So what is Git, and why does it help us?
Above all else, Git is a fast and **distributed** version control system, that allows you to efficiently handle projects large and small.

Here are some problems we face, and how git solves them:

#### Reverting to past versions

Git allows us to make save points at any time. These save points are called '**commits**'. Once a save point is made, it's permanent, and allows us to go back to that save point at any time. From there, we can see what the code looked like at that point, or even start building off that version.

#### Keeping track of what each version 'meant'

Every commit has a description (**commit message**), which allows us to describe what changes were made between the current and previous commit. This is usually a description of what features were added or what bugs were fixed.

Additionally, git supports tagging, which allows us to mark a specific commit as a specific version of our code (e.g. '2.4.5').

#### Comparing changes to past versions

It's often important to see content of the actual changes that were made. This can be useful when:

* tracking down when and how a bug was introduced
* understanding the changes a team member made so you can stay up-to-date with progress
* reviewing code as a team for correctness or quality/style

Git allows us to easily see these changes (called a **diff**) for any given commit.

#### Fearlessness in making changes

In writing code (or copy), we often want to experiment in adding a feature or refactoring (rewriting) existing code. 

Because git makes it easy to go back to a known good state, we can experiment without worrying that we'll be unable to undo the experimental work.

Note: This section was borrowed from [Al Johri's guide to Git & GitHub](https://github.com/AlJohri/DAT-DC-12/blob/master/notebooks/intro-git.ipynb)

## Some Vocabulary

* **Git** - version control software
* **Repository** - a folder containing your files and also containing a structure that helps keep track of changes in those files. When you intialize a repository, git creates a hidden folder (`.git` folder) that stores the changes to those files.
* **GitHub** - a place to host git repositories and collaborate
* **Local Repository** - the version of a git repository on your local computer
* **Remote Repository** - the version of a git repository stored somewhere else that your local repository is connected to (frequently on GitHub)
* **Commit** - the basic unit of a git repository is a commit. It is a set of changes to a file. A commit usually comes with an id as well as a **commit message** that describes the change.

Within a Repository you have

* **Untracked Changes** - files that are in your folder but that git doesn't pay attention to.
* **Staging Area** - a place where you can put files before you commit them. Once files are in the staging area, git is paying attention to them.
* **Commit Log** (aka Git History) - all of the commits (previous changes) to all of the files in your repository.

## Lets use Git!

Note that everything we are about to do is happening locally on your computer. We have not yet involved GitHub.

### Step 1: Create a new local repository on the Desktop
![](images/screenshot_1.jpg)

Note: This creates a new folder on your desktop which  contains a single file with the name `README.md`

### Step 2: Create some commits

1. Add the following to the file called `README.md`:	
	
	```
	# My Simple Website
	
	This repository contains code for my simple website.
	I am building this Simple Website as a way to learn about **Git** and **GitHub**.
	```
	and commit it with the commit message "add documentation in the README file"
	
	![](images/screenshot_4.jpg)

2. create a new file called `index.html`
	
	```
	<!DOCTYPE html>
	<html>
	<head>
  		<link rel="stylesheet" href="styles.css">
	</head>
	<body>
		<h1> My Simple Website </h1>
		<p> I'm building this website in the process of learning about github. </p>
		<script src="main.js"></script>
	</body>
	</html>
	```
	and commit it with the commit message "add website homepage"
	
3. create a new file called `styles.css`

	```
	body {
		background: teal;
	}
	```
	and commit it with the commit message "make homepage teal"
	
### Step 3: Lets pause and view the history

![](images/screenshot_3.jpg)

Right now the commit history is linear, as visualized in the network diagram below. Later when we learn about branching this won't be the case. Keep this in mind as we move forward to the next section.

![](images/branch_1.gif)

## One More Thing: Branching!

Until now our commit history has been linear. However, sometimes in projects we want to try something new without losing the stable state which our project is in. At times like these, branching is most useful. Branching is another tool that really helps you to be fearless with your changes. It creates a new paralell version of your project where you can make changes and not worry about breaking the project. Once you're confident of those changes, and have decided you'd like to add them to your main project, you can merge the paralell branch back into the master branch of your project.

Remember, we're doing this with a website right now, but you can also follow the same workflow with your data, your analysis, your code, your images, or even your copy!

![](images/branching.jpg)


### Step 4: Create a new branch called "personalize"

![](images/screenshot_6.jpg)

Now your branches tab should look like this. Note that there is a checkmark next to the "personalize" branch. That means you're now working on the "personalize" branch.

![](images/screenshot_7.jpg)

### Step 5: Make some changes to personalize the webpage in the `personalize ` branch

**Note:** as you follow the instructions in this step, make sure you're commiting your changes to the `personalize` branch. The commit button will indicate which branch you're commiting to (as shown below).
![](images/screenshot_8.jpg)



1. Change the background color to your favorite color and commit this change to the `personalize` branch. Don't forget to write a descriptive commit message describing the change.
2. Change the name of website from "Simple Website" to something like "Dhrumil's Simple Website" and commit this change to the `personalize` branch. 
3. Add an image of your choice by dropping this code into the "body" of the webpage

	```
	<img src="https://s0.wp.com/wp-content/themes/vip/espn-fivethirtyeight/assets/images/logo-fox-head-color.svg"/>
	```
	
	and commit this change to the `personalize` branch with a descriptive commit message. 

### Step 6: Lets Pause and Think about Branches

Now you have two parallel branches. `master` and `personalize`. The `master` branch contains the code for your simple website, and the `personalize` branch contains the feature where you personalize it. You have now started a non-linear workflow, and that is the beauty of git!

![](images/branch_2.gif)

You can also have multiple branches working at once. For example, here is the network diagram of an active project (chartbuilder)

https://github.com/fivethirtyeight/chartbuilder-2/network

Particularly when the workflow is collaborative, different people may be working on different branches. This is why its important to always merge master into your branch before beginning the day's work. That way you can get the latest updates from the main stable branch and make sure the latest changes in the `master` branch of the project don't conflict with any work you're trying to do.

Right now we won't worry about it too much, but basically if you're working in a branch other than `master` you probably want to be hitting the "update from default branch" button shown below pretty often.

![](images/screenshot_12.jpg)

### Step 7: Merge the `personalize` branch back into `master`

Make sure everyting is commited into  the personalize branch and the staging area is empty. This means it should say `0 changed files` as shown below. All of your commits should be in your commit history.

![](images/screenshot_9.jpg)

Then switch the branch to `master` and merge the `personalize` branch into the `master` branch.

![](images/screenshot_10.jpg)

## Recap: The Branching Workflow

1. Create a new branch
2. Switch to the new branch
3. Regularly commit changes to the new branch
4. Regularly update from `master` branch as you work
5. When you're done, switch to `master`
6. Merge the new branch into master
7. Delete the new branch



## Things we did not go over

* Merge Conflicts - if two branches you are trying to merge contain changes made to the same line of code, you will have what is called a "merge conflict". In a case like this, git will show you both changes in a file, and you will have to resolve the conflict by deciding what that file should look like before you complete the merge.
* `.gitignore` - a hidden file that contains a list of files which your git repository will ignore. For example, we keep all of our passwords in a separate file and add it to the gitignore so that they don't get accidentally added to the repository.
* `.git` folder. A Hidden folder that stores all the files that manage this git repository. It contains the git history, each commit, and all the other metadata associated with this git repository.
	
## Good rules of thumb

**DO:**

1. Commits are cheap, make them all the time!
2. Pull from GitHub regularly
3. Push to GitHub regularly
4. Create a branch for each "feature" or new discrete chunk of work that you're going to do. 
5. Keep the `master` branch clean - Don't a branch into master until you are confident that it is in its final form.
6. If you're concerned about messing up the history of a branch, create a new branch and work in there. 
7. Don't Worry! Everything is reversible. The whole point of Git is that you can go back to any point in time. You can go back to any commit on any branch at any time.

**DON'T**

1. Commit passwords to your git repository (keep those uncommited)
2. Rewrite git history

## Pushing to GitHub

### Step 8: Push the `master` branch to github

![](images/screenshot_2.jpg)

Lets view the repository on github now and explore how GitHub displays everything we have done.

![](images/screenshot_5.jpg)

One thing to take note of is that we only pushed the `master` branch to GitHub so it doesn't know about the `personalize` branch at all. Right now, the `personalize` branch exists locally on our computer, but it doesn't exist in GitHub.

## Diagram

Here is a diagram I once drew. You can ignore the text written in pen (those are terminal commands)

![](images/diagram_1.jpg)

### Step 9: Delete the `personalize` Branch locally

Finally lets delete the `personalize` branch on our local computer.

![](images/screenshot_11.jpg)

### Step 10: Rejoice, then move onto the [next section about GitHub](github.md).   