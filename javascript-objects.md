# Javascript - Objects

**Objects** are a *complex data type* that allow you to bring together common properties and behaviors into a single entity.

Objects are a data structure used to hold **key/value** pairs. An example of this is looking up a word in the dictionary. The word is the key, and the definition would be the value.

```
var ledZepplin = {
	singer: 'Robert Plant',
	guitar: 'Jimmy Page',
	bass: 'John Paul Jones',
	drums: 'Jon Bonham'
}

// singer, guitar, bass, drums: keys
// 'Robert Plant', 'Jimmy Page', etc.: values

// if you need space or a period in a key, use quotation marks around the key.
```

An **object literal** is created by using the ```{}``` bracket syntax.

All keys in an object must be unique -- each key can only be used once. The values can be any Javascript data type (numbers, booleans, other objects, null, functions).

When an object has a value that is a function, the key/value pair is referred to as a **method**.

```
var mammal = {
  numEyes: 2,
  warmBlooded: true, 
  evolve: function() {
    console.log("I'm not mutating, I'm evolving.");
    mammal.numEyes ++;
  } 
}
```

Once the object is created, you can get values and run object methods in two ways:
+ dot notation (```ledZepplin.singer```)
+ bracket notation (```ledZepplin['lead singer']```).

Best to use dot notation, unless you need to get a key with spaces or periods at which case you must use bracket notation.

**Add key/value pairs to an object:**

Once an object is defined, you can add a new key/value using dot or bracket notation:

```
var myFamily = {
  lastName: 'Doe',
  mom: 'Cynthia',
  dad: 'Paul',
};

myFamily.sister = 'Lucinda';
myFamily['brother'] = 'Merle';
myFamily.sayHi = function() {
  console.log('Hello from the ' + myFamily.lastName + 's');
}
```

**To update a value, use the same process:**

```
var foo = {
  bar: 'bizz'
};

foo.bar = 'bang';
```

**To delete key/value pairs, use the **delete** command:**

```
var foo = {
  bar: true
};
delete foo.bar;
console.log(foo.bar); // => undefined
```

**Self reference** is when you work with object literals, use the ```this``` keyword to refer to other properties on the object. ```this``` is used so you can call the variable name without calling the name of the variable, and makes the code more maintainable as it is then not connected to the variable name.

When you have a variable defined in the global scope, and then use the same variable name in a local scope, the locally scoped variable **shadows** the global scoped variable.

When you pass a variable whose data type is an ```object``` it can get tricky. When you pass a variable as an argument to a function, the value is passed by **reference**. That means instead of passing a copy of the value to the function, a **reference** to the original value is passed in. Be careful when writing functions that take objects (inclusive of arrays) as an argument.

## ```Object.keys```

Use **```Object.keys```** when you need to iterate over the key/value pairs in a Javascript object.

```
var pageViewCounts = {
  homePage: 399,
  aboutPage: 400,
  termsOfService: 22
};

console.log(Object.keys(pageViewCounts));

Object.keys(pageViewCounts).forEach(function(key){
  console.log(
    'the `' + key + '` page has ' + pageViewCounts[key] +
    ' views.'
  );
})

// In order to get the log messages about page views in this example, we iterate over the keys of the
// object and retrieve the value for each key.
```

### Factory Functions

**Factory functions** are used to generate individual instances of a single concept or thing. The job of the factory function is to create an individual instance of some model.

```
function mammal(name, numEyes) {
  return {
    name: name,
    isWarmblooded: true,
    numEyes: numEyes,
    evolve: function() {
      console.log(
        "I'm not mutating, I'm evolving.");
      this.numEyes ++;
    },
    explainYourSelf: function() {
      console.log(
        "I'm just a " + this.name + " with " +
        this.numEyes + " eye(s). Nothing to see here."
      );
    }
  };
}

var tiger = mammal('tiger', 2);
tiger.explainYourSelf();
tiger.evolve();
tiger.explainYourSelf();

var oneEyedBadger = mammal('badger', 1);
oneEyedBadger.explainYourSelf();
```

### Looping over collections of objects

Looping over a collection of objects is similar to looping over an array of numbers.

```
var users = [
  {
    name: 'Bernard',
    age: 29,
    birthMonth: 'April'
  },
  {
    name: 'Bernice',
    age: 14,
    birthMonth: 'December'
  },
  {
    name: 'Gerard',
    age: 88,
    birthMonth: 'June'
  },
  {
    name: 'Stella',
    age: 3,
    birthMonth: 'September'
  }
];

users.forEach(function(user) {
  console.log(
    user.name + ' will be ' + (user.age + 1) + ' in ' +
    user.birthMonth
  );
});
```
---
### Resources

+ [JavaScript objects basics](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics)
+ [Guide to working with objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects)
+ [Object-oriented JavaScript for beginners](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS)
+ **Eloquent Javascript**
  + [Data Structures: Objects and Arrays](http://eloquentjavascript.net/04_data.html)
  + [Higher Order Functions](http://eloquentjavascript.net/05_higher_order.html)
  + [The Secret Life of Objects](http://eloquentjavascript.net/06_object.html)

