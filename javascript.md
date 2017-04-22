# Javascript

+ JavaScript does two things: on the one hand, modeling and manipulating data and processes, and on the other hand, interacting with browser elements (which are represented using HTML).

+ The part of JavaScript that deals with modeling and manipulating data — that is, using variables, strings, numbers, logic, functions, etc. — is specified by ECMA (the European Association for Standardizing Information and Communication Systems). This organization creates the ECMAscript specification, which is a description of what a language called ECMAscript should implement. It's up to individual browsers to decide how to implement the features called for by the ECMAscript specification.

+ The part of JavaScript that deals with interacting with HTML elements — called the DOM (document object model) API, is specified by the W3C(World Wide Web Consortium), which is the same organization that creates the specification for HTML.

+ **What** JavaScript is gets specified by the ECMA and W3C specs. Individual browsers handle the **how** of implementing the ECMA and W3C specifications.

## Variable

A **variable** is a name that is attached to a **value**.

+ They give us a shorthand way to refer to values created elsewhere in a program. We can declare and define a variable once, and pass that value around in our code without having to rewrite it each time.

+ They give us a way to manage **state** in a program. State has to do with persisting values over time in a program.

+ Three times to think about variables: **declaring a variable**, **assigning a value to it**, **retrieving its value**

Variable **declaration** is telling the computer that it needs to set aside a space in memory for a new variable.

``` **var** myVar;```

**Note:** hen you declare a variable, it doesn't have a value yet. By default, JavaScript gives declared variables the special value ```undefined```.

Assign a value to a variable:

```
**var** myVar;
myVar = 6;
```

The **assignment operator (=)** is used to assign a value to a variable. We could update the value of myVar by adding another line using the assignment operator (for instance, a line that says ```myVar = 'foo';```).

```
var myVar = 6;
```

This code both declares the variable ```myVar``` and assigns the value ```6``` to it.

To access the value in a variable, refer to the variable in you rode. Example:

```
var myVar = 6;
alert(myVar); // causes a popup to appear with the alert message "6"
```

### Naming Variables

There are rules about how variable names **must** look in order for the Javascript interpreter to recognize it is a variable. See [this link](https://mathiasbynens.be/notes/javascript-identifiers)for rules governing this.

Also stylistic conventions about we **should** name our variables.

**Reserved words** cannot be used as variable names.

```
var var = 'some value';
// this will cause an error
```

**Note:** but they can be used within a variable name:

```
var varFoo = 'some value';
// this is okay
```

**Character restrictions** require taht a variable name must begin with an upper or lower case letter, ```$``` or ```_```. It cannot begin with a number.

Numbers can be used elsewhere in the variable name:

```
var myFoo2;
// this is okay

```

Spaces cannot be used in the variable name:

```
var my Foo = 'bar';
// this is not okay
```

Comparison and logical operators cannot be used in variable names:

```
var my+Foo;
// this is not okay
```

**Best practices to follow:**

Use **camelCasing** to write variable names, which starts with a lowercase, uses lowercase characters throughout, except for the first letter of a new word in the variable name.

```
thisIsCamelCasing
```

Choose meaningful variable names depending on how the variable name gets used in the program.

```
// good
var clickCount;

// bad
var y;
```

Avoid global variables:

```
foo = 'bar';

// this will still work without using var but it will be creating a global variable instead. Do not use untless you have a reason to do so.
```

It's best to put ```'use strict';``` at the top of a Javascript file or on top of an individual function to stop code like this from executing. Strict mode insures that no global variables get created.

## Data Types

A **data type** is a kind of value that variables can have, there are six data types:

+ String
+ Number
+ Boolean
+ Null
+ Undefined
+ Object

### String

String are indicated with an opening and closing quotes **BUT** both must be the same kind, cannot open with single and close with double. They are used to represent **text**. Any character from the Unicode](https://en.wikipedia.org/wiki/Unicode) scheme can be shown in a string.

```
var foo = 'bar';
var bar = "foo";
// both are valid
```

### Number

Number type is used to represent integer values like whole numbers (1, 2, 100), and floating point decimal numbers (1.223).


### null

```null``` is used to indicate a variable has no value. Javascript thinks it is an "object" even though it is a data type (un-fixed issue).

### Boolean

Signify true or false, only two values ```true``` and ```false```.

### undefined

```undefined``` is a special value the browser assigns to a variable when it first creates them in memory.

```
var foo = undefined;.
// NEVER do, if you want to represent the absence of a value, use null.
```

### Functions

A mini program that you define once and call elsewhere.

```
function sayHello(personName) {
 var greeting =  "Hi there, " + personName;
 console.log(greeting);
}
```

Functions are **values**, but not like the other data types. A ```function``` describes a set of instructions that can be run elsewhere. These instructions can create, manipulate and reference the other simple data types (numbers, strings, booleans, null, undefined).

### Objects

Are considered to be a **complex data type** because they combine the **primitive data types** (numbers, strings, boolean, null, undefined). They allow us to have variables which point to a collection of values, instead of a single value.

```
var person = {
  name: 'Jane Doe',
  greet: function() {
    console.log('Hello world');
  }
}

console.log(person.name); // => Jane Doe
person.greet(); // => Hello world
```

**Arrays** which are lists, technically are objects, the syntax for them:

```
var myFriends = ['Tweedle Dee', 'Tweedle Dum'];
```

### Coercion

```
var stringVar = 'Kilroy was here ';
var numVar = 12;

var combined = stringVar + numVar;
typeof combined; // => string
console.log(combined); // => Kilroy was here 12

// The example above demonstrates that if you combine a number with a string using the + operator, the resulting value will be a string.
```

The idea is that if you use an operator such as + with two values with different data types, Javascript will force one of the variables to the data type of the other.

---
## Resources

+ [Eloquent Javascript](http://eloquentjavascript.net/00_intro.html)
+ [Javascript Data Types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures)
+ [Guide to Variables](https://www.javascript.com/learn/javascript/)