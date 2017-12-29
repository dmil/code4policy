# Unix

Unix (/ˈjuː.nɪks/; trademarked as UNIX) is a family of multitasking, multiuser computer operating systems that derive from the original AT&T Unix, developed starting in the 1970s at the Bell Labs research center by Ken Thompson, Dennis Ritchie, and others. - [https://en.wikipedia.org/wiki/Unix](https://en.wikipedia.org/wiki/Unix)

Many Unix-like operating systems have arisen over the years, of which Linux is the most popular, having displaced SUS-certified Unix on many server platforms since its inception in the early 1990s. - [https://en.wikipedia.org/wiki/Unix](https://en.wikipedia.org/wiki/Unix)

* [https://en.wikipedia.org/wiki/Unix](https://en.wikipedia.org/wiki/Unix)
* [https://en.wikipedia.org/wiki/Unix_philosophy](https://en.wikipedia.org/wiki/Unix_philosophy)
* [https://en.wikipedia.org/wiki/History_of_Unix](https://en.wikipedia.org/wiki/History_of_Unix)
* [http://www.howtogeek.com/182649/htg-explains-what-is-unix/](http://www.howtogeek.com/182649/htg-explains-what-is-unix/)

# Command Line
#### What is the command line?
The Command Line Interface (CLI) is a way of interacting with your computer using text-based commands. This is different from the way most people interact with their computers, using their mouse and a Graphical User Interface (GUI).

#### Why should I use it?
Once you become comfortable with the basics, it can be a more powerful way to use your computer. You're able to do many things more quickly and programatically.

#### General format for commands
`<command> -<options> <arguments>`

* `<command>` is the action we want the computer to take
* `<options>` (or "flags") modify the behavior of the command
* `<arguments>` are the things we want the command to act on
For Linux and Mac users, you can get view the manual for a command by typing man <command>. For Windows users, you can view the help page by typing <command> --help.

#### File paths
A **relative file path** specifies the path to a file, taking into account your current working directory. For example, if you were to give someone "relative" directions to your house, you would give them directions from their current location (the relative path from where they are to where you are).

An **absolute file path** specifies the complete path to a file, ignoring your current working directory. For example, if you were to give someone "absolute" directions to your house, you would start by telling them to be on earth, then go to your continent, then go to your country, then go to your region, etc.


## Basic Commands

### Intro
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

### Parts of a Command
[http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade-2#/2/3](http://slides.com/dhrumilmehta/how-to-tell-a-story-with-data-tools-of-the-trade-2#/2/3)

### Basic commands

##### `pwd`
* **p**rints **w**orking **d**irectory (the directory you are currently in)

##### `ls`
* **l**i**s**ts files and subdirectories in your working directory
* `ls -a` lists **a**ll files, including hidden files
* `ls -l` lists the files in a **l**ong format with extra information (permissions, size, last modified date, etc.)
* `ls *` also lists the contents of subdirectories (one level deep) in your working directory
* `ls <path>` lists files in a specific directory (without changing your working directory)

##### `clear`
* **clear**s all output from your console

##### `cd`
* `cd <path>` **c**hanges **d**irectory to the path you specify, which can be a relative path or an absolute path
* `cd ..` moves you "up" one directory (to the parent directory)
* `cd` moves you to your "home" directory

##### `mkdir`
* `mkdir <dirname>` **m**a**k**es a new **dir**ectory called `<dirname>`

##### `touch`
* `touch <filename>` creates an empty file called `<filename>`
* This is useful for creating empty files to be edited at a later time.

##### `rm -i`
* `rm <filename>` **r**e**m**oves (deletes) a file permanently
* `rm -i <filename>` removes files in **i**nteractive mode, in which you are prompted to confirm that you really want to delete the file. It's best to always use `rm -i`.
* `rm -ir <dirname>` removes a directory and **r**ecursively deletes all of its contents

##### `mv`
* `mv <filename> <new path>` **m**o**v**es a file from its current location to `<new path>`
* `mv <filename> <new filename>` renames a file without changing its location

##### `cp`
* `cp <filename> <new path>` **c**o**p**ies a file from its current location to `<new path>`, leaving the original file unchanged
* `cp <filename> <new filename>` copies a file without changing its location


## Try It

Take some time to cd around and explore your filesystem. See what is at the root, see if you can find some of the files you use daily.

## Try It
In your home directory, make a folder called `Development`. This is where we will keep all of the code for the class.

1. In the `Development` folder, create a new folder called `universe` and create the following structure of files and folders.

	```
		solar_system/
			planets/
				mercury.txt
				venus.txt
				earth/
					continents/
						africa.txt
						asia.txt
						australia.txt
						europe.txt
						north_america/
							countries/
								united_states.txt
								canada.txt
								mexico.txt
						south_america.txt
						antarctica.txt
				mars.txt
				asteroid_belt.txt
				jupiter.txt
				saturn.txt
				uranus.txt
				neptune.txt
				pluto.txt
			stars/
				sun.txt
	```

2. Delete asteroid belt, since that isn't a planet.

3. Move pluto to a folder called "other"

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

## More Commands
```
head
tail
cat
less
wc
find
grep
```
##### `head`
* `head <filename>` prints the **head** (the first 10 lines) of the file
* `head -n20 <filename>` prints the first 20 lines of the file
* This is useful for previewing the contents of a large file without opening it.

##### `tail`
* `tail <filename>` prints the **tail** (the last 10 lines) of the file

##### `cat`
* `cat <filename>` prints the entire file

##### `less`
* `less <filename>` allows you to page or scroll through the file
* Hit the spacebar to go down a page, use the arrow keys to scroll up and down, and hit `q` to exit.

##### `wc`
* `wc <filename>` returns the **c**ount of lines, **w**ords, and characters in a file
* `wc -l <filename>` only counts lines, `wc -w <filename>` only counts words, and `wc -c <filename>` only counts characters
* A "word" is defined as any set of characters delimited by a space.

##### `find`
* `find <path> -name <name>` will recursively search the specified path (and its subdirectories) and **find** files and directories with a given `<name>`
    * Use `.` for the `<path>` to refer to the working directory.
* For the `<name>`, you can search for an exact match, or use wildcard characters to search for a partial match:
    * `*` specifies any number of any characters, such as `find . -name *.py` or `find . -name *data*.*`
    * `?` specifies one character, such as `find . -name ??_*.*`

##### `grep`
* `grep <pattern> <filename>` searches a file for a **r**egular **e**xpression **p**attern and prints the matching lines
    * The pattern should be in quotation marks to allow for multiple words.
    * The pattern is case-sensitive by default, but you can use the `-i` option to **i**gnore case.
    * You can use wildcards in the filename to search multiple files, but it only searches the working directory (not subdirectories).
* `grep -r <pattern> <path>` does a **r**ecursive search of the path (checks subdirectories) for matches within files
    * Use `.` for the `<path>` to refer to the working directory.
* `grep <pattern>` does a **g**lobal search (of your entire computer) for matches
    * Hit `Ctrl + c` if you want to cancel the search.
* Much more complex string-matching patterns can be used (which we will cover in a future class).

## Try It

1. `cd` into a folder with some files in it
2. Count the number of files by piping the output of `ls` into `wc` with the correct flags
3. search for all files with a particular extension using grep (for example `*.txt`)

## Try It
1. Open a web browser
2. Use `ps aux` to see all processes
3. Grep for the name of your web browser to see how much memory it is using up. To see the column headers, you can pipe the processes into `head`, to filter the data use `grep`

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

## Redirection & Piping

##### `>` Redirecting Output
* `<command> > <filename>` takes the output of `<command>` and saves it in `<filename>`
* This will overwrite the file if it already exists.


##### `>>` Redirecting Input
* `<command> >> <filename>` takes the output of `<command>` and appends it to `<filename>`
* This will create the file if it does not yet exist.


##### `|` Piping
* `<command 1> | <command 2>` pipes the results from `<command 1>` into `<command 2>`, and then the results of `<command 2>` are printed to the console

## Try It

Congress's Expenditures 2015 Q4
> http://assets.sunlightfoundation.com.s3.amazonaws.com/expenditures/house/2015Q4-detail.csv

Mirror for 2015 data only

>https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q1-detail.csv
>https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q2-detail.csv
>https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q3-detail.csv
>https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q4-detail.csv

1. Find the headers in one of these files
2. Look at the bottom of the file
3. Count the number of rows in the file
4. Count the number of rows in the file containing the word "Water"
5. Return only the congressional spending rows containing the word "Water" and redirect the output into a file
6. Select an office or a member of congress. Grab all 4 quarters of 2015 spending for that person and combine them into one file.

### Bonus
Bonus points if you can do it all without creating four files. (Creating only one file)

Super duper bonus points if you can do it all in one line.

### Solutions

Create a new folder called `congress` and download the data:

```
mkdir ~/Development/congress
cd ~/Development/congress
curl https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q1-detail.csv > 2015Q1-detail.csv
curl https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q2-detail.csv > 2015Q2-detail.csv
curl https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q3-detail.csv > 2015Q3-detail.csv
curl https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q4-detail.csv > 2015Q4-detail.csv
```

1. Find the headers in one of these files

	```
	head -n1 2015Q1-detail.csv
	```

2. Look at the bottom of the file

	```
	tail 2015Q1-detail.csv
	```

3. Count the number of rows in the file

	```
	2015Q1-detail.csv | wc -l
	```

4. Count the number of rows in the file containing the word "Water"

	```
	cat 2015Q1-detail.csv | grep "WATER" | wc -l
	```

5. Return only the congressional spending rows containing the word "Water" and redirect the output into a file

	```
	cat 2015Q1-detail.csv | grep "WATER" > water.csv
	```

6. Select an office or a member of congress. Grab all 4 quarters of 2015 spending for that person and combine them into one file.

	```
	cat 2015Q1-detail.csv 2015Q2-detail.csv 2015Q3-detail.csv 2015Q4-detail.csv | grep "PAUL RYAN" > paulryan.csv
	```

Bonus

```
curl https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q1-detail.csv >> 2015spending.csv
curl https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q2-detail.csv >> 2015spending.csv
curl https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q3-detail.csv >> 2015spending.csv
curl https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q4-detail.csv >> 2015spending.csv
```

Notice that use of `>>` allows us to keep appending to the same file.


Super Duper Bonus

```
curl https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q{1,2,3,4}}-detail.csv > 2015spending.csv
```

Some more advance usage of curl, downloads from all URLs matching the pattern.

## CSVKit, Sed, Awk, Data Manipulation

For the future, there is CSVKit: [https://csvkit.readthedocs.io/en/1.0.1/](https://csvkit.readthedocs.io/en/1.0.1/)
- This program is its both a command line interface (CLI) and a python package. It helps parse CSVs cleanly.

```
in2csv roster.xlsx | csvcut -c 5 | tail -n +2 | awk '{gsub("\"", "")}1' | cut -d'|' -f 1 | sed 's/^[ \t]*//;s/[ \t]*$//' | sort | uniq -c
```

```
csvstat roster.csv
```

```
csvstat 2015Q2-detail.csv
cat 2015Q2-detail.csv | grep "BIOGUIDE\|,HON" | csvstat
cat 2015Q2-detail.csv | grep "BIOGUIDE\|,HON" | grep 1,885
cat 2015Q2-detail.csv | grep "BIOGUIDE\|,HON" | grep WATER | csvstat
```

Why would you ever do this?

* Reproducability
* Portability
* Transparancy
* To be obnioxious
* Simplicity and ease of use. Once you're comfortable with this, its easier sometimes to use the command line for simple cleaning operations before piping to file and starting the real analysis.

## Try It

Spend some time playing around with these tools, come up with an interesting line of inquiry about congressional speding in 2015.

## Editing Files
### Vim

### Nano

### Emacs

### less

[Vim vs. Emacs](https://en.wikipedia.org/wiki/Editor_war)

## Dangers
The terminal is a powerful tool (especially in linux)
[http://www.howtogeek.com/125157/8-deadly-commands-you-should-never-run-on-linux/](http://www.howtogeek.com/125157/8-deadly-commands-you-should-never-run-on-linux/)

## Credits
some information sourced from: [https://github.com/AlJohri/DAT-DC-12/blob/master/notebooks/intro-command-line.ipynb](https://github.com/AlJohri/DAT-DC-12/blob/master/notebooks/intro-command-line.ipynb)

## More Resources

Man/Help pages for commands

* http://conqueringthecommandline.com/book/basics
* http://cli.learncodethehardway.org/book/

Command Line Power Tools

- Ag (The Silver Searcher) - Manipulate text in the command line
https://github.com/ggreer/the_silver_searcher
http://conqueringthecommandline.com/book/ack_ag
- Sed and Awk
	- http://www.grymoire.com/Unix/Sed.html
	- http://www.hcs.harvard.edu/~dholland/computers/awk.html
- ​CsvKit - parse CSV data in the command line, transfer to sql database, JSON, and so much more.
	- ​https://csvkit.readthedocs.org/en/0.9.1/install.html​
	- https://source.opennews.org/en-US/articles/eleven-awesome-things-you-can-do-csvkit/
- UnderscoreCLI - Manipulate json data in the command line
https://github.com/ddopson/underscore-cli

* Unix Books [http://www.ee.surrey.ac.uk/Teaching/Unix/books-uk.html](http://www.ee.surrey.ac.uk/Teaching/Unix/books-uk.html)

* Command line data science: [http://datascienceatthecommandline.com](http://datascienceatthecommandline.com/)

