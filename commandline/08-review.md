# Command Line 8: Review

Review of command line material.

#### General format for commands
`<command> -<options> <arguments>`

* `<command>` is the action we want the computer to take
* `<options>` (or "flags") modify the behavior of the command
* `<arguments>` are the things we want the command to act on
For Linux and Mac users, you can get view the manual for a command by typing man <command>. For Windows users, you can view the help page by typing <command> --help.

### Basic Commands
```
whoami # your username
hostname # my computer's network name
echo "Hello, World!" # print text to terminal

man <name_of_command> # "manual" page - get help on how to use any command
```
### Navigating

```
pwd # print working directory
cd <directory> # change directory
ls # list directory
```

### Files
```
cat <filepath>
touch <filepath>

mkdir <directory_path> # make directory
rmdir <directory_path> # remove directory
cp <from> <to> # copy a file or directory
mv <from> <to> # move a file or directory
```

## Try It
* Navigate to your `Development/` folder in the terminal
* Create a directory called `python-playground`
* Create a file inside `python-playground` called `README.md`. The file should look like this
	
	```
	# Python Playground
	
	This is my python-playground, a place where I keep some simple python scripts as I learn python.
	
	```

* Create a new file called `hello.py`
* Write a python program that prints "Hello, World!" inside that file. It should look like this:

	```
	print "Hello, World!"
	```

* Run the file from the command line as follows

	```
	python hello.py
	```
	
This should print "Hello, World!" to the terminal
