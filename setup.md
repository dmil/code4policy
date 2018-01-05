# Setup

## Mac

1. Install the Homebrew package manager from: [http://brew.sh/](http://brew.sh/)
2. In the terminal run the following command to update your package manager.

	`brew update`

3. Install the "tree" command

	`brew install tree`

4. Install git

	`brew install git`

5. Install python, and python's package manager (called pip). For mac, pip is included in the python package in homebrew.

	```
	brew install python
	```

6. Install Sublime Text, the text editor we will be using in class
	```
	brew cask install sublime-text
	```

## Ubuntu

1. In the terminal run the following command to update your package manager.

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
	
5. Install Sublime Text, the text editor we will be using in class

	```
	wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -
	echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
	sudo apt update && sudo apt install sublime-text
	```
	
## Windows

Please see instructions to boot Ubuntu on Windows ([windows.md](windows.md)). Once you've loaded and run Ubuntu, please follow the Ubuntu instructions above.
