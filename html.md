# HTML
+ HTML stands for Hypertext Markup Language, it is used to mark up content so web browsers know what kinds of content they're dealing with.
+ HTML is about structure, meaning it specifies each and every one of it's elements and it specifies the hierarchical relationship between elements.
+ Semantic HTML means when you create content, to use the correct elements for that content, such as when you are adding an address use the ```<address>``` to specify the address instead of wrapping the address in a ```<p>``` tag.
Elements are individual HTML components that start with an opening and end with a closing tag and have content in between. Example of 'div' element below:
```html
<div>Some content</div>
```
Tags are used to mark off the beginning and end of an element. Both opening and closing tags consist of angle brackets, tag name, and the closing one has a forward slash '/'; Example of the 'div' tag below:
```html
<div></div>
```
Attributes are modifiers for an HTML element, used for setting properties on the HTML element. Example below of an attribute for the 'img' tag, 'src' is the attribute:
```html
<img src="">
```
Command to the page to parse the browser as HTML5 standards.
```html
<!DOCTYPE>
```
Root element and all other elements are children elements of this root.
```html
<html>
```
This is where we put document meta data.
```html
<head>
```
Title of the page, helps with SEO and for web crawlers to know the name of the page.
```html
<title>
```
Description of the page, help web crawlers understand your page and contribute to search engine optimization.
```html
<meta name="description" content=" ">
```
The tag used to describe the main elements of the web page.
```html
<body>
```

## Forms

**Forms**

Forms are containers that hold a set of inputs. The ```<form>``` element wraps all our inputs and labels. See [this link](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form#Attributes) for form attributes. To progressively support all users you'll want to set the ```action``` and ```method``` attributes. This will ensure user input can be submitted even if JavaScript is disabled or breaks. The ```action``` attribute is the URL of the server endpoint that submitted form data should be sent to. The ```method``` attribute is the request method that the browser should use when sending the data to the server. 

**Inputs** are individual components that a user interacts with - typically corresponding to a single data point. HTML provides numerous input types (text, email, number, password, etc.), and input types differ in how they are rendered. Inputs also vary in how they are validated. See [link for form input types](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Form_<input>_types).

**Fieldsets and legend**

The ```fieldset``` element is used to group together related inputs and labels. An example is to use a fieldset to group together the contact info related inputs and their labels in a form. The main reason to use fieldsets is that they help web crawlers and screen readers understand how inputs are grouped together (even if this is not revealed visually to sighted end users).

The legend element is like a title for the fieldset.

**Inputs and labels**

Standard inputs such as first and last name inputs are standard ```type=text``` inputs, with no special validation rules. **Labels** tell human users, web crawlers, and screen readers what an input is for -- using the ```for``` attribute.

The ```for``` attribute goes on a label, and its value should be set to the ID of the input it's for. Note that although you're generally discouraged from using IDs as CSS selectors, using them to link inputs and labels is **best practice**.

While the label element requires opening and closing tags, inputs do not.

```html
<label for="first-name">First name</label><input id="first-name" name="first-name" type="text">
```

**Input attributes**

```placeholder``` is used to set text that initially displays before the user has input any data. Typically placeholders are used for example entries, and usually they're styled to be lighter than user input text.

```required``` is used to indicate that an input must be filled out. When the user submits the form, if there are any required child inputs on the form, the browser will display a message telling the user where they need to supply data.

The ```pattern``` attribute is used to supply regular expression patterns that the user's input must match with in order to be valid. In the example above, we use this to require that the phone number entry consists of only numbers, and optionally dashes.

Finally, we find the ```type``` attribute. This attribute determines how the element looks and how its validation works. For instance, an input with ```type='email'``` will be valid if the user inputs text that has an ```@``` with text before and after.

**Select and option elements**

The ```<select>``` element is used to let users choose from a list of options. ```<select>``` tags wrap a set of one or more options, and you can pre-select an individual ```<option>``` by adding the selected attribute.

It's possible to use an ```<optgroup>``` element to wrap multiple ```<option>``` elements under a given group name. This is helpful to organize a large set of options.

**Buttons**

```<button>``` elements to allow users to submit and reset the form. This is done by setting the ```type``` attribute.

Buttons have many uses beyond forms once you start working with JavaScript, but when you're only working with HTML and CSS, their use is usually limited to simple form controls.

---
### Resources
+ [How the Web Works](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works)
+ [Building Forms](http://learn.shayhowe.com/html-css/building-forms/)
+ [Guide to Creating Accessible Forms](http://webaim.org/techniques/forms/)
+ [Responsive Web Design Resources](https://bradfrost.github.io/this-is-responsive/resources.html)
