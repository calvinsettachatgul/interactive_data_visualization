***Binding data***

***In a Bind***

use selection.data() method to bind DOM elements 
but there are 2 things we need in place first 

01 data
02 selection of DOM elments

***Data***

accept any array, strings, objects

JSON and GeoJSON

even has build-in methods to help you load in CSV files

array of numbers

var dataset = [5, 10, 15 ,20, 25];

***Please Make Your Selection***

decide what to select

simple new paragraph for each value in the data set

d3.select("body).selectAll("p")

but paragraphs don't exist yet!!

answer enter()

d3.select("body").selectAll("p")
	.data(dataset)
	.enter()
	.append("p")
	.text("New paragraph!");

.select("body") finds the body in DOM and hands a ref off to next step

.selectAll("p") selects all paragraph in DOM

returns empty selection

.data(dataset) counts and parses data values

5 values in our data set 5 times once for each value

.enter()
	create new, data-bound elements use enter 

	creates a new placeholder element on which work magic

	hands off ref to this new placeholder to next step

.append("p") takes placeholder selection created by enter() inserts p element into DOM hands off ref to element just created to the next stop in the chain

.text("New paragraph!") takes ref to newly created p and inserts a text value

***Bound and Determinded***


where is the data?

console.log(d3.selectAll("p"))

an array is printed

__datat__:5
the data is in __data__

D3 binds data to an element that data doesn't exist in the  DOM but exists in memory as __data__
