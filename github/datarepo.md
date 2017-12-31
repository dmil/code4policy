## Our Data Repo Setup

The private and public data repos are now both forks of the same repository. Below are instructions on setup and adding new data.

This means I have on my computer one repository locally. However it has two **remote repositories** on GitHub, one private and one public. Each remote repository has its own branches.

![](images/datarepodiagram.jpg)

## Process for Publishing Data

1. Writers submit data via email
2. Create a `new-dataset` branch on the `private-data` remote repository and send that in the email where data is filed.
3. Discuss the data and README in the email thread with the author of the peice and the editors, make edits as needed inside the `new-dataset` branch.Then issue a pull request back to the `master` branch of `private-data`.
4. Review and merge pull request back into the `master` branch of `private-data` and delete the branch.
5. Review the [private repo](https://github.com/fivethirtyeight/private-data). If everything looks correct, pull the master branch of the `fivethirtyeight/private-data` **remote repository** to my local computer and then push it up to the [public](https://github.com/fivethirtyeight/data) `fivethirtyeight/data`.
		
**Note:** In this setup, the `private-data` repo will have many branches, however we only ever push the `master` branch to the public `data` repository.

Additionally, the private repo is always ahead of the public repo. Never add directly to the public repo (or if you do make sure to push that change back to the private repo).

