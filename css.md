# CSS
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

## Box Model
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

## CSS Selectors
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

## CSS Layout

### Horizontal centering

Works only on block-level elements such as div, paragraph, ordered list, heading, etc. By default, block-level elements extend to the full width of their parent container.
```
margin-left: auto; margin-right: auto;
``` 

When you need to horizontally center inline elements within a block element, ```text-align: center``` does the trick.

**Important:** block-level elements inside the parent require use of a ```width``` so that they sit inside without touching the edges. Also for better mobility use ```max-width```.

### Display property

The ```display``` property determines how an element's block is rendered in the browser (recall that we learned that all HTML elements are blocks, as described by the box model).

+ **Flex** is a new property not yet supported by all browsers. After learning the others, then get into learning it, start with [Flexbox Froggy](http://flexboxfroggy.com/).


+ **Inline elements** don't start on a new line and usually do not contain additional elements, but instead just contains text. [Examples of inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#Elements).

+ **Block-level** elements get displayed on a new line (and take up the whole available line), may contain additional block-level or inline elements, and its height and width can be explicitly set. **Note:** an example is to explicitly set a ```max-width``` for ```p``` elements appearing on a web page as a common practice, because it's hard for users to read overly wide paragraphs. [Examples of block-level elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements#Elements).

+ **Inline-block level** combine characteristics of both inline and block-level elements. An inline-block element displays inline like a span or a element, but you can give it an explicit width, height, margin, and padding. This can be a good approach when you need to create elements with a set width, but you also need them to display side by side. **Note:** Setting font-size to 0 on the parent of a set of inline block elements removes white space between them. The browser interprets line breaks between two inline-elements as a space.

Also know that there are other strategies for solving the underlying layout problem (How do I get set width elements to appear together on the same line?).

One is to use the ```float``` property, and another is to use ```<table>``` elements for layout. Before inline-block was implemented, these were the only two ways to solve this problem, but there are drawbacks to both. Be prepared to encounter legacy code and outdated tutorials that use floats and tables to get set-width elements to appear on the same line, but don't use these solutions in your own work. **Tables are for displaying tabular data, and floats have some good use cases, but don't use them to achieve what inline-block gives you.** Also see [this link](http://learnlayout.com/inline-block.html).

**Note that you can set an element to be inline even if, by default, it’s set to block (and vice-versa). This is a good strategy when you want to use a particular element because it is semantically correct but its default display is not what your designs call for.** One common place you'll see this is in the list of links that appear in a nav bar. By default, both unordered lists and list items are block level elements, but by setting their display property to inline-block, you can get them to display side by side in the nav.

**Finally, a word of caution:** a common beginner mistake is to start setting the display property on all your CSS classes. Don't do this. Oftentimes, the default settings will be what you need. Only explicitly set the display property if you have a specific reason to do so.

### Position property

The ```position``` property is all about the flow of elements in an HTML document.

**Static**

Any HTML element with the ```position: static``` (which is also to say, any element that you don't explicitly set position to a different value on) will have what is called normal flow. Normal flow refers to the default way browsers render content. Under normal flow, block level elements get rendered in the same order that they appear in the HTML markup, one on top of another, starting from the top left corner of the document, and inline elements stretch as wide as their inside content (usually text).

**Fixed**

When an element's position is set to fixed, it will stay in place even when the user scrolls. Fixed elements are taken out of the normal flow and other elements will position themselves as if the fixed element does not exist. For navbars or footers that you want to remain stuck to the top or bottom of the screen, this is often the best approach.

**Tip:** A fixed element does not leave a gap in the page where it would normally have been located.

***Offsets*** are given by CSS for us to use: left, right, top, bottom. These properties can be used on elements whose position is set to fixed, relative, and absolute, but not static.

**Relative**

When an element's position property is set to relative, it is still in the normal flow (in other words, relatively positioned elements are rendered in the order they appear in HTML), but unlike with static elements, we can use offset properties (left, right, top, bottom) with relative elements. Note that any offsets on a relative element are in relation to where they would be in the normal flow, not the viewport. 

**Absolute**

The final position value to cover is absolute. Like fixed elements, absolute elements are outside the normal flow and can be offset, but unlike fixed elements, they are offset in relation to the first parent container with a non-static position. A common use case for absolute positioning is when you have a nav bar where you want to align a logo to the left, and a set of links to the right.

**Tip:** ```absolute``` is the trickiest position value. ```absolute``` behaves like fixed except relative to the nearest positioned ancestor instead of relative to the viewport. If an absolutely-positioned element has no positioned ancestors, it uses the document body, and still moves along with page scrolling.

If you use a fixed header or footer, make sure there is room for it! I put a ```margin-bottom``` on the ```body```.

### Float property

The primary use case for floats is getting text to wrap around an image (or some other container).

**Important**: see [clear-fix hack](http://learnlayout.com/clearfix.html) for issues which may come up using float.

---
### Resources
+ [Text on Images](https://css-tricks.com/design-considerations-text-images/)
+ [CSS Diner](http://flukeout.github.io/)
+ [Learn CSS Layout](http://learnlayout.com/)
+ [Opening the Box Model](http://learn.shayhowe.com/html-css/opening-the-box-model/)
+ [Positioning Content](http://learn.shayhowe.com/html-css/positioning-content/)
+ [Centering in CSS](https://css-tricks.com/centering-css-complete-guide/)
