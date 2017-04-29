# Javascript - Loops

**Loops** is a construct which allows you to repeat a set of instructions a specific number of times, or until a specific condition is true.

## ```for``` loops

```for``` loops are used to run through a set of instructions a specific number of times.

```
var countTo = 10;
for (var i = 1; i <= countTo; i++) {
	console.log(i);
}

// This code is saying "starting at i = 1, log the value of i, after logging i, if i is less than
// or equal to the value of countTo, increment i by one, and then repeat the process."
```

Use ```for``` loops whenever there is a set of operations that you want to do a set number of times.

## ```while``` loops

As ```for``` loops are used to run a block of behavior **a set number of times**, ```while``` loops are about running a block of behavior **as long as some logical condition is true**.

```
var counter = 1;
var countTo = 10;
while (counter <= countTo) {
	console.log(counter);
	counter++;
}

// This example is meant to demonstrate syntax, but in practice 'for' loop is better for this use case.
```

```while``` loops are meant to be used where the looped behavior does not have a known number of iterations, but instead a known logical condition where it should terminate.

```
while (true) {
	// do something
	if (someCondition) {
	break;
  }
}

// Since the condition above will always be true it will run forever until the condition in the if block is true; use break to break out of a loop and move on to any remaining code.
```