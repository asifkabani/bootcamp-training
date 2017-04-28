# Javascript - Arrays

**Arrays** are a data structure for storing lists of items. Arrays are used with **loops**, which are a construct that allows you to execute a set of instructions numerous times. List items can be of different types, and even be other lists.

To create an array we use the square brackets and seperate items in the array with commas. Arrays can be created with 0 or more elements.

```
var emptyArray = [];
var nonEmptyArray = [1, 'two'];
```

Array contents are accessed by *index* meaning you can access an item in an array by asking for the item in a given position in the array.

```
var allTheThings = ['cats', 'dogs', 42, ['foo', 'bar'], true, function() { console.log('hello')}];
console.log("The first thing is " + allTheThings[0]);
// we start counting array items at 0.
```

Add an item to the current list by settings an element in the [0] position;

```
allTheThings[0] = 'bears';
```

Adding items to the end of an array:

```
var myArray = [1, 2, 3];
myArray.push(4);
console.log(myArray);  // => [1, 2, 3, 4]
```

To count the number of items in an array:

```
var myArray = [1, 2, 3, 4];
console.log(myArray.length); // => 4
```

You can use the ```length``` property together with indexing to get or set items relative to the *end* of the list:

```
var myArray = ['one', 'two', 'three', 'four', 'five'];
console.log(myArray[myArray.length - 2]);
// this is targeting 'four'
```

## Array Methods

See [this list](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array#Methods) for all the built in methods.

### ```.pop```

This is used to remove the final item fron an array; the method below returns the discarded item:

```
var myArray = [1, 2, 'three'];
console.log(myArray.length); // => 3
var lastItem = myArray.pop();
console.log(lastItem); // => 'three'
console.log(myArray.length); // => 2
```

### ```shift()```

This is used to remove and return the first element of a list:

```
var myArray = [1, 2, 'three'];
console.log(myArray.length); // => 3
var firstItem = myArray.shift();
console.log(firstItem); // => 1
console.log(myArray.length); // => 2
```

### ```.slice(begin, end)```

This is used to create a new array from an existing array. Without any arguments () it will copy the original array in entirety. Use ```begin``` and ```end``` to specify only parts of the array of the original to be copied. You can also use negative values for the begin paramter parameter in order to select the last *n* numbers of an array.

```
var myArray = [1, 2, 3, 4];

myArray.slice(); // => [1, 2, 3, 4]

copyArray = myArray.slice(0, 2)
console.log(copyArray); // => [1, 2]

myArray.slice(-2); // => [3, 4]
```

### ```sort```

This method sorts an array in *place*, meaning it sorts the original array, it does not make a copy, sort it, then return the sorted copy. Without any agruments () it will alphabetically sort the list by default:

```
var myArray = ['zebra', 'yodel', 'xylophone'];
myArray.sort();
console.log(myArray); // => ['xylophone', 'yodel', 'zebra']
```

If you want to sort an array by any criteria, you must pass in a **compare function** to ```.sort()``` that tells the criteria for sorting any two items. This must return a numeric value. If returned value is < 0, the first element comes before the second. If returned value is > 0, the second element comes first. And if it is = 0 then the two elements have teh same numeric value.

```
var myArray = [1, 2, 10, 20, 100, 200];
myArray.sort();
console.log(myArray); // => {1, 10, 100, 2, 20, 200}

function sortNumbers(a, b) {
  return a - b;
}
myArray.sort(sortNumbers);
// [1, 2, 10, 20, 100, 200]
```

### ```.map()```

This is used to generate a new array of items by **applying the same function to each item** in the original array.

```
function double(num) {
  return 2 * num;
}

var myNumbers = [1, 2, 3, 4];
var doubledNumbers = myNumbers.map(double);
console.log(doubledNumbers); // => [2, 4, 6, 8];

// This example is using .map() to product a collection of HTML elements:

var steps = [ 'wash', 'rinse', 'repeat'];

var stepsElements = steps.map(function(step) {
  return '<li>' + step + '</li>';
});

console.log('<ul>\n\t' + stepsElements.join('\n\t') + '\n</ul>'); // <ul>
                 //   <li>wash</li>
                 //   <li>rinse</li>
                 //   <li>repeat</li>
                 // </ul>
```

### ```.forEach()```

Like ```.map()``` it applies a function to each item in a collection, but it does not return an array of transformed elements.

```
var directionsLibrary = [
  ['wash', 'rinse', 'repeat'],
  ['be born', 'live', 'die'],
            ['wake', 'work', 'sleep']
];

function saveDirectionInDatabase(direction) {
  // save the direction in the database
  console.log('`saveDirectionInDatabase` called');
}

directionsLibrary.forEach(saveDirectionInDatabase);
```

### ```.filter()```

This is used to take on array of items and make a new one that contains only items that a filtering function returns true for.

```
function isEven(num) {
	return num % 2 === 0;
}

var myNumbers = [1, 2, 3, 4, 5, 6];

var evens = myNumbers.filter(isEven);
console.log(evens);
// => [2, 4, 6]
```

### ```.reduce()```

This is useful for combining several elements to a whole from the array data. This iterates over the array while maintaining an accumulation object. This object is returned inside the reduce function and is passed into the subsequent iteration.

```
function sum(total, num) {
  return total + num;
};

var numbers = [1, 2, 3, 4];

console.log(numbers.reduce(sum)); // => 10
```

### ```.find()```

This is used to find a single item in an array.

```
function isEven(num) {
  return num % 2 === 0;
}

function getFirstEvenNumber(numbers) {
  return numbers.find(isEven);
}

var myNumbers = [1, 2, 3, 4, 5, 6];
myNumbers.find(isEven) // => 2

var myNumbers2 = [1, 3, 5, 7, 9];
myNumbers2.find(isEven) // => undefined
```

Like ```.filter```, ```.find``` takes a function that each item in the array is run through (```isEven```, in the example above). If that function returns ```true``` for an element, then that element is returned. If that function returns ```false``` for all of the array items, then ```.find``` returns ```undefined```.
