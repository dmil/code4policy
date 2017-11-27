# Setup

## Mac

1. Install the Homebrew package manager from: [http://brew.sh/](http://brew.sh/)
2. In the terminal run the following command to update your package manager. 

	`brew update`

2. Install the "tree" command

	`brew install tree`
	
3. Discuss what this is doing with a fellow mac user, then do it
	
	First run this in the terminal: ```touch ~/.bash_profile```
	
	Then open your `~/.bash_profile` file and place the following snippet at the bottom
	
	```
	PS1='\[\033[01;32m\]\h\[\033[01;34m\] \w #\[\033[00m\] '
	```
	
	This exports the environment variable `PS1` which controls how your terminal display looks. All of the code inside your `~/.bash_profile` file is run every time you open a terminal.
	
	Modifying the `PS1` environment variable as you just did creates this nice prompt that tells you where you are as you move around directories:
	
	![](https://www.evernote.com/shard/s150/sh/3d3a8926-0860-4ccc-9577-1d75647e775c/eb541349138e8ca7/res/9fbf1858-d65c-46bc-a655-b0e2543e5154/skitch.png?resizeSmall&width=832)
	
4. Install git

	`brew install git`

5. Install python, and python's package manager (called pip). For mac, pip is included in the python package in homebrew.

	```
	brew install python
	```

## Ubuntu

2. In the terminal run the following command to update your package manager.

	`sudo apt-get update`

2. Install the "tree" command

	`sudo apt-get install tree`

3. Install git

	`sudo apt-get install  git`
	
4. Install python, and python's package manager (called pip)

	```
	sudo apt-get install python
	sudo apt-get install python-pip
	```

## Windows

If you're on windows, please boot in ubuntu inside a virtual box and then follow the ubuntu instructions.

### Setting up a virtual box
* Download [Virtualbox](https://www.virtualbox.org/wiki/Downloads)
* Download the [Ubuntu ISO](https://www.ubuntu.com/download/desktop)
* Create a new "Ubuntu" virtual box, when you first open the virtual box, a prompt will pop up

	![](https://www.evernote.com/shard/s150/sh/e26bb014-0fd8-4bb2-93f5-18f55d5169ec/83abe0b21d90e39a/res/cbc6682a-8f44-43de-abe8-6ed8da6a7fee/skitch.png?resizeSmall&width=832)


* Select the folder icon and find your ubuntu ISO and hit "start"
* Follow the on-screen instructions to "install ubuntu"
* Jump up to the "Ubuntu" section of this document and follow those rules inside the virtual box.