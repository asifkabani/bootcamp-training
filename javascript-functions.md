# Javascript - Functions

+ A **function**  describes a repeatable process or behavior. You define that behavior once, and you can call it whenever you need to run your set of instructions.

+ In the context of functions, an **argument** is a variable that gets passed to the function when it is called.

+ Well crafted functions like ```alert``` have a **single responsibility**. This means that they are designed to do one thing and do it well. ```alert's``` sole responsibility is to display a pop-up window to the user with a message in it.

+ Well crafted functions are also **determinate**. Given the same inputs on separate invocations, the result should be exactly the same.

```
function alertHelloWorld() {
  alert('Hello world');
}

alertHelloWorld();
```

```function``` keyword signifies that a function is about to be defined. Next comes the function name (in this case, "alertHelloWorld"), followed by its **call signature ```()```***. Call signature refers to the *arguments* *or* **parameters** — if any — that get passed to a function. ```alertHelloWorld``` doesn't get any parameters (aka, arguments) passed to it, but we'll see an example of that in a moment. Between the ```{ .. }``` brackets comes the main block of the function. This is the behavior that will be carried out each time the function is run.

Note that we **call** *or* **invoke** the function by entering a line with the function name followed by the call signature (empty, in the case of alertHelloWorld above: alertHelloWorld()).

Also, note that **defining a function** and **calling/invoking it** *are* **separate things**, and when you define a function, the code isn't automatically run. You only run it by calling it as described above.

```
function hello(name) {
  return 'Hello ' + name + '!';
}

console.log(hello('Thomas')); // => "Hello Thomas!"
```

This function takes one argument ```(name)``` in its call signature:

This function abstracts out the ```name```. We now can call it and pass in any value for ```name```, and it will output a string that says "Hello " + the value of name.

This function has a **return statement**, as do many functions. **A return statement causes a function to return the value to the right of the return keyword••. We can assign values returned by a function to a variable ```(var hiTom = hello("Thomas"))``` or *pass them as inputs to other function calls* ```(console.log(hello("Thomas")))```.

Note that functions that do not set an explicit return value via return still return something, namely, ```undefined```:

```
function noReturn() {
  // don't do anything
}

var foo = noReturn();

console.log(foo); // => undefined
```

Here's a function that takes two numbers and computes their average:

```
function averageOfTwo(num1, num2) {
  return (num1 + num2) / 2;
}
```

Two ways to define functions:

**function declaration**

```
function myFunction() {
  console.log("myFunction");
}
```

**function expression**

```
var myFunction = function(arg1, arg2) {
  console.log("myFunction");
};
```


