# Command Line 4

## Unix

Unix (/ˈjuː.nɪks/; trademarked as UNIX) is a family of multitasking, multiuser computer operating systems that derive from the original AT&T Unix, developed starting in the 1970s at the Bell Labs research center by Ken Thompson, Dennis Ritchie, and others. - [https://en.wikipedia.org/wiki/Unix](https://en.wikipedia.org/wiki/Unix)

Many Unix-like operating systems have arisen over the years, of which Linux is the most popular, having displaced SUS-certified Unix on many server platforms since its inception in the early 1990s. - [https://en.wikipedia.org/wiki/Unix](https://en.wikipedia.org/wiki/Unix)

* [https://en.wikipedia.org/wiki/Unix](https://en.wikipedia.org/wiki/Unix)
* [https://en.wikipedia.org/wiki/Unix_philosophy](https://en.wikipedia.org/wiki/Unix_philosophy)
* [https://en.wikipedia.org/wiki/History_of_Unix](https://en.wikipedia.org/wiki/History_of_Unix)
* [http://www.howtogeek.com/182649/htg-explains-what-is-unix/](http://www.howtogeek.com/182649/htg-explains-what-is-unix/)

### Operating System Concepts

* Kernel vs Shell
* Files and Processes
	- `ps aux` to see the processes that are running
	- kernel manages the processes

	[http://www.ee.surrey.ac.uk/Teaching/Unix/unixintro.html](http://www.ee.surrey.ac.uk/Teaching/Unix/unixintro.html)

* Exploring the root directory (in case you're ever wondering what all those files in `/` are)
[https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard) [http://www.thegeekstuff.com/2010/09/linux-file-system-structure/?utm_source=tuicool](http://www.thegeekstuff.com/2010/09/linux-file-system-structure/?utm_source=tuicool)

### Environment Variables and PATH
Setting Environment Variables

```
export MY_VAR=1
```

Reading Environment Variables

```
echo $MY_VAR
```

`~/.bash_profile` is run every time you open a shell. You can store variables that you would like to persist in there.

`$PATH` is an environment variable that specifies where the executable programs are located.

* `which echo` for example, will tell you where the echo command is located, it will be within one of the folders specified in `$PATH` otherwise you would have to call it explicitly every time as `/bin/echo`

Check out all of your environment variables
`printenv | less`

* some basic ones [http://www.ee.surrey.ac.uk/Teaching/Unix/unix8.html](http://www.ee.surrey.ac.uk/Teaching/Unix/unix8.html)

### Stdin & Stdout (& Stderr)
Originally I/O happened via a physically connected system console (input via keyboard, output via monitor), but standard streams abstract this. When a command is executed via an interactive shell, the streams are typically connected to the text terminal on which the shell is running, but can be changed with redirection, e.g. via a pipeline. - [https://en.wikipedia.org/wiki/Standard_streams](https://en.wikipedia.org/wiki/Standard_streams)

![](http://www.informit.com/content/images/chap5_9780133927313/elementLinks/05fig02.jpg)

source: [http://www.informit.com/articles/article.aspx?p=2273593&seqNum=5](http://www.informit.com/articles/article.aspx?p=2273593&seqNum=5)

![](http://www.informit.com/content/images/chap5_9780133927313/elementLinks/05fig03.jpg)

Figure 5-3 By default, standard input comes from the keyboard, and standard output goes to the screen

source: [http://www.informit.com/articles/article.aspx?p=2273593&seqNum=5](http://www.informit.com/articles/article.aspx?p=2273593&seqNum=5)

### and Exit Codes
Get exit code of previous command

```
echo $?
```

Example Bash Script

```bash
#!/bin/bash

# An Invalid Command
touch /root/test 2> /dev/null

# An if Statement checking the validity of a command
if [ $? -eq 0 ]
then
  echo "Successfully created file"
else
  echo "Could not create file"
fi
```

### Permissions and `chmod`

`chmod` stands for "change mode", it is the command that lets you set permissions for a file

https://en.wikipedia.org/wiki/Chmod

https://www.cise.ufl.edu/~shray/

http://computerplumber.com/2009/01/using-the-chmod-command-effectively/

Error Codes other than 1 and 0 are more rare, but here are some examples: http://www.tldp.org/LDP/abs/html/exitcodes.html

[http://bencane.com/2014/09/02/understanding-exit-codes-and-how-to-use-them-in-bash-scripts/](http://bencane.com/2014/09/02/understanding-exit-codes-and-how-to-use-them-in-bash-scripts/)

### Try It (together)
Lets modify an environment variable in side your your `~/.bash_profile` (macOS) or `~/.bashrc` (Ubuntu).

1. First `touch ~/.bash_profile` (macOS) or `touch ~/.bashrc` (Ubuntu) in the terminal. This will create an empty file in your home folder if one doesn't already exist. If the file does exist, the touch command won't modify it's contents.

2. Then open your `~/.bash_profile` (macOS) or `~/.bashrc` (Ubuntu) file and place the following snippet at the bottom. This exports the environment variable PS1 which controls how your terminal display looks. All of the code inside this file is run every time you open a terminal.

	```
	# Define a function that returns your current git branch
	parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
	}

	# Display present working directory and git path in bash prompt with colors
	export PS1="\u \[\033[32m\]\w\[\033[33m\]\$(parse_git_branch)\[\033[00m\] $ "
	```

3. Close and reopen the terminal to see the change. Modifying the PS1 environment variable as you just did creates this nice prompt that tells you where you are as you move around directories:

![](https://www.evernote.com/shard/s150/sh/d72e8c94-7e02-4185-b098-d89be0fbbe62/67e7c7d6f27a7790/res/0ba8eb13-4413-4ee0-8f9f-f1d211f5968a/skitch.png?resizeSmall&width=832)

4. Modify PS1 within the existing shell (instead of in the bashrc/bash_profile). Notice that since we didn't add this to the bashrc/bash_profile it doesn't persist when we open a new tab.

