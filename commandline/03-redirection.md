# Command Line 3

## Redirection & Piping

##### `>` Redirecting Output
* `<command> > <filename>` takes the output of `<command>` and saves it in `<filename>`
* This will overwrite the file if it already exists.

##### `>>` Redirecting Input
* `<command> >> <filename>` takes the output of `<command>` and appends it to the end of the content of `<filename>`
* This will create the file if it does not yet exist.

##### `|` Piping
* `<command 1> | <command 2>` pipes the results from `<command 1>` as input to `<command 2>`, and then the results of `<command 2>` are printed to the console

## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

Congress's Expenditures 2015

>https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q1-detail.csv
>https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q2-detail.csv
>https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q3-detail.csv
>https://raw.githubusercontent.com/AlJohri/house-expenditures/master/2015Q4-detail.csv

1. Print just the header in one of these files
2. Look at the bottom 5 lines of one of these files
3. Count the number of rows in one of these files
4. Count the number of rows in one of the files containing the word "Water"
5. Return only the congressional spending rows containing the word "Water" in one of the files and redirect the output into a file
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

## Slackcat

Lets install a new command-line tool. On macOS use `brew install slackcat`. For linux, see the bottom of this page [http://slackcat.chat/](http://slackcat.chat/) for instructions.

Configure slackcat by running this command and following the instructions in your web browser:

```
slackcat --configure
```

when you're done, the browser will display something like this (except with a real token), go ahead and run that command.

```
echo "your-token-goes-here" > ~/.slackcat
```

lets stop there and discuss what just happened

## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

1. cd into your planets directory, count the number of files by piping the output of `ls` into `wc`, then pipe the ouptut of that into slackcat and send it as a message to the person sitting next to you. You can use the --noop flag to first test it out without sending the message, then you can remove it to send the message.

	hint:

	```
	cd ~/Development/universe/solar_system/planets
	ls | wc -l | slackcat -t -s -p -c dhrumil --noop
	```

	talk to the person sitting next to you about what this is doing.

2. in the `solar_system` directory, run the `tree` command, pipe the output of that into slackcat and send it to the #r-learning-group channel on slack. Make sure to not send it a snippet, but rather as a stream. You can test this out first by slacking yourself.
