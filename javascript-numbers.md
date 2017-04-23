# Javascript - Numbers

```number``` is a single data type for representing integers (whole numbers like -1, 0, 2, 3000, etc. and floating point decimal numbers like 2.3344)

```
typeof 7 === "number" // => true
var total = 1 + 2 + 3 + 4;
console.log(total) // => 10
total = total + 1;
console.log(total) // => 11
total += 3
console.log(total) // => 14
total ++;
console.log(total) // => 15
console.log(3/10) // => 0.3
```


## Arithmetic Operators

Numbers can also use the arithmetic operators:

+ ```+``` addition
+ ```-``` subtraction
+ ```*``` multiplication
+ ```/``` division
+ ```**``` exponentiation
+ ```%``` remainder (modulo or modulus operator)

Shortcut functions for incrementing numbers:

```
var counter = 0;
console.log(counter) // => 0
counter += 1;
console.log(counter) // => 1
counter += 9;
console.log(counter) // => 10
counter -= 1;
console.log(counter) // => 9
```

These compound operators allow us to change the value of a number variable in place — that is, we don't have to say ```counter = counter + 1;```. Calling ```counter ++``` also increases the value of counter by 1. 

Note that you can also increment like this ```++counter```. The difference between the two is illustrated here:

```
var i = 0;
var j = 0;

// postfix operator
var x = i++;

// prefix operator
var y = ++j;

console.log(x); // 0
console.log(i); // 1

console.log(y); // 1
console.log(j); // 1
```

With both the prefix (```++j```) and postfix (```i++```) operators, the original variable is incremented by 1 (that is, after running ```++j```, ```j``` is equal to 1, and after running ```i++```, ```i``` is equal to 1). The difference is in the **value that is returned** by the operator. When you run the ```++``` either before or after a variable, it returns a value. In the case of **the prefix operator, it increments before it returns the value**. In the case of **the postfix operator, it increments after it returns the value**.

Operations can be grouped, as in Algebra, with parentheses. JavaScript handles operator precedence via **PEMDAS (parenthesis, exponents, multiplication/division, addition/subtraction)**. So, for instance, in ```var foo = 3 + 2 * 6 / 3```, foo will evaluate to ```7``` because we first do ```2 * 6 / 3```, which gives us ```4```, and add that to ```3```, for ```7```.

See [this link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Arithmetic_Operators) for more information about arithmetic operators.

## Comparing Numbers

+ ```<``` less than
+ ```<=``` less than or equal to
+ ```>``` greater than
+ ```>=``` greater than or equal to
+ ```===``` equal
+ ```!==``` not equal

```
// Examples of comparing numbers:

var foo = 1;
var bar = 2;

foo < bar // => true
foo === 1 // => true
foo >= foo + bar // false
```

See [this link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) for built-in ```Math``` object methods.
