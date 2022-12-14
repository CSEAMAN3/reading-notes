


# Reading notes: Class 04

#### Reference pages:
Creating Hyperlinks
https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks

CSS Layout: Normal Flow CSS
https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow

Layout: Positioning
https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning

JS functions:
https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions

## Learn HTML
### Hyperlinks

What is a HyperLink: 
Hyperlinks allow us to link documents to other documents or resources, link to specific parts of documents, or make apps available at a web address.
Most web content can be converted in a link so when clicked upon or activated the browser goes to another url (web address).

#### Anatomy of a link

Basic links consist of a text wrapped between an achor tag with an href attribute to contain the web address: 
Example:
```
<a href="https://www.helloworld.com">hello world</a>.
```

The title attribute: Including a title attribute to your anchor element allows you to include supporting information about where the link will take you. So when you hover the link a tooltip will display what ever text you have included in your title attribute.
Example:
```
<a href="https://www.helloworld.com" title="The best place to introduce yourself to the world and get to know who else exists">Hello world</a>
```

#### Block level links

Almost any content can be made into a link - this inludes block level elements. For example an image.

```

<a href="https://www.helloworld.com">hello world
  <img src="globe-image.jpg" alt="Earth viewed from space.">
</a>

```

#### A quick primer on URLs and paths

A URL is a Uniform Resource Locator. It is a string of text that defines where something is on the web.
URLs use paths to find files. Paths specify where the file is in the filesystem.
When working locally with a website you will have one directory that contains the entire site. 
index.html will always be our homepage when working on a real website.
Your paths can link to:
The same directory
```
<a href="contacts.html">Contact page</a>

```
Moving down into subdirectories
```
<a href="projects/index.html">Contact page</a>

```
Moving back up into parent directories
```
<a href="../pdfs/project-brief.pdf">Contact page</a>

```
To go up a directory use two dots ..

#### Document Fragments

You can link to a specific part of an HTML document rather than just to the top of the page.
To do this you must assign an id to the element you're wanting to link to.
Usually it is best to link to a heading.
Example
```
<h2 id="mailing-address">Mailing Address</h2>

```

To link to that specific id we would include it at the end of the URL, preceded by a # symbol.
Example:
```
<p>Write to use at our
<a href="contacts.html#mailing-address">mailing address</a>
or contact us on 01603 545343.</p>

```
You can also link to a specific part of the same page by simply using the # symbol and the name of the id.
```

<p>The
<a href="#mailing-address">mailing address</a>
can be found at the bottom of this page.</p>

```

#### Absolute vs relative URLs

Absolute URL: Points to a location defined by its absolute location on the web, including protocol and domain name.
Example: If an index.html page is uploaded to a directory called projects that sits inside the root of a web server, and the website's domain is https://www.example.com, the page would be available at https://www.example.com/projects/index.html
An absolute URL will always point to the same location, no matter where it's used.

Relative URL: Points to a location that is relative to the file you are linking from, more like what we looked at in the previous section. For example, if we wanted to link from our example file at https://www.example.com/projects/index.html to a PDF file in the same directory, the URL would just be the filename ??? project-brief.pdf ??? no extra information needed. If the PDF was available in a subdirectory inside projects called pdfs, the relative link would be pdfs/project-brief.pdf (the equivalent absolute URL would be https://www.example.com/projects/pdfs/project-brief.pdf.)

#### Link best practices

Use clear link wording:
Screen reader users access links jumping around the links to find useful info.
Search engines use link text to index target files so include keywords in your link text.
visual readers skim text. 
Good link text
```
<p><a href="https://www.mozilla.org/firefox/">
  Download Firefox
</a></p>
```
Bad link text
```
<p><a href="https://www.mozilla.org/firefox/">
  Click here
</a>
to download Firefox</p>
```

Other tips:
Don't repeat the URL as part of the link text.
Don't say "link" or "links to" in the link text.
Keep your link text as short as possible.
Minimize instances where multiple copies of the same text are linked to different places. 

#### Linking to non-HTML resources ??? leave clear signposts
Let's look at some examples, to see what kind of text can be used here:

```
<p><a href="https://www.example.com/large-report.pdf">
  Download the sales report (PDF, 10MB)
</a></p>

<p><a href="https://www.example.com/video-stream/" target="_blank">
  Watch the video (stream opens in separate tab, HD quality)
</a></p>

<p><a href="https://www.example.com/car-game">
  Play the car game (requires Flash)
</a></p>
```
#### Use the download attribute when linking to a download
Used when linking to a resource which is intended for download and not loaded in the browser.
Example:
```

<a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=en-US"
   download="firefox-latest-64bit-installer.exe">
  Download Latest Firefox for Windows (64-bit) (English, US)
</a>

```
#### E-mail links

Creating an email link you need to use the mailto: link inside the href attribute of the opening anchor tag.
Example
```

<a href="mailto:nowhere@mozilla.org">Send email to nowhere</a>

```

Here's an example that includes a cc, bcc, subject and body:
```

<a href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&subject=The%20subject%20of%20the%20email&body=The%20body%20of%20the%20email">
  Send mail with cc, bcc, subject and body
</a>

```

1) To create a basic link, we wrap text or other content inside what element?
The anchor element <a href="#"></a>

2) The href attribute contains what information?
 The URL that the link is will request. Can also link internally to other site pages and or even to a specific part of a page.
 
3) What are some ways we can ensure links on our pages are accessible to all readers?
https://usability.yale.edu/web-accessibility/articles/links
Important for the link text to make sense as sreen readers can jump around the links to help locating content. Avoid "click me" or "read more"
give more context to the link by using the title attribute.
images should use the alt text to convey the location and purpose of the link. The alt text should not describe the image. Treat image links as links, not as images.
We can use specific color, font weight and also an underline to help identify visually what is a link.
As a general rule, designers should design custom focus styles. Focus styles should be noticeable and salient.
consider: aria-describedby, aria-label, and aria-labelledby. To read more on this and other techniques follow the link below the question.


## CSS Layout.

Starting with a solid, well-structured document that's readable in normal flow is the best way to begin any webpage.

#### How are elements laid out by default?

Block level elements: Fills the available inline space of the parent element containing it and grows along the block dimension to accommodate its content.
Inline elements: Is the size of its content.
Inline-block elements: Similar to inline elements except they can have padding and margins added on all four sides.

#### Margin Collapsing.
If two vertically adjacent elements both have a margin set on them and their margins touch, the larger of the two margins remains and the smaller one disappears. This is known as margin collapsing. Collapsing margins is only relevant in the vertical direction.

### Positioning
Positioning allows you to take elements out of normal document flow and make them behave differently.

There are a number of different types of positioning that you can put into effect on HTML elements. To make a specific type of positioning active on an element, we use the position property.

#### Static positioning
This is default for every element. It just means "put the element into its normal position in the document flow.

#### Relative positioning
Similar to static positioning, except that once the positioned element has taken its place in the normal flow, you can then modify its final position, including making it overlap other elements on the page.
To modify the elements position you need to use the top, bottom, left, and right properties.

#### Introducing top, bottom, left, and right
top, bottom, left, and right are used alongside position to specify exactly where to move the positioned element to.
the value of these properties can be set in pixels, em, rems, %, etc

#### Absolute positioning
An absolutely positioned element no longer exists in the normal document flow. Instead, it sits on its own layer separate from everything else.
It means that we can create isolated UI features that don't interfere with the layout of other elements on the page.

top, bottom, left, and right behave in a different way with absolute positioning. Rather than positioning the element based on its relative position within the normal document flow, they specify the distance the element should be from each of the containing element's sides.

You can use top, bottom, left, and right to resize elements if you need to.
Yes, margins still affect positioned elements. Margin collapsing doesn't, however.

#### Positioning contexts
Which element is the "containing element" of an absolutely positioned element?
It is dependent on the position property of the ancestors of the positioned element. 
The absolutely positioned element will position it self absolutey to it's nearest relative positioned parent.
If no there is no relative positioned parent the absolutely positioned element will be displayed outside of the <html> element and be positioned relative to the initial viewport.

#### Introducing z-index
When elements start to overlap, what determines which elements appear over others and which elements appear under others?
Positioned elements will overlap none positioned elements.
Positioned elements later in the source order win over positioned elements earlier in the source order.

Can you change the stacking order? Yes, you can, by using the z-index property. "z-index" is a reference to the z-axis.
z-index values affect where positioned elements sit on that axis; positive values move them higher up the stack, negative values move them lower down the stack. By default, positioned elements all have a z-index of auto, which is effectively 0.
z-index only accepts unitless index values. 1,2,3,4 ect

#### Fixed positioning
This works in exactly the same way as absolute positioning, with one key difference: whereas absolute positioning fixes an element in place relative to its nearest positioned ancestor, fixed positioning usually fixes an element in place relative to the visible portion of the viewport.
An ecception to this may be if one of the element's ancestors is a fixed containing block because its transform property has a value other than none.) This means that you can create useful UI items that are fixed in place, like persistent navigation menus that are always visible no matter how much the page scrolls.
  
#### Sticky positioning
his is basically a hybrid between relative and fixed position. It allows a positioned element to act like it's relatively positioned until it's scrolled to a certain threshold (e.g., 10px from the top of the viewport), after which it becomes fixed.

 ```
  .positioned {
  position: sticky;
  top: 30px;
  left: 30px;
}
```
 
#### Scrolling index
An interesting and common use of position: sticky is to create a scrolling index page where different headings stick to the top of the page as they reach it. The markup for such an example might look like so:
```
<h1>Sticky positioning</h1>

<dl>
    <dt>A</dt>
    <dd>Apple</dd>
    <dd>Ant</dd>
    <dd>Altimeter</dd>
    <dd>Airplane</dd>
    <dt>B</dt>
    <dd>Bird</dd>
    <dd>Buzzard</dd>
    <dd>Bee</dd>
    <dd>Banana</dd>
    <dd>Beanstalk</dd>
    <dt>C</dt>
    <dd>Calculator</dd>
    <dd>Cane</dd>
    <dd>Camera</dd>
    <dd>Camel</dd>
    <dt>D</dt>
    <dd>Duck</dd>
    <dd>Dime</dd>
    <dd>Dipstick</dd>
    <dd>Drone</dd>
    <dt>E</dt>
    <dd>Egg</dd>
    <dd>Elephant</dd>
    <dd>Egret</dd>
</dl>
```
```
dt {
  background-color: black;
  color: white;
  padding: 10px;
  position: sticky;
  top: 0;
  left: 0;
  margin: 1em 0;
}
```
Sticky elements are "sticky" relative to the nearest ancestor with a "scrolling mechanism", which is determined by its ancestors' position property.
  
## Learn JS: Functions ??? Reusable Blocks of Code.

functions allow you to store a piece of code that does a single task inside a defined block, and then call that code whenever you need it using a single short command ??? rather than having to type out the same code multiple times.

#### Where do I find functions?
In JavaScript, you'll find functions everywhere. Pretty much anytime you make use of a JavaScript structure that features a pair of parentheses ??? () ??? and you're not using a common built-in language structure like a for loop, while or do...while loop, or if...else statement, you are making use of a function.

#### Built-in browser functions
Examples:
Manipulated a text string
```
const myText = 'I am a string';
const newString = myText.replace('string', 'sausage');
console.log(newString);
// the replace() string function takes a source string,
// and a target string and replaces the source string,
// with the target string, and returns the newly formed string
```
manipulated an array
```
const myArray = ['I', 'love', 'chocolate', 'frogs'];
const madeAString = myArray.join(' ');
console.log(madeAString);
// the join() function takes an array, joins
// all the array items together into a single
// string, and returns this new string
```
when we generate a random number
```
const myNumber = Math.random();
// the random() function generates a random number between
// 0 and up to but not including 1, and returns that number
```
The JavaScript language has many built-in functions to allow you to do useful things without having to write all that code yourself. 

#### Functions versus methods

Functions that are part of objects are called methods.
The built-in code we've made use of so far come in both forms: functions and methods. You can check the full list of the built-in functions, as well as the built-in objects and their corresponding methods here. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects

Anytime you saw a custom name with parentheses straight after it, you were using a custom function.
Example 
```
function draw() {
  ctx.clearRect(0,0,WIDTH,HEIGHT);
  for (let i = 0; i < 100; i++) {
    ctx.beginPath();
    ctx.fillStyle = 'rgba(255,0,0,0.5)';
    ctx.arc(random(WIDTH), random(HEIGHT), random(50), 0, 2 * Math.PI);
    ctx.fill();
  }
}
```
This function draws 100 random circles inside a <canvas> element. Every time we want to do that, we can just invoke the function with this:
```
draw();
```
  
functions can contain whatever code you like ??? you can even call other functions from inside functions. The above function for example calls the random() 
function three times, which is defined by the following code:
  
```
function random(number) {
  return Math.floor(Math.random()*number);
}
```
  
#### Invoking functions
  
To actually use a function after it has been defined, you've got to run ??? or invoke ??? it. This is done by including the name of the function in the code somewhere, followed by parentheses.
```
  function myFunction() {
  alert('hello');
}

myFunction();
// calls the function once
```
Note: This form of creating a function is also known as function declaration. It is always hoisted, so you can call function above function definition and it will work fine.
  
#### Function parameters
  
Some functions require parameters to be specified when you are invoking them ??? these are values that need to be included inside the function parentheses.
Note: Parameters are sometimes called arguments, properties, or even attributes.
  
Example:
The browser's built-in Math.random() function doesn't require any parameters. When called, it always returns a random number between 0 and 1:
```
  const myNumber = Math.random();
```
The browser's built-in string replace() function however needs two parameters ??? the substring to find in the main string, and the substring to replace that string with:
```
const myText = 'I am a string';
const newString = myText.replace('string', 'sausage');
```
####Optional parameters
Sometimes parameters are optional ??? you don't have to specify them. If you don't, the function will generally adopt some kind of default behavior. As an example, the array join() function's parameter is optional:
```
const myArray = ['I', 'love', 'chocolate', 'frogs'];
const madeAString = myArray.join(' ');
console.log(madeAString);
// returns 'I love chocolate frogs'

const madeAnotherString = myArray.join();
console.log(madeAnotherString);
// returns 'I,love,chocolate,frogs'
```
If no parameter is included to specify a joining/delimiting character, a comma is used by default.

#### Default parameters
If you're writing a function and want to support optional parameters, you can specify default values by adding = after the name of the parameter, followed by the default value:
```
  function hello(name = 'Chris') {
  console.log(`Hello ${name}!`);
}

hello('Ari'); // Hello Ari!
hello();      // Hello Chris!
```
####Anonymous functions and arrow functions
This is how we would usually create a function:
```
  function myFunction() {
  alert('hello');
}
```
however we can also create a function that doesn't have a name:
```
(function () {
  alert('hello');
})
```
This is called an anonymous function, because it has no name. You'll often see anonymous functions when a function expects to receive another function as a parameter. In this case the function parameter is often passed as an anonymous function.
  
Note: This form of creating a function is also known as function expression. Unlike function declaration, function expressions are not hoisted.
  
#### Anonymous function example
For example, let's say you want to run some code when the user types into a text box. To do this you can call the addEventListener() function of the text box. This function expects you to pass it (at least) two parameters:

the name of the event to listen for, which in this case is keydown
a function to run when the event happens.
When the user presses a key, the browser will call the function you provided, and will pass it a parameter containing information about this event, including the particular key that the user pressed:
```
  function logKey(event) {
  console.log(`You pressed "${event.key}".`);
}

textBox.addEventListener('keydown', logKey);
```
Instead of defining a separate logKey() function, you can pass an anonymous function into addEventListener():
```
  textBox.addEventListener('keydown', function(event) {
  console.log(`You pressed "${event.key}".`);
});
```
  
#### Arrow functions
  
If you pass an anonymous function like this, there's an alternative form you can use, called an arrow function. Instead of function(event), you write (event) =>:
```
  textBox.addEventListener('keydown', (event) => {
  console.log(`You pressed "${event.key}".`);
});
```
If the function only has one line in the curly brackets, you omit the curly brackets:
```
  textBox.addEventListener('keydown', (event) => console.log(`You pressed "${event.key}".`));
```
If the function only takes one parameter, you can also omit the brackets around the parameter:
```
  textBox.addEventListener('keydown', event => console.log(`You pressed "${event.key}".`));
```
Finally, if your function needs to return a value, and contains only one line, you can also omit the return statement. In the following example we're using the map() method of Array to double every value in the original array:
```
const originals = [1, 2, 3];

const doubled = originals.map((item) => item * 2);

console.log(doubled); // [2, 4, 6]
```
The map() method takes each item in the array in turn, passing it into the given function. It then takes the value returned by that function and adds it to a new array.
  
So in the example above, (item) => item * 2 is the arrow function equivalent of:
```
function doubleItem(item) {
  return item * 2;
}
```
We recommend that you use arrow functions, as they can make your code shorter and more readable. To learn more, see the section on arrow functions in the JavaScript guide, and our reference page on arrow functions.
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#arrow_functions
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions\

#### Arrow function live sample
Here's a complete working example of the "keydown" example we discussed above:

The HTML:
```
<input id="textBox" type="text"></input>
<div id="output"></div>
```
The JavaScript
```
const textBox = document.querySelector("#textBox");
const output = document.querySelector("#output");

textBox.addEventListener('keydown', (event) => output.textContent = `You pressed "${event.key}".`);
```

####Function scope and conflicts
scope ??? a very important concept when dealing with functions.
When you create a function, the variables and other things defined inside the function are inside their own separate scope, meaning that they are locked away in their own separate compartments, unreachable from code outside the functions.
The top level outside all your functions is called the global scope. Values defined in the global scope are accessible from everywhere in the code.

#### Functions Conclusion
This article has explored the fundamental concepts behind functions, paving the way for the next one in which we get practical and take you through the steps to building up your own custom function.
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
