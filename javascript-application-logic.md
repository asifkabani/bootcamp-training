# Javascript - Application Logic

**Application logic** means writing programs that can behave differently depending on their inputs.

## Logical Assertions

An **assertion** is a statement that evaluates to either true or false. Used with ```if``` and ```else``` logical assertions allow writing conditional logic in programs. Do something if it's true, or do something else if it's false.

To remember which values are true and which are false, memorize the falsy ones:

```
//values that evaluate to false
Boolean(false);
Boolean(""); // empty string
Boolean(0);
Boolean(null);
Boolean(undefined);
Boolean(NaN);
```

If it is not any of the above, then it evaluates to ```true```.

## Logical Operators

**Logical operators** are used to make assertions about **two or more statements or values**.

```
&&
// logical and, used to assert whether or not two statements are true.


true && false // false
// Both are Boolean
```

Javascript checks if BOTH expressions evaluate to true. Technically it returns the second value if the first value is true.

Logical operators can also be used with strings and numbers (non-Boolean values).

```
true && "foo bar"
// true
```

There are three logical operators:

```
&& (and)
// Evaluates to true if both sides of the operator evaluate to true.

|| (or)
// Evaluates to true if one or both of the values evalaute to true.

! (not)
// Negates (makes negative) a truth value so !true evaluates to false and !false evaluates to true.
```
```
Logical OR

functions helloX(who) {
	who = who || 'world';
	return "hello " + who; 
}
// First line of function body, who is equal to who or 'world'. Return text "hello" with 'who'. Meaning if no value was input in the helloX() function then return "world" with "hello", hence "hello world".

helloX() // "hello world"
helloX('John') // "hello John"
```

## Equality, strict equality, coercion

**Strict equality** ```===``` first compares data type of the two items being compared, and if they are not the same data type, then it returns ```false```. If they are the same type, it then checks if they have the same value. It checks both sides of the comparison.


```
true === 1
// False because both data types are not the same.

1 === 2
// False because even though data types are the same, 1 is NOT equal to 2.


2 === 2
// True

```

**Coercion** ```==``` compares two items, if they are not the same type it converts one of the value types to the type of the other.

```
true == 1
// True because between a boolean and a number, the number gets converted to a boolean and Boolean(1) is true.
```

















