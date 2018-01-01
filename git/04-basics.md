# Git 4: Basics

## Git

#### Components of a Git Repository

![](https://www.evernote.com/shard/s150/sh/3a1357b6-6250-432c-b5be-6bc0a895b97f/0a90b7cfc659e426/res/930e27c8-7194-484b-84f5-d411e15c2bc5/skitch.jpg?resizeSmall&width=832)

#### Key Terms
* **working directory** - the current local directory in which you are working
* **staging area** - the files that are ready to be committed (saved)
* **commit** - a saved snapshot of files (or the changes thereof)

![](https://git-scm.com/book/en/v2/images/areas.png)

1. The working directory
  - `git init` creates a git repo inside current working directory

2. The staging area
  - `git add .` adds changes from the working directory to the staging area
  - `git add <filename>` adds changes to filenames specified from the working directory to the staging area

3. The commit
  - `git commit -m "commit message"` adds changes in staging area to the repository
  - `git log` shows

**Protip**: Run `git status` after each command in the beginning because it allows you to visualize what just happaned.

## Github

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

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example: universe

1. cd into your directory `~/Development/universe`
2. run `pwd` and `ls` to remind yourself where you are and what is there
3. intitialize a git repository in the folder

	```
	git init
	```

4.  add mars.txt

	```
	git add solar_system/planets/mars.txt
	```

5. check the git status

	```
	git status
	```

6. commit

	```
	git commit -m "add mars"
	```

7. check the git status

	```
	git status
	```

8. add earth

	```
	git add solar_system/planets/earth
	```

9. commit
	
	```
	git commit -m "add earth"
	```

10. check the git status
	
	```
	git status
	```

11. check the git log
	
	```
	git log
	```

12. create a [blank github repo](https://github.com/new) called "universe" 

13. set your remotes (follow the instructions in the new github repository)  

14. push your 2 commits

	```
	git push
	```

15. check your repository online by refereshing the page in github

## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

1. Add the rest of the `planets` folder and commit it with the message "add remaining planets".
2. Add the rest of the `stars` folder and commit it with the message "add stars".
3. Push the two commits to github.

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example: assignments

1. cd into your directory `~/Development/assignments`
2. run `pwd` and `ls` to remind yourself where you are and what is there
3. intitialize a git repository in the folder

	```
	git init
	```
4. Add yesterday's homework to the staging area. Move it to a folder first.
	
	```
	mkdir day1
	mv sayhello.py day1/
	mv expensive_water.csv day1/
	mv expensive_water_summary.txt day1/
	mv description.txt day1/
	mv output.csv day1/
	mv summary.txt day1/

	git add day1
	```

5. check the git status
6. commit
7. check the git status
8. check the git log
9. create a [blank github repo](https://github.com/new) called "assignments" 
10. set your remotes (follow the instructions in the new github repository)  
11. push your commits
12. check if the code is pushed online

## Git vs Github

Git is a _distributed_ version control system (VCS). Distributed means that there is no one central server that stores all of your code- you can have redundancies (copies) of the code wherever you like. There is always one copy of the code (along with its entire history) on your local computer. Other copies of your code are each referred to as "remotes". Github.com is a *very* popular remote used for Git projects such as it is almost synonymous with Git now. There are of course other alternatives such as [BitBucket](https://bitbucket.org/) and [GitLab](https://about.gitlab.com/).
