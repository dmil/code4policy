
# Visualizing Data

## D3 JS (Data Driven Documents)
D3 JS

* [https://d3js.org/](https://d3js.org/)
* [https://github.com/d3/d3/wiki/Gallery](https://github.com/d3/d3/wiki/Gallery)

Grammar of Graphics

* [https://www.amazon.com/Grammar-Graphics-Statistics-Computing/dp/0387245448](https://www.amazon.com/Grammar-Graphics-Statistics-Computing/dp/0387245448)

What D3 is Not

* [http://ruoyusun.com/2014/05/26/what-d3js-is-not.html](http://ruoyusun.com/2014/05/26/what-d3js-is-not.html
)

## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example - Part 1

Lets create a new webpage with a D3 visualization in it. We'll call this `chart-example`.

1. Create a [new repository](https://github.com/new) in GitHub called `chart-example`. Intialize it with a README.

2. Clone the new repo into your Development folder

	```
	cd ~/Development
	git clone git@github.com:XXXXXX/chart-example.git
	ls
	```
3. Create an `index.html` and a `data.tsv` and open the folder with Sublime Text.

	```
	cd chart-example
	touch index.html
	touch data.tsv
	subl .
	```
4. Grab the code from the example block and put it in `index.html`, grab the data and put it in `data.tsv`
 https://bl.ocks.org/mbostock/3902569
 
5. Now if you run a simple HTTP server, the code will run.

	```
	python2 -m SimpleHTTPServer 8000
	```
	
6. Once you're sure it works, lets commit that.

	```
	
	```
	
## ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) Example - Part 2

The problem with this is that the HTML, CSS, and JavaScript are ill formed. Also, they're all in one big file. Messy! I will demand that you always keep them separated for this class. Lets go ahead and do that.


### Bonus
Add two buttons to your page, one to show the chart and one to hide it

### Super duper bonus
Make those into one button that toggles show/hide of the chart

## ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Try It

Lets see if you can do the same thing again, but this time add the chart into your mozilla-website.

1. Go to your mozilla website on your computer and makesure you're in the master branch.

```
cd ~/Development/mozilla-website
git checkout master
```

2. Create a new branch called `add-chart`

```
```


## Note

Some of these pre-created D3 visualizations take in CSV format (like the simple example that we did above). Others take in a JSON format. We will be a good chunk of tomorrow practicing conversions between CSV and JSON formats using python, which will hopefully open up for your project

  11. any D3 visualization that takes input as CSV or JSON (most of them)
  2. any data source that outputs data as CSV or JSON (including APIs which often serve JSON files)

If you find that you want to use a data visualization, but are not sure how to connect the dataset to the visualization, have someone in your project group chat with me, I'm happy to help you learn how to connect any particular visualization to any particular dataset (JSON or CSV).


## Organizing your Code

[https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/Dealing_with_files)
