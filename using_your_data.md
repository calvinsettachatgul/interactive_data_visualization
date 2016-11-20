http://alignedleft.com/tutorials/d3/using-your-data

***using your data***

var dataset = [5, 10, 15, 20, 25];

d3.select("body").selectAll("p")
	.data(dataset)
	.enter()
	.append("p")
	.text("New paragraph");

change the last line to .text(function(d) {return d;});

anytime afer data() create an anonymous fucntion that accepts d as input 
data() ensures that d is set to corresponding value in your original data set given the current element at hand

current element changes as D3 loops over each element


***High-functioning***

function (input) {
	calculate something here
	return output;
}

function(d) {
	return d;
}

wraped in D3's text() function

.text(function(d){
	return d;
}

customize these functions

add some text?

.text(funtion(d){
	return "I can count up to " + d;
});

***Data Wants to be Held***


without wrapping d in an annonymoust function d has no value!

d as a lonely placeholder value that just needs a warm containing hug from a functions parenths

the hug is an annonymous function

.text(function(d){
	return "I can count up to " + d;
})

.text
.attr() and many other D3 methods take a function as an arg

text() can take either simply static string as an arg

.text("someString");

or the rest of a function

.text(someFunction())

or an anonymous function 

.text(function(d){
	return d;
})

you are defining an anon fcn
D3 sees a fcn there it will call that function 
	handing off the current datum d as the fcn arg

without function wont know whom it should hand off the arg d

***Beyond Text***

complicated with other methods

attr()
style()

allow HTML attributes and CSS prop on selections

adding this

.style("color", "red");

all red color?

what if we add custom function to make text only red if current datum exceeds a certain threshold

revise the fcn

.style("color" function(d){
	if (d > 15) {
		return "red";
	} else {
		return "black";	
	}
}
