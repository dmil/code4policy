# Command Line 3

## Redirection & Piping

##### Redirecting output to file: `>`

```
command > filename
```

Takes the output of `command` and saves it in `filename`. This will overwrite the file if it already exists.

##### Redirecting output and appending to file: `>>`

```
command >> filename
```

Takes the output of `command` and appends it to the end of the content of `filename`. This will create the file if it does not yet exist.

##### Piping: `|`

```
command1 | command2
```

Pipes the results from `command1` as input to `command2`, and then the results of `command2` are printed to the console.

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example: redirection

1. Redirect a fact about planet mars into the mars.txt.

```
echo "Mars is red." > ~/Development/universe/solar_system/planets/mars.txt
```

2. Add another mars fact to mars.txt.

```
echo "Mars has an 687 day year." >> ~/Development/universe/solar_system/planets/mars.txt
```

3. Cat the contents of mars.txt.

```
cat ~/Development/universe/solar_system/planets/mars.txt
```

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example: piping

Count the number of characters in the string "hello world" using `wc`.

```
echo "hello world" | wc -c
```

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example: piping

Count number of **files** in the `universe` folder.

```
cd ~/Development/universe
find . -type f | wc -l
```

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example: piping and redirection

House Office Expenditure Data: https://projects.propublica.org/represent/expenditures

1. Let's start a new directory for the house expenditure data.

    ```
    cd ~/Development
    mkdir house-expenditure
    cd house-expenditure
    ```

4. Download the Q2 2017 expenditure detail data and pipe it into a file.

    ```
    curl "https://projects.propublica.org/congress/assets/staffers/2017Q2-house-disburse-detail.csv" > 2017Q2-house-disburse-detail.csv
    ```

5. Print the header (first line) of this file.

    ```
    head -n 1 2017Q2-house-disburse-detail.csv
    ```

6. Print the last 12 lines of this file.

    ```
    tail -n 12 2017Q2-house-disburse-detail.csv
    ```

7. Count the number of lines in this file.

    ```
    cat 2017Q2-house-disburse-detail.csv | wc -l
    ```

8. Count the number of rows in this file that contains the word "technology" (case insensitive)

    ```
    cat 2017Q2-house-disburse-detail.csv | grep -i technology | wc -l
    ```

9. Return only the rows containing the word "technology" and redirect the output into a file. Keep the header.
    
    ```
    head -1 2017Q2-house-disburse-detail.csv > technology.csv
    cat 2017Q2-house-disburse-detail.csv | grep -i technology >> technology.csv
    ```

## Slackcat

Lets install a new command-line tool. On macOS use `brew install slackcat`. For linux, see the bottom of this page [http://slackcat.chat/](http://slackcat.chat/) for instructions.

Configure slackcat by running this command and following the instructions in your web browser:

```
slackcat --configure
```

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example

Let's use slackchat to send a simple message to the #section-a or #section-b channel.

```
echo "hello world" | slackcat -c section-a
```

## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

Notice how the message is being sent as a snippet. Figure out how to send a normal, non-snippet, message using slackcat.

<!--
echo "hello" | slackcat -t -s -c testing
-->

## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

1. cd into your planets directory, count the number of files by piping the output of `ls` into `wc`, then pipe the ouptut of that into slackcat and send it as a message to the person sitting next to you. You can use the `--noop` flag to first test it out without sending the message, then you can remove it to send the message.

<!--
cd ~/Development/universe/solar_system/planets
ls | wc -l | slackcat -t -s -c dhrumil
-->

2. In the `universe` directory, run the `tree` command, pipe the output of that into slackcat and send it to the #section-a or #section-b channel. Make sure to not send it a snippet, but rather as a stream.

<!-- 
cd ~/Development/universe/solar_system
tree | slackcat -t -s -c dhrumil
-->
