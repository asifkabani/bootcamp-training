# Javascript - Control Flow

**Control flow** dictates how programs execute different sets of instructions based on differing conditions.

Two ways of achieving control flow are conditions (```if```, ```else```, ```else if```) and ```try/catch/finally``` blocks.

## Conditionals ```if```, ```else```, ```else if```

To use a conditional, begin with ```if``` followed by an expression wrapped in parantheses ```(true === true)```. Between ```{...}``` comes the statement(s) to be executed if the expression evaluates to true.
```
function sanityCheck() {
	if (true === true) {
	  console.log("true is still true. that's reassuring.");
	}
}
```

The same syntax is used for ```else``` and ```else if``` but they both have to come after and adjacent ```if``` block;

```
function analyzeNumber(num) {
	if (typeof num !== 'number') {
		console.log('not a number');
	}
	else if (num % 2 === 0) {
		console.log('even number');
	}
	else {
		console.log('odd number');function 
	}
}

analyzeNumber();
// Since empty will return 'not a number'.
```

Common pattern is to set a variable's value to a default value and then reassign it based on one or more conditional statements:

```
var myVar = null;
if (condition1) {
	myVar = 'something other than default';
}

//  A shortcut for this situation provided by Javascript, the ternary operator:

var myVar = condition1 ? 'something other than default' : null;
// The syntax for ternary operator is a logical expression (something that can be coerced to a boolean) followed by the ? operator, followed by value to be returned if the condition is true, followed by the : operator, followed by the value to be returned if the conditions is NOT true.
```

## ```try``` / ```catch``` / ```finally```

Javascript gives us three commands for dealing with conditional logic in the case of **errors**.
They allow us to specify a block of behvior that is to be tried (```try```). If that does not work, the behavior in the ```catch``` block runs. And either in success or failure case, ```finally``` block will run. You do not have to use ```finally``` with ```try``` and ```catch```.

The ```throw``` keyword can also be used to intentionally raise an error:

```
try {
	throw 'myException';
}
catch (e) {
	// do something
}
```

When a ```catch``` block runs, the error no longer "bubbles up" like it would otherwise. The browser will run the ```catch``` block and then continue running the next line of code. This is in contrast to an uncaught error, which bubbles up and stops code execution.