# Command Line 4

## Unix

Unix (/ˈjuː.nɪks/; trademarked as UNIX) is a family of multitasking, multiuser computer operating systems that derive from the original AT&T Unix, developed starting in the 1970s at the Bell Labs research center by Ken Thompson, Dennis Ritchie, and others. - [https://en.wikipedia.org/wiki/Unix](https://en.wikipedia.org/wiki/Unix)

Many Unix-like operating systems have arisen over the years, of which Linux is the most popular, having displaced SUS-certified Unix on many server platforms since its inception in the early 1990s. - [https://en.wikipedia.org/wiki/Unix](https://en.wikipedia.org/wiki/Unix)

* [https://en.wikipedia.org/wiki/Unix](https://en.wikipedia.org/wiki/Unix)
* [https://en.wikipedia.org/wiki/Unix_philosophy](https://en.wikipedia.org/wiki/Unix_philosophy)
* [https://en.wikipedia.org/wiki/History_of_Unix](https://en.wikipedia.org/wiki/History_of_Unix)
* [http://www.howtogeek.com/182649/htg-explains-what-is-unix/](http://www.howtogeek.com/182649/htg-explains-what-is-unix/)


## Operating System Concepts

* Kernel vs Shell
* Files and Processes
	- `ps aux` to see the processes that are running
	- kernel manages the processes

	[http://www.ee.surrey.ac.uk/Teaching/Unix/unixintro.html](http://www.ee.surrey.ac.uk/Teaching/Unix/unixintro.html)

* Exploring the root directory (in case you're ever wondering what all those files in `/` are)
[https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard](https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard) [http://www.thegeekstuff.com/2010/09/linux-file-system-structure/?utm_source=tuicool](http://www.thegeekstuff.com/2010/09/linux-file-system-structure/?utm_source=tuicool)

## Environment Variables and PATH
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

## Permissions and `chmod`

`chmod` stands for "change mode", it is the command that lets you set permissions for a file

https://en.wikipedia.org/wiki/Chmod

https://www.cise.ufl.edu/~shray/

http://computerplumber.com/2009/01/using-the-chmod-command-effectively/



## Stdin & Stdout (& Stderr)
[https://en.wikipedia.org/wiki/Standard_streams](https://en.wikipedia.org/wiki/Standard_streams)

### and Exit Codes
Get exit code of previous command

```
echo $?
```

Example Bash Script

```
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

Error Codes other than 1 and 0 are more rare, but here are some examples: http://www.tldp.org/LDP/abs/html/exitcodes.html

[http://bencane.com/2014/09/02/understanding-exit-codes-and-how-to-use-them-in-bash-scripts/](http://bencane.com/2014/09/02/understanding-exit-codes-and-how-to-use-them-in-bash-scripts/)

### Try It
1. Open a web browser
2. Use `ps aux` to see all processes
3. Grep for the name of your web browser to see how much memory it is using up. To see the column headers, you can pipe the processes into `head`, to filter the data use `grep`

