# Git 7: Merge Conflicts

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example

1. `cd ~/Development/universe`.

2. Run `git status` to make sure the repository is "clean" (i.e. there are no "untracked files", "unstaged changes", or "staged changes").

3. Run `git pull` to ensure you have the latest changes in the repository.

4. Create a branch called `blue-universe`.
	1. Modify the facts in `mars.txt` to add a new line "Mars is blue". Use `git diff` to ensure that you only modifeid that one line and nothing else.
	2. Commit this change to the branch.
	3. Push the branch.
	4. Create a pull request but do not merge it.

5. Check out the master branch and then create a new branch called `red-universe`.
	1. Modify the facts in `mars.txt` to add a new line "Mars is red". Use `git diff` to ensure that you only modifeid that one line and nothing else.
	2. Commit this change to the branch.
	3. Push the branch.
	4. Create a pull request but do not merge it.

6. Merge the `red-universe` pull request. Try to merge the `blue-universe` pull request and it should say the branch cannot be automatically merged. This mean's there is a merge conflict.

7. Create a branch called `the-upside-down`.
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
