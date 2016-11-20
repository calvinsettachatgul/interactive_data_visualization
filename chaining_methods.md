***Chaining Methods***

http://alignedleft.com/tutorials/d3/chaining-methods

chaining several actions in a single line of code

d3.select("body").append("p").text("New paragraph!");

d3.select("body")
	.append("p")
	.text("New paragraph!");

***One Link at a Time***
d3 references the D3 object so access its methods

.select("body")

.append("p")
creates new DOM element you specify and appends it to the end but just inside whatever selection it's acting on

.text("New paragraph!") takes string and inserts it btwn the opening and closing tags of current selection

append() hands down ref to the new element it just created

the ;


***The Hand-off***

return a selection or reference to a selection

order matters when chaining
adjacent outputs mismatched dropped baton

***Going Chainless***


var body = d3.select("body");
var p = body.append("p");
p.text("New paragraph!");


