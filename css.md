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

**Multiple selectors** are used to target multiple selectors with the same ruleset, just put a comma between the classes.
```css
.foo, .bar, .bizz.bang {
  /* make the rules */
}
```

**Descendant selectors** target children of the parent element whether they're immediate children, or further down the hierarchy.
```css
aside p {
  /* make rules */
}
```
```html
<aside>
  <p>The quick brown fox jumps over the lazy dog.</p>

  <div class='alert'>
    <h3>Pay attention!</h3>
    <p>Because the quick brown fox jumps over the lazy dog.</p>
  </div>
</aside>
```

**Direct child selectors** target only elements that are direct children of an element.
```css
aside > p {
  /* make rules */
}
```

**Before and after psuedoelements** allow you to render content just before or after your element.
```css
ul li::before {
  content: "\f121";
  font-family: FontAwesome;
  color: green;
  font-size: 20px;
  margin-right: 5px;
}
```

**Anchor pseudoclasses** provides four pseudoclasses for anchor elements.
```css
a:link {
  /* unvisited link */
}

a:visited {
  /* visited link */
}

a:hover {
  /* mouse over link */
}

a:active {
  /* selected link (i.e., you've clicked
    but not released on the link)
 */
}
```

**Attribute selectors** allows you to target elements by attribute value. Common use is for targeting specific kinds of form inputs ```html input[type="radio"] ```.

Options for matching attribute values:
+ Exact match: ```css element[attribute=value]```
+ Match pattern anywhere in value: ```css element[attribute*=value]```
+ Match pattern at beginning of value: ```css element[attribute^=value]```
+ Match pattern at end of value: ```css element[attribute$=value]```

### CSS Layout

**Horizontal centering**
Works only on block-level elements such as div, paragraph, ordered list, heading, etc. By default, block-level elements extend to the full width of their parent container.
```
margin-left: auto; margin-right: auto;
``` 

When you need to horizontally center inline elements within a block element, ```text-align: center``` does the trick.

**Display property**
The *display* property determines how an element's block is rendered in the browser (recall that we learned that all HTML elements are blocks, as described by the box model).

+ **Inline elements** don't start on a new line and usually do not contain additional elements, but instead just contains text. Note: an example is to explicitly set a ```max-width``` for ```p``` elements appearing on a web page as a common practice, because it's hard for users to read overly wide paragraphs. [Examples of inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#Elements)
+ **Block-level** elements get displayed on a new line (and take up the whole available line), may contain additional block-level or inline elements, and its height and width can be explicitly set. [Examples of block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements#Elements)
+ **






---
### Resources
+ [Text on Images](https://css-tricks.com/design-considerations-text-images/)
+ [CSS Diner](http://flukeout.github.io/)
