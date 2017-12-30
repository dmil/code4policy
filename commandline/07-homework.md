# Command Line 7

## Homework

The following program reads data from STDIN that is in a csv format and filters rows where someone has made a purchase for water that is over $1000. It writes this data back to STDOUT.

```python
#!/usr/bin/env python2
import csv
import sys

# read data from STDIN and split on each newline
data = sys.stdin.read().splitlines()

# use python's csv library to create a csv reader and a writer
reader = csv.DictReader(data)
writer = csv.DictWriter(sys.stdout, fieldnames=reader.fieldnames)

# write the header (first line of the csv)
writer.writeheader()

# loop through the rows in the original csv
for row in reader:
	# filter rows
    if row['PURPOSE'] == 'WATER' and float(row['AMOUNT']) > 1000:
    	# write rows that match above filter
        writer.writerow(row)
```

### Part 1

1. cd into your assignments directory
2. save this program as `filter.py`
3. make the script executable (hint: chmod)
4. `curl` the 2017 quarter 1 expenditure file from https://projects.propublica.org/congress/assets/staffers/2017Q1-house-disburse-detail.csv and pipe it into `./filter.py`
5. redirect the output into a file `expensive_water.csv`

### Part 2

1. Modify the above program to get another subset of the data that is interesting to you.
2. Redirect the output to a file called `output.csv`.
3. Write a short description. It can be as short as two sentences.
4. Put it in a file called `description.txt`.
5. Slackcat the contents of `descrption.txt` as **NOT** a snippet to the `#assignments` slack channel:

	```
	cat description.txt | slackcat -s -c assignments
	```
6. Pipe `output.csv` into `csvstat` and redirect that into a file called `summary.txt`.
7. You will learn how to submit summary.txt and output.csv via github tomorrow.
