# Data 3: Python 1

While command line tools allows for several quick out of the box data transformations, we resort to Python to doing anything a bit more custom.

## Text Files

### Opening a text file

This snippet opens a file in read only mode (default), loads the entire contents of the file as a string in `full_text` and prints it out.

```python
with open('myfile.txt') as f:
    full_text = f.read()

print full_text
```

`with open(...) as f` is called a "context manager". After opening a file, we generally want to close it to prevent memory leaks. The context manager will do this for us.

### Writing a text file

This snippet opens a file in write mode and writes the word 'hello' with a newline character at the end.

```python
with open('testwrite.txt', 'w') as f:
    f.write('hello')
    f.write('\n')
```

## CSV/TSV

## Opening a CSV file

This snippet opens a file in read only mode and uses the csv module to instantiate a [`csv.DictReader`](https://docs.python.org/2/library/csv.html#csv.DictReader). This object will parse the CSV and return a dict for each record where the keys of the dict are the header of the csv.

```python
import csv

with open('myfile.csv') as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(row)
```

If we wanted to get all of the rows into a single variable, we can run `rows = list(reader)`. `reader` is what is referred to as an `iterable` in python. Running the `list` function exhausts the iterator and just gives us the entire file as a plain old list.

```python
import csv

with open('myfile.csv') as f:
    reader = csv.DictReader(f)
    rows = list(reader)

for row in rows:
    print(row)
```

Note that since we have loaded the entire CSV into memory in the variable `rows` we can now put our `for` loop outside of the context manager since we no longer need access to the file, `f`.

You can also open a TSV file in the same manner by passing the `delimeter` argument to `csv.DictReader`.

```python
import csv

with open('myfile.csv') as f:
    reader = csv.DictReader(f, delimeter='\t')
    rows = list(reader)

for row in rows:
    print(row)
```

### Writing a CSV file

We will be using the [`csv.writer`](https://docs.python.org/2/library/csv.html#csv.writer) to write csv files. [`csv.DictWriter`](https://docs.python.org/2/library/csv.html#csv.DictWriter) is a higher level abstraction you can also use but we will be using `csv.writer` in the examples below.

```python
import csv

with open('testwrite.csv', 'w') as f:
    writer = csv.writer(f)
    writer.writerow(['col1', 'col2'])
    writer.writerow(['val1', 'val2'])
    writer.writerow(['val1', 'val2'])
    writer.writerow(['val1', 'val2'])
```

You can read more about the csv module here: https://docs.python.org/2/library/csv.html

## JSON

### Opening a JSON file

This snippet reads `test.json` and loads the contents as a dict into the variable `data`.

```python
import json

with open('test.json') as f:
    data = json.load(f)
```

### Writing a JSON file

```python
import json

rows = [
    {"name": "Rachel", "value": 34},
    {"name": "Monica", "value": 34},
    {"name": "Phoebe", "value": 37}
]

with open('testwrite.json', 'w') as f:
    json.dump(rows, f)
```

