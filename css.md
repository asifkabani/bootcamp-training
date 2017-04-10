## CSS
+ **Cascading Style Sheets** is used as a presentation layer (as opposed to HTML which is a structure and content layer); used to control style and appearance.
+ **Ruleset** is how a particular element should look. Below example shows the ruleset for the paragraph element. **Selector** is an element(s) that will be targeted by the declarations. In the same case, 'p' is the selector. **Declaration block** is a set of declarations, the items in between braces {} are declarations, contained within the declaration block. **Declarations** consist of a property and a value, example above (property: color, value: red).
```css
p {
  color: red;
  font-size: 10px;
}
```
+ **Pseudo-Class** is used to specify a special state of the element.
```css
p::first-letter
```
+ **Pseudo-Element** is used to style specified parts of an element.
```css
div.foo:hover
```
+ **Cascade** is a process browsers follow to determine which CSS values get applied for all the properties on a given element.

### Box Model
Box model is the idea that every element of a web page is a rectangle area, ```box-sizing: content-box ``` is the default value it is set at. This default determines the total space taken by an element, from width, height, padding, margin, and border. The answer to the below example is 282px width. So the true value of that element does not stay what is defined ```width: 200px```.
```css
div.foo {
width: 200px;
height: 100px;
padding: 10px;
border: 1px solid green;
margin: 30px;
}
```
To solve this issue, we set the ```box-sizing: border-box``` as a good reset in the beginning for our universal selector ```*, *:before, *:after {box-sizing: border-box;}``` which makes all the element even to the width.

Best reset technique:
```css
html {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*, *:before, *:after {
  -webkit-box-sizing: inherit;
  -moz-box-sizing: inherit;
  box-sizing: inherit;
  }
  ```
  
Best reset stylesheets to work with:
+ [Meyer Rest](http://meyerweb.com/eric/tools/css/reset/reset.css)
+ [Normalize.css](https://necolas.github.io/normalize.css/)

### CSS Selectors
**Element selector** consists of only the element you want to target.
```css
p {
  padding: 30px;
  font-size: 16px;
}
```

**Combination selectors** are used to target one or more classes of an element.
```css
.foo.bar {
  /* make some rules */
}
```

This example is targeting the paragraph of the two classes.
```css
p.foo.bar {
  /* make some rules */
}
```

Another example to demonstrate:
```css
#header.callout {}
```
```html
<div id="header" class="callout"></div>
```
```css
#header .callout {}
```
```html
<div id="header" class="callout">
<div class="callout"></div>
</div>
```


---
### Resources
+ [Text on Images](https://css-tricks.com/design-considerations-text-images/)
