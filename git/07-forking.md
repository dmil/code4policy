# Git 7: Forking

![](https://s3.amazonaws.com/media-p.slid.es/uploads/489063/images/2498675/pasted-from-clipboard.png)

Draw on the board, forking vs branching.

## Branching vs Forking

* **Branching** is a feature of Git, you've used branching already
* **Forking** is a feature of GitHub
	* A fork is a personal copy of another user's repository that lives on your account. Forks allow you to freely make changes to a project without affecting the original. Forks remain attached to the original, allowing you to submit a pull request to the original's author to update with your changes. You can also keep your fork up to date by pulling in updates from the original. - [GitHub Glossary](https://help.github.com/articles/github-glossary/)
	*  When you fork a repository, you get all of the branches the other person posted on GitHub
	*  Pull requests however, don't acknowledge forks since they are a feature of GitHub and not Git

Good example repository that makes use of issues and pull requests: https://github.com/openelections/

## Key Terms

* **fork** - make a copy of a remote repo on github.
* **merge** - taking two histories, merge one into the other
* **push**  - sending changes to a remote repository and merging them into the specified branch
* **pull request** - ask the upstream maintainer to pull in changes from origin.
* **merge conflict** - when two commits conflict, and thus can't be merged automatically

<!--
example
fork https://github.com/dmil/simple-website
and submit PRs

show openelections

try it
fork each other

try it
come to my website and then leave an issue
-->

1. Step 1: Fork my repository [`dmil/simple-website`](https://github.com/dmil/simple-website).

This

https://github.com/`dmil`/simple-website

will fork to 

https://github.com/`your-username`/mozilla-website

![](images/screenshot_28.jpg)

If you want to see the site rendered in your GitHub pages, go to Settings > GitHub Pages and select the "master" branch to render the page from.

### Step 2: Make ONE change!

**Make Changes on GitHub**

The short way to do this is to just make the changes directly in the GitHub web editor in the `your-username/mozilla-website` repository's `master` branch. 

**Optional (make changes locally instead)**

If you want to get some more practice with GitHub though, you can clone the repository locally onto your Desktop. Make the changes, commit them, and then push the new commits from your **local** `master` branch to your **remote** `master` branch in GitHub.

![](images/screenshot_29.jpg)

### Step 3: Issue a pull request back to my repository

Issue a pull request back from the `master` branch of the `your-username/mozilla-website` to the `master` branch of `dmil/mozilla-website`

![](images/screenshot_30.jpg)

### Step 4: Wait for me to approve the pull request and see the change on my site.

compare

http://dmil.github.io/mozilla-website

with

http://`your-username`.github.io/mozilla-website

### Step 5: Woohoo! You just collaborated open-source.

Open source collaboration is great for:

* Not duplicating work
* Collaborating accross organizations
* Interacting with people - sometimes making an issue or a pull request can lead to friendship (or sources or collaborators)
* Reader feedback
* [Collective debugging](https://github.com/themarshallproject/klaxon/issues/107), finding critical [errors](https://github.com/fivethirtyeight/data/pull/54) faster (often also leads to better security and better data quality).
* [Building upon](https://twitter.com/ascheink/status/783394500710457344) someone else's project
* [Feuding](https://github.com/jashkenas/underscore/issues/2182)
* [Philosophical](https://www.gnu.org/philosophy/shouldbefree.en.html) [Reasons](https://www.gnu.org/philosophy/open-source-misses-the-point.en.html)
* Being [nerdy](https://github.com/fivethirtyeight/data/pull/63)?

More Links

- https://government.github.com/
- https://government.github.com/community/





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
