# Command Line 2 

## Navigating File Structure

### Intro

Just like in Finder (macOS), Explorer (Windows), or Nautilus (Ubuntu), you can navigate through the folders in your computer using the command line. Each session in your terminal starts in a particular directory and you can traverse the directory structure starting from there. You can use `pwd` (print working directory) to find the current working directory.

```
pwd
```

This command gives the *absolute* path to your current working directory.

### File paths

A **relative path** specifies the path to a file or folder, taking into account your current working directory. For example, if you were to give someone "relative" directions to your house, you would give them directions from their current location (the relative path from where they are to where you are).

A few directories have special symbols:
- `.` current directory
- `..` parent directory
- `~` home directory

```
.
├── Applications
└── Users
    └── mehtad
        ├── Desktop
        ├── Development
        ├── Documents
        ├── Downloads
        ├── Movies
        ├── Music
        └── Pictures
 
```

In the example above, if I was in the Downloads folder and I wanted the relative path to the Documents folder, that would be `../Documents`.

**Pop Quiz**: If you are in the Downloads folder, what folder is:

- `../`
- `../../`
- `../../mehtad/`
- `../../mehtad/./`
- `../../mehtad/./Downloads/../Documents`

An **absolute path** specifies the complete path to a file or folder, ignoring your current working directory. For example, if you were to give someone "absolute" directions to your house, you would start by telling them to be on earth, then go to your continent, then go to your country, then go to your region, etc. The root of the filesystem is referred to as `/`.

In the same example above, the absolute path to the Documents folder would be `/Users/mehtad/Documents`.

### Navigating

#### `cd`

To navigate to different directories within your filesystem, you can use the `cd` (**c**hange **d**irectory) command. `cd` takes one positional argument, the absolute or relative path to the destination directory.

```
cd <target_directory>
```

`cd ..` will move you "up" one directory (to the parent directory) and `cd ~` will move you back to the "home" directory.

#### `ls`

In order to **l**i**s**t the contents of the current directory you can use `ls`. 

* `ls -a` lists **a**ll files, including hidden files
* `ls -l` lists the files in a **l**ong format with extra information (permissions, size, last modified date, etc.)
* `ls *` also lists the contents of subdirectories (one level deep) in your working directory
* `ls <path>` lists files in a specific directory (without changing your working directory)

#### `cat`

You can view the contents of an individual file by using `cat`. `cat` will print contents of a file to the screen.

* usage: `cat <filename>`

### Manipulating

The command line not only lets you navigate the file system but also manipulate it by creating new files (`touch`), creating directories (`mkdir`), deleting files and directories (`rm -i`, `rm -ir`), copying files and directories (`cp -v`, `cp -vR`), move/rename files and directories (`mv`), and more...

#### `touch`
* `touch <filename>` creates an empty file called `<filename>`
* This is useful for creating empty files to be edited at a later time.

#### `mkdir`
* `mkdir <dirname>` **m**a**k**es a new **dir**ectory called `<dirname>`

#### `rm -i`
* `rm -i <filename>` removes files in **i**nteractive mode, in which you are prompted to confirm that you really want to delete the file. It's best to always use `rm -i`
* `rm -ir <dirname>` removes a directory and **r**ecursively deletes all of its contents

#### `cp -v`
* `cp -v <filename> <new_path>` **c**o**p**ies a *file* from its current location to `<newpath>`, leaving the original file unchanged. The `-v` is for verbose mode
* `cp -vR <dirname> <new_path>?` copies a *directory* **r**ecursively to `<newpath>`

#### `mv`
* `mv <filename> <new path>` **m**o**v**es a file from its current location to `<new path>`
* `mv <filename> <new filename>` renames a file without changing its location

### Try It

Take some time to cd around and explore your filesystem. See what is at the root, see if you can find some of the files you use daily.

### Try It

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

## Redirection and Piping


