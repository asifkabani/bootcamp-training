# Javascript - Strings

Some common scenarios to understand strings:

+ Validating form submissions
+ Injecting data into an HTML template
+ Alphabetically sorting a set of items by some property

A **string** is a **collection of characters**. In JavaScript, we can assign string values to variables by using either *single* or *double quotes*.

```
var foo = 'this is a string';

var foo = "foo";
var bar = 'bar';
```

Strings are used to represent text. Any character from the [UTF-16](https://en.wikipedia.org/wiki/UTF-16) character encoding scheme can be represented in a JavaScript string.

At *greater than ~80 characters per line*, code gets difficult to read. If you need to represent a string that's larger than 80 characters, you can split it over multiple lines by using either the escape character (\) or by closing the quote, adding a + sign, and starting a new string on the next line. Both of the following are valid:

```
var element = '<p>The quick brown fox jumps over the lazy dog. The \
  quick brown fox jumps over the lazy dog. The quick brown fox jumps over \
  the lazy dog.</p>'

var element2 = '<p>The quick brown fox jumps over the lazy dog. The quick ' +
  'brown fox jumps over the lazy dog. The quick brown fox jumps over the ' +
  'lazy dog.</p>'
  ```

## Special characters and Escaping

To use ```"``` character *inside* of a string that you are wrapping with a double quote, use the backslash to **escape** the quotation mark delimiter:


```
var foo = "He said, \"Foo!\"";
console.log(foo); // => He said "Foo!"
```

See [this link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#Escape_notation) for full list of escaped characters.

## Concatenating Strings

Use the ```+``` operator to concatenate (connect) two strings into a bigger:

```
var innerText = 'The quick brown fox jumps over the lazy dog.'
var element = '<p>' + innerText + '</p>';
console.log(element) // => '<p>The quick brown fox jumps over the lazy dog.</p>'
```

Use the ```===``` operator to compare two strings to see if they are the same:

```
var foo = 'foo';
var foo1 = 'foo';
var bar = 'bar';

foo === foo1 // => true
foo === bar // => false
```

## String Methods

```
var foo = 'foo bar foo bar';
foo.length // => 15
foo.charAt(0) // => "f"
foo.slice(4) // => "bar foo bar"
foo.slice(4, 7) // => "bar"
foo.split(" ") // => ["foo", "bar", "foo", "bar"]
foo.toUpperCase() // => "FOO BAR FOO BAR"
foo.replace('foo', 'bar') // => 'bar bar foo bar'
```

See [this list](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#String_instances) for a full list.

**Note:** ES6 template strings gives us a way to refer to variables and execute Javascript code inside of a string:

```
var foo = 'foo';
function sayHello() {
  return 'hello ';
}

var myString = `foo is set to ${foo}. Let's say hello: ${sayHello()}`
```

**Template strings** are indicated by surrounding text between opening and closing backticks (``````` ). Inside a template string, you can refer to variables or execute code by using ```${}```. Template strings are especially valuable when you need to create fill in details in a string from data you're getting from elsewhere. 

