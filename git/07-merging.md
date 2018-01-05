# Git 7: Merge Conflicts

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example

1. 	`cd` into the universe folder and open the directory in sublime as well.

	```
	cd ~/Development/universe
	subl ~/Development/universe
	```

2. Run `git status` to make sure the repository is "clean" (i.e. there are no "untracked files", "unstaged changes", or "staged changes").

3. Run `git pull` to ensure you have the latest changes in the repository.

4. Create a branch called `blue-universe`.
	1. Modify the facts in `mars.txt` to add a new line "Mars is blue". Use `git diff` to ensure that you only modified that one line and nothing else.
	2. Commit this change to the branch.
	3. Push the branch.
	4. Create a pull request but do not merge it.

5. Check out the master branch and then create a new branch called `red-universe`.
	1. Modify the facts in `mars.txt` to add a new line "Mars is red". Use `git diff` to ensure that you only modified that one line and nothing else.
	2. Commit this change to the branch.
	3. Push the branch.
	4. Create a pull request but do not merge it.

6. Merge the `red-universe` pull request. Try to merge the `blue-universe` pull request and it should say the branch cannot be automatically merged. This mean's there is a merge conflict.

7. Create a branch called `the-upside-down`.
	1. Edit `united_states.txt` with the text: "Hawkins, Indiana: The Demogorgon was here."
	2. Commit this change to the branch.
	3. Push the branch.
	4. Do not merge this branch back in as [the upside down](http://strangerthings.wikia.com/wiki/The_Upside_Down) runs parallel to the real `universe`...

## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Example

1. Make sure the repository is clean and you are in the master branch.

2. Create a branch called `alternative-facts`.
 
3. Go back to (checkout) the `master` branch.
	1. Add two facts to `mars.txt`: "Mars has polar ice caps." and "Mars is a little more than half the size of earth."
	2. Commit these changes to `master`.

4. Checkout the `alternative-facts` branch.
	1. Add two facts to `mars.txt`. "Mars is gaseous." and "Mars is double the size of earth."
	2. Commit these changes to `alternative-facts`.
	3. Create a pull request using `alternative-facts`.

5. Attempt to merge the pull request and try to resolve the merge conflicts.


## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

1. Get into your teams and come up with a team name and a product owner if you haven't already done so.

2. Have the product owner create a **blank** repository (no README) under their account named `our-website`. 

3. The product owner should:
	1. add the remaining team members as collaborators to the repo. This is done under the repo settings
	2. enable github pages on this repo with the `master` branch as the source

5. Everyone should clone the empty repository.

5. The product owner should create an `index.html` and a an empty folder called `our-team`. Commit and push this change directly to the `master` branch. Here is a sample `index.html`:
	
	```
	<!DOCTYPE html>
	<html>
	<body>

	<h1>Our Website</h1>

	</body>
	</html>
	```

6. Everyone else should pull these changes.

7. All team members, should create branches titled `add-member-<name>`.

	For example a team might have `add-member-jessica`, `add-member-dhrumil`, `add-member-john`, etc.

8. In this branch, each team member should create a file that is titled `our-team/<name>.html`. For example, I would create `our-team/dhrumil.html`. Add some basic information about yourself to this page. Be sure to only create this one file - there should be no other changes to the repository. It's important to keep your code changes isolated when working with git to avoid unecessary merge conflicts.
	1. Commit this change to the feature branch, push it, and create a pull request.
	2. Product Lead should review and merge all of the PRs. There should be no conflicts.

9. The product owner should link each of these member pages into the `index.html`.
