# Javascript

+ JavaScript does two things: on the one hand, modeling and manipulating data and processes, and on the other hand, interacting with browser elements (which are represented using HTML).

+ The part of JavaScript that deals with modeling and manipulating data — that is, using variables, strings, numbers, logic, functions, etc. — is specified by ECMA (the European Association for Standardizing Information and Communication Systems). This organization creates the ECMAscript specification, which is a description of what a language called ECMAscript should implement. It's up to individual browsers to decide how to implement the features called for by the ECMAscript specification.

+ The part of JavaScript that deals with interacting with HTML elements — called the DOM (document object model) API, is specified by the W3C(World Wide Web Consortium), which is the same organization that creates the specification for HTML.

+ **What** JavaScript is gets specified by the ECMA and W3C specs. Individual browsers handle the **how** of implementing the ECMA and W3C specifications.

##Variable

+ A **variable** is a name that is attached to a **value**.
	+ They give us a shorthand way to refer to values created elsewhere in a program. We can declare and define a variable once, and pass that value around in our code without having to rewrite it each time.
	+ They give us a way to manage **state** in a program. State has to do with persisting values over time in a program.

+ Three times to think about variables: **declaring a variable**, **assigning a value to it**, **retrieving its value**

Variable **declaration** is telling the computer that it needs to set aside a space in memory for a new variable.
``` var myVar;```