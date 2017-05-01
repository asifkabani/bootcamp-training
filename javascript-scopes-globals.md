# Javascript - Scopes & Globals

**Variable scope** is a set of rules that define which parts of your code can access a particular variable. It is what allows us to **reuse variable names** at different points in our code without things breaking.

**Avoid global variables** which are variables that can be retrieved and altered anwyhere in your code.

## Variable Scope

**Variable scope** defines how the variables we declare either can or cannot be accessed at different points in the code.

### Global & Local Scope

When you declare a **global scope** it is available everywhere in the code. Any variable **declared outside of a function** has global scope in Javascript.

```
console.log(window.foo); // => undefine
var foo = 'fooo';
console.log(window.foo); // => 'fooo'

function logFoo() {
	console.log(foo);
}

logFoo(); // => 'fooo';

Note: we don't have to say window.foo to refer to foo after it has been defined.
```

Anytime you create a global scope variable, it gets attached to the **window object**.

```
var foo = 'fooo';

function logFoo() {
	var foo = 'barrr';
	cosole.log(
	'inside this function, `foo` == "' + foo + '"');
}

logFoo(); // => 'inside this function, 'foo' == "barrr"'
console.log(foo); // => 'fooo'
```

This is calling a variable inside with **local scope**. It is only accessible within the function's block of instructions. When the function has been executed, the local scope variable disappears.

How does a function in Javascript know about variables declared in the global scope? Because of the **scope chain**.

Inside functions, including nested functions, when you refer to a variable, Javascript follows the **scope chain** to determine the value of the variable:
+ First looks in local scope to see if there is a variable with that name
+ If not defined locally, it then looks in the parent scope of the function to see if the variable is defined there, and if it is it will use that value.
+ It will continue up until it gets to the global scope (aka window).
+ If it does not find it in the global it will raise an ```Uncaught ReferenceError``` meaning your code has a variable that is not defined.

**Note:** if you define a global scope variable in one file, you can also refer to it in other files.

**index.html:**
```
<!DOCTYPE html>
<html>
<body>

  <script type="text/javascript" src="app1.js"></script>
  <script type="text/javascript" src="app2.js"></script>
</body>
</html>
```

**app1.js:**
```
var foo = 'foo';
```

**app2.js**
```
function logFoo() {
  console.log(foo);
}

logFoo();
```

In example above as long as app1.js gets loaded before app2.js the code will work. When ```logFoo``` runs, it will not find ```foo``` in the local scope, and will look up into the global scope, where it will find ```foo```, which has been defined by app1.js.

### Problem with Globals

+ Globals tend to make unintended **side effects** which is when a function reaches outside it's local scope up to the parent scope and alters a value that lives there.
+ A **determinate** function is one that will always return the same value if it is provided with the same inputs.
+ A **indeterminate** functions is one that returns one value some times and another at other times.
+ A function is said to be **pure** when it is both determinate and indeterminate and has no side effects.

```
var firstOption = 'firstOption';

function getOptionName() {
  firstOption = 'firstOption changed!';
  return firstOption;
}

function doOption(optionName) { 
  console.log('`doOption` ran with "' + optionName + '"') }


function doBothOptions() {
  
  var secondOption = getOptionName();
  doOption(firstOption);
  doOption(secondOption);
  
}

doBothOptions();

// There are two problems:
* getOptionName has unintended side effects as it alters a global variable (firstOption)
* doBothOptions relies on firstOption being defined the global scope, rather then the function, so doBothOptions is indeterminate because if the code outside of doBothOptions changes firstOption, then doBothOptions value will change.
``` 

**To avoid these issues, use these strategies:**

Use ```var```, use strict mode:
```
'use strict';

function myFunc() {
	foo = 'foo';
	// do something
}

myFunc(); // => raises 'Uncaught ReferenceError'

// When strict mode is enabled, anytime a variable is declared without ```var``` keyword an error will be triggered.
// 'use strict'; can be used at the top of a file for the entire file or at the top of a function if it is only meant to be used within the function body. Best practice is to put it at the top of all JS files, unless you have a reason.
```

**One exceptional case where it is okay to use globals:** using for example jQuery script in the page as it will put a variable called ```$``` in the global scope so you can reference it in other files and functions.


### Hoisting

**Hoisting** refers to the way the Javascript interpreter finds every variable declaration within a given scope, and moves it to the top of the scope. JS does an initial pass through where it looks for any and all variable declarations.

```
function myFunc2() {
  console.log(myString);
  var myString = 'foo';
}

// This is converted to:

function myFunc2() {
  var myString;
  console.log(myString);
  myString = 'foo';
}
```

This holds true for global scope as well:
```
console.log(foo);
var foo = 'foo';

// This interprets to:

var foo;
console.log(foo);
foo = 'foo';
```

Hoisting is also why you can call a function before you declare them, assuming you are using function declaration syntax (```function myFunc() {}```) over function express syntax (```var myFunc = function() {};```):

```
helloWorld();

function helloWorld {
	console.log('hello world');
}

// The interpreter hoists the entire function declaration to the top:

function helloWorld () {
	console.log('hello world');
}

helloWorld();
```
