# Functional Programming

+ Easier to reason about
+ Less bugs - easier to reason about
+ Less time - able to reuse more of your code
+ Functions are values - functions can be assigned to variables OR passed into other functions...higher order functions
+ 

```
function triple(x) {
	return x 3
}

But, Javascript can do this:

// Create an anonymouse function and assign it to a variable. Just like any other value,
// we can pass it around.
var triple = functions(x) {
	return x * 3
}

var waffle = triple
waffle(30)
```

What are they good for?
Composition - take one function into another function, allows us compose alot of small functions into bigger functions.


```
Most basic and useful function is filter, a filter on the array that accepts another function as an argument.

var animals = [
{ name: 'Fluffykins', species: 'rabbit' },
]

