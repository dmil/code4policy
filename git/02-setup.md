# Git 2: Setup

## Install

### Mac

1. Install XCode Command Line Tools which contains git.

	```
	xcode-select --install
	```

2. Open Terminal and check if git is installed.

	```
	git --version
	```

3. If there are any issues with installing git via XCode CLT, git can also be installed via [homebrew](https://brew.sh/) using `brew install git`.

### Windows 10

1. See [windows.md](../windows.md)
2. Follow Ubuntu instructions

### Ubuntu

1. Install Git

```
sudo apt-get install git
```

## Setup

1. Configure `git` with your name and email address. Be sure to use the same email associated with your Github account.

	```
	git config --global user.name "YOUR FULL NAME"
	git config --global user.email "YOUR EMAIL ADDRESS"
	```

2. Follow these instructions for connecting to Github via SSH.

https://help.github.com/articles/connecting-to-github-with-ssh/ 

