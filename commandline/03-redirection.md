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
