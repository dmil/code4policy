# Command Line 4

## Downloading and manipulating data

TODO

##### `clear`
* **clear**s all output from your console
* on macOS, you can also press `Ctrl+L` to clear your console while retaining history or `Cmd-K` to clear console while deleting the history. `Ctrl+L` should work on Ubuntu as well.

##### `tar`
* example usage 1: `tar -cvf temp.tar `

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
