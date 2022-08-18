# Class 1

ACP stands for add, commit, push

How the web works
https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works
Link is a reference to understand:
How clients and servers communicate.
To summarise Clients (devices used to access the web) send web address requests through browsers to servers (computers which store web pages, sites, apps) which responds allowing the client to download a copy of the webpage requested.

The other important components
To summarise there is more involved than just your client and a server.
Your internet connection, TCP/IP, DNS, HTTP, Component files including Code files and Assets are all involved.
The internet connection allows you to send and recieve data on the web.
TCP/IP stands for Transmission Control Protocol and Internet Protocol. Communnication protocols that define how data should travel across the internet.
DNS: Domain Name System - address book for websites. The browser looks at the DNS to find the websites IP address.
HTTP: Hypertext Transfer Protocol. The language used for clients and servers to communicate.
Component files come in the form of Code files and Assets. Code files include HTML, CSS and JavaScript mostly. Others also exist.

How they all work together
To summarise the client does a search for a web address and the browser goes to the DNS server to find the address of the real server that the website lives on. The browser sends a HTTP request message to the server requesting the server sends a copy of the website to the client. If the server approves the clients request it sends a 200 OK message which means it is ok to view the website. The server then sends the website files in small chunks called data packets. The browser assembles the data packets to display the webpage on the clients display. All data sent between the client and server are sent across the internet connection using TCP/IP.

Order in which component files are parsed.
To summerise the HTML file is parsed first, this allows the browser to identify any link elements and scripts. As the browser parses the HTML file it sends requests to the server for any CSS and JavaScript files which in turn are also parsed. The browser then generates an in-memory DOM tree from the parsed HTML, generates an in-memory CSSOM structure from the parsed CSS, and compiles and executes the parsed JavaScript. The browser then builds the DOM tree, applies the styles from the CSSOM tree and executes the JavaScript. A visual representation is then displayed so the user can view and interact with the webpage.

Explonation of DNS
To summarise real web addresses are made up of special numbers called an IP address. As the IP address is hard to remember the DNS (domain name server) is used to match up the web address you type into the browser with the websites real IP address. The IP address is a unique location on the web.

Packets explained
To summarise the format in which data is sent from server to client is known as packets. We request to view a web page and the data is sent in thousands of small packets. This is done for several reasons: if any are dropped or corrupted they're easier to replace, packets are routed across many different paths making the exchange faster and allows many clients to download the webpage at once.

Website design and process
https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/What_will_your_website_look_like
Link is a reference to understand:
To summarise the process of designing a webpage starts with planning. Who is your website for, what should you website do, what content should your website present, which fonts and colors will best fit the style and message of teh webpage, designing the layout, which images are required. Sketching several rough designs on paper is a great place to start once you're clear on what you website is about and what its intended purpose is.

Javascript Basics
https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics
Link is a reference to understand:
To summarise JavaScript is a language that adds interactivity to your webpages. This can come in the form of buttons, data entry in forms, dynamic styling like animations amongst others.
Javascript has been used to create API's (Application Programming Interfaces) including third party API's as well as third-party frameworks and libraries.
Langauge basics:
Variables - containers that store values. we use either let or const to declare a variable. Using let allows the value of the variable to be changed later in the code. Const states that the variable will constantly be assigned the value it has been given. It can not be changed.
Variables can hold values of many different data types such as: string, number, boolean (true or false), array (allows multiple values to be stored in one variable), object.
Useful operators

- allows you to add to numbers together or combine two strings

* minus / divide and \* multiplication act as you would expect in maths.
  = assigns a value to a variable.
  === strictly equals, tests to see if two values are equal returns true or false.
  ! and !== returns the opposite value for example turns true into false.

conditioanals
if else statements are used to test if an expression returns true or not and allows you to alter the code to suit dependent on the result.

Functions
functions package functionality that we wish to reuse. Functions can be called in the code as and when needed.
Some functions are built in to the browser such as document.querySelector and alert.
Functions can take arguments inside of the parenthesis if needed to execute their job.

Events
Come in the form of event handlers which listen activity in the browser

What is HTML
HTML, hyper text mark up language, tells web browsers how to structure web pagesa and is made up of elements with tags.
The HTML element is made up from an opening tag and a closing tag however there are self closing elements also. The openeing and closing tags of an element state the name of the element however the closing tag begins with a / to state it is the closing tag. Inbetween the tags is where you place your content.
The element is the opening tag followed by the content followed by the closing tag.
Elements placed within other elements is called nesting.
There are two important elements in HTML Block Level Elements and Inline Elements.
Empty elements such as the <img> only have an opening tag. Typically used to insert or embed something into the document.

Attributes
Elements can container Attributes. These provide the element with extra information.
An Attribute will consist of the attribute name followed by the = symbol and then the attribute value wrapped in quotations.

The Anchor element
The Anchor element is specifically designed to turn the text it encloses into a hyperlink.
The Anchor element will have attributes such as href: which defines the web address, the title attribute will give the link a description and the target attribute will determine how the link is open for example target="\_blank" will open the link in a new tab.

Boolean Attributes
These are attributes which don't require a value. A good example is the disabled attribute.

Anatomy of an HTML document

<!DOCTYPE html>: The doctype. This is required to make everything work correctly.
<html></html>: The <html> element. This wraps all the content excluding the doctype.
<head></head>: The <head> element. This container everything you wish to use in your HTML page. CSS links ect
<meta charset="utf-8">: The <meta> element. Represents metadata.
<title></title>: The <title> element. This sets the title for the page and is displayed in browser tab.<body></body>: The <body> element.  This contains all the content which will be displayed.

Whitespace can be used for readabilty but is reduced to one space by HTML parser

Special Characters
In HTML certain characters are considered special characters. These are part of the HTML syntax. To include these you would need to use a character referrence.

HTML comments
To write an HTML comment, wrap it in the special markers <!-- and -->.

Document and website structure
Typically web pages will include specific block level elements for its structure.
These include:
header - Usually placed at the top and contains some sort of logo or heading.
Navigation bar - This links to the main pages of a web site. usually represented by menu buttons, links, or tabs.
The header and the navigation bar are usually consitent throughout every page on a website. Many include the navigation bar inside the header and some argue it is best o keep them seperate for accessibilty / screen reader.
main content - This is the area of the web page that contains the unique content of the page. The content will change on every page of the website.
Sidebar - Some peripheral info, links, quotes, ads, etc.
footer - Placed at the bottom of the page. Contains fine print, copyright notices, or contact info. The footer is also sometimes used for SEO purposes, by providing links for quick access to popular content.

HTML for structuring content

header: <header>.
navigation bar: <nav>.
main content: <main>, with various content subsections represented by <article>, <section>, and <div> elements.
sidebar: <aside>; often placed inside <main>.
footer: <footer>.

<main> is for content unique to this page. Use <main> only once per page, and put it directly inside <body>. Ideally this shouldn't be nested within other elements.
<article> encloses a block of related content that makes sense on its own without the rest of the page (e.g., a single blog post).
<section> is similar to <article>, but it is more for grouping together a single part of the page that constitutes one single piece of functionality (e.g., a mini map, or a set of article headlines and summaries), or a theme. It's considered best practice to begin each section with a heading; also note that you can break <article>s up into different <section>s, or <section>s up into different <article>s, depending on the context.
<aside> contains content that is not directly related to the main content but can provide additional information indirectly related to it (glossary entries, author biography, related links, etc.).
<header> represents a group of introductory content. If it is a child of <body> it defines the global header of a webpage, but if it's a child of an <article> or <section> it defines a specific header for that section (try not to confuse this with titles and headings).
<nav> contains the main navigation functionality for the page. Secondary links, etc., would not go in the navigation.
<footer> represents a group of end content for a page.

Non-semantic wrappers
div and span - make sure you add a class attribute.
span is for inline, div is a block level

Planning a simple website
Information architecture refers to the pages required and how they are arranged.
list the elements which will be common to every page.
Draw rough sketch of the structure.
brainstorm all the content you'll want for your website.
Sort content into groups for which parts will live togehter on different pages.
Sketch rough site map

---

1. Compose a short poem describing how HTTP sends data between computers.

HTTP a message from me, you'll hopefully recieve, your client I'll be.
My browser delivers, the DNS quivers, address search magic, finds what I need.
A copy will do, thats fine by me, a 200 Ok message will show you agree.
my internet connection, TCP and IP, working together will get you to me.
The data packets fly, like rockets in the sky, exploding on my screen, a vision is seen.
The end.

2. Describe how HTML, CSS, and JS files are “parsed” in the browser.
   HTMl files are parsed first allowing to browser to find any links and or scripts. Requests are then sent to the server for the CSS and JS which is then parsed The browser then generates an in-memory DOM tree from the parsed HTML, generates an in-memory CSSOM structure from the parsed CSS, and compiles and executes the parsed JavaScript. The browser then builds the DOM tree, applies the styles from the CSSOM tree and executes the JavaScript. A visual representation is then displayed so the user can view and interact with the webpage.

3)How can you find images to add to a Website?
From what I read you can download them from google. I would use stock libraries some are free but you must credit the creator. You can pay for things such as adobe stock. You should keep the images in a images folder. I personally run through a process - first finding a large image file in terms of pixel width and height, keeping in mind if I want a protrait or landscape image, I then use photoshop to create 1x 2x and 3x image sizes and use srcset to allow the browser to render the appropriate image based on viewport size and pixel density.

4)How do you create a String vs a Number in JavaScript?
a string is wrapped in " or ' where as a number is just typed without being wrapped.
Example: let myAge = "thirty nine" vs let myAge = 39

5)What is a Variable and why are they important in JavaScript?
A variable is a container to store a value. Varianbles are neccessary in JavaScript allowing us to be dynamic like personalize a greeting message or change an image displayed in an image gallery.

What is an HTML attribute?

Describe the Anatomy of an HTMl element.
HTML elements consist of an opening and closing tag. However there are some self closing / empty tags which do not require a closing tag. The element is the opening tag followed by the content followed by the closing tag.

What is the Difference between <article> and <section> element tags?
Generally a section is for grouping together a part of the page or article. An article could have several sections and a section could contain several articles. I would use a section to group things to a specific part of the page. This may be a group of articles. It is also possible that those articles may contain several sections.

What Elements does a “typical” website include?
header, nav, main, footer are the main elements also aside, section and article may be used.

How does metadata influence Search Engine Optimization?
Metadata is written in the search engines language helping them to better understand the topic of your webpages and content. It helps them display more relevant results to searches.

How is the <meta> HTML tag used when specifying metadata?
It is used inbetween the opening and closing tags of the head element on the HTML document with attributes name and content.

---

Read Class 02

HTML text fundamentals
HTML can be used to structure a page of text by adding headings and paragraphs, emphasizing words, creating lists, and more.
headings and paragraphs

<p> tags for paragraphs
There are six heading elements: <h1>, <h2>, <h3>, <h4>, <h5>, and <h6>. Note you should only have 1 h1 per page. As the heading number increases it importance is lessend. Aim to use no more than 3 per page and make sure the are used in a hierarchy. So if you have a section of articles make the section heading a h2 and the article headings a h3 and not the other way around.
Why do we need structure?
People will often scan a page quickly looking at the headings to find what is useful.
search engines indexing your page consider the heading contents as important keywords affecting your page ranking. Without headings pages will perform badly with SEO.
Screen reader help visually impaired, they are able to read headings to help the user find what they're looking for without reading the entire content.
We need the right elements wrapping the right content so CSS and JS can target them.

Why do we need semantics?
We need semantics so there is a clear understanding of what the elements function is. SEO and screen readers for example will be able to understand.
Elements such as span and div have no semantics. So if we need to manipulate somthing with out giving it any semantic meaning we can do so.

Lists
We have 3 types
ul - unordered
ol - oredered
Nesting lists

Emphasis
em element adss emphasis to words these are used by screen reader which will use a different tone.

Strong importance
strong element used again by sreen readers and the tone.

presentational elements
i, bold and underine have no semantics and therefore should not be used.
Always keep an accessibility mindset

###

Advanced text formatting

Description lists
The purpose of these lists is to mark up a set of items and their associated descriptions.
These use the dl element to define the description list. Inbetween the openeing and closing of the dl element we use the dt element meaning description term to wrap each term. We then use the dd element to wrap each description.
Note you can have a single term can have multiple descriptions.

Blockquotes
If a section of block level content (be it a paragraph, multiple paragraphs, a list, etc.) is quoted from somewhere else, you should wrap it inside a <blockquote> element to signify this, and include a URL pointing to the source of the quote inside a cite attribute.

Inline quotations
Inline quotations work in exactly the same way, except that they use the <q> element.

Citations
cite element

Abbreviations
abbr element used to wrap around content which is an abbreviation. Use the title attribute inside the opening tag to provide the full expansion of the term.

Marking up contact details
the address element is wrapped around contact details

Superscript and subscript
Use superscript and subscript when marking up items like dates, chemical formulae, and mathematical equations so they have the correct meaning. <sup> and <sub> elements are used. The sup element will lift the text and make it smaller like the TH of a date 25th for example. Wrap the th with sup element. The sub element will also make the text smaller / lighter but lower it like the number in a chemical fomula.

Representing computer code
<code>: For marking up generic pieces of computer code.

<pre>: For retaining whitespace (generally code blocks) — if you use indentation or excess whitespace inside your text, browsers will ignore it and you will not see it on your rendered page. If you wrap the text in <pre></pre> tags however, your whitespace will be rendered identically to how you see it in your text editor.

<var>: For specifically marking up variable names.
<kbd>: For marking up keyboard (and other types of) input entered into the computer.
<samp>: For marking up the output of a computer program.

Marking up times and dates
HTML also provides the <time> element for marking up times and dates in a machine-readable format.
example <time datetime="2016-01-20">20 January 2016</time>

Why is it important to use semantic elements in our HTML?
We need semantics so there is a clear understanding of what the elements function is. SEO and screen readers for example will be able to understand.

How many levels of headings are there in HTML?
6 - <h1><h2><h3><h4><h5><h6>

What are some uses for the <sup> and <sub> elements?
sup for writing dates wrapped around the th for example 25<sup>th</sup>
sub for writing a chemical formula H<sub>2</sub>O

When using the <abbr> element, what attribute must be added to provide the full expansion of the term?
title example <abbr title="Doctor">Dr</abbr>

###

Learn CSS

Link CSS - External, internal and inline

Selectors
A selector targets HTML to apply styles to content.

Specificity
The CSS language has rules to control which selector is stronger in the event of a conflict, cascade and specificity.

Properties and values
Properties indicate which stylistic feature you wish to modify. Each property is given a value indicating how to style the property.
when a property is paired with a value it is called a decleration block.
CSS declaration blocks are paired with selectors to produce CSS rulesets

Functions
Some values take the form of a function.
The calc() function
An example would be the calc() function, which can do simple math within CSS
example width: calc(90% - 30px);
A function consists of the function name, and parentheses to enclose the values for the function.

Transform functions
syntax
transform: matrix(1.0, 2.0, 3.0, 4.0, 5.0, 6.0);
transform: matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
transform: perspective(17px);
transform: rotate(0.5turn);
transform: rotate3d(1, 2.0, 3.0, 10deg);
transform: rotateX(10deg);
transform: rotateY(10deg);
transform: rotateZ(10deg);
transform: translate(12px, 50%);
transform: translate3d(12px, 50%, 3em);
transform: translateX(2em);
transform: translateY(3in);
transform: translateZ(2px);
transform: scale(2, 0.5);
transform: scale3d(2.5, 1.2, 0.3);
transform: scaleX(2);
transform: scaleY(0.5);
transform: scaleZ(0.3);
transform: skew(30deg, 20deg);
transform: skewX(30deg);
transform: skewY(1.07rad);

Accessibility concerns
Scaling/zooming animations are problematic for accessibility, as they are a common trigger for certain types of migraine. If you need to include such animations on your website, you should provide a control to allow users to turn off animations, preferably site-wide.

Also, consider making use of the prefers-reduced-motion media feature — use it to write a media query that will turn off animations if the user has reduced animation specified in their system preferences.

@rules

One examlpe is @media used

Shorthands
properties like font, background, padding, border, and margin are called shorthand properties. This is because shorthand properties set several values in a single line.

Comments /_ this will be commented in css _/

###

What are ways we can apply CSS to our HTML?
External (recommended), internal and inline styling(should be avoided)

Why should we avoid using inline styles?
Because it's clearer to have all your css in one place and with an external stylesheet styles can be accessed from other pages.

Review the block of code below and answer the following questions:

What is representing the selector?
h2
Which components are the CSS declarations?
color: black;
padding: 5px;

Which components are considered properties?
color and padding

###

JavaScript

Javascript notes have already been written above.

\*Begin with a statement addressing why this topic matters as it relates to what you are studying in this module.

The basics of HTML, CSS and JS are at the core of Web / app / software development. They are the languages which work together allowing you to build content, communicate with others and allow other to communicate back over and for the internet.

What data type is a sequence of text enclosed in single quote marks?
A String

List 4 types of JavaScript operators.

- , / , \* , !

Describe a real world Problem you could solve with a Function.
We could use a function to create and return a random number.

Things I want to know more about
I want to know more about each language I know alot of this will come down to practice practice practive to embed my knowledge.

Class 03
Readings: HTML Lists, Control Flow with JS, and the CSS Box Model

When should you use an unordered list in your HTML document?
When the list items do not have or require a numerical order. There order does not matter.

How do you change the bullet style of unordered list items?
Using CSS I would use the selector for the unordered list (ul) and set the property of list-style with a value that I wanted.

When should you use an ordered list vs an unorder list in your HTML document?
You should use an ordered list if there is a numerical order to follow, if there is some impotance to the order in which they are read. If there is no importance and the list items can be placed in any order an unordered list should be used.

Describe two ways you can change the numbers on list items provided by an ordered list?
You could set an attribute like reversed on the <ol> html element.
You could set an attribute like type="i" on the <ol> html element.

Learn CSS the box model

Describe the CSS properties of margin and padding as characters in a story. What is their role in a story titled: “The Box Model”?

The Box model.
It was a lovely summers evening and two doorman named Margin and Padding had arrived at work as the security of their local boozer, The Box model Inn. During the night everything was fine until one of the customers had an epileptic fit in the seating area, margin and padding were called into action. Padding went inside and made sure all the other customers were pushed 5 meters away from the incident. Margin secured the outside of the box model inn making sure anyone wanting to come into the venue was pushed 5 meters to one side, allowing the paremedics through. Padding and margin were consided heros so the next day they celebrated with a game of ping pong making sure they uploaded their score onto the king pong app.

List and describe the four parts of an HTML elements box as referred to by the box model.
content box - This is where you content is display.
padding box - this sits around the outside of the content box as whitespace so to speak.
border box - this wraps the content and the padding
margin box - this is a box that wraps the border, padding and content. If given a value it can creat space around the outside.

Learn JS

Note that an array inside an array is called a multidimensional array.

Finding items in an array
This is fine if you know the index of an item, but what if you don't? You can find the index of a particular item using the indexOf() method. This takes an item as an argument and returns the index, or -1 if the item was not found in the array:

Adding items to an array
array.push() - will push whatever data you place inside the curly braces into the array as the last item.
array.unshift() - will push whatever data you place inside the curly braces into the array as the first item.
Removing items from an array
array.pop() - will remove the last item of the array.
array.shift() - will remove the first item of the array.
array.splice() - will remove the first item of the array.

for of loop
const birds = ['Parrot', 'Falcon', 'Owl']
for (const bird of birds){
console.log(bird)
}

.map() method
We give the map a function and it will create a new array containing the changed items.

.filter() method
create a function
function isLong(city) {
return city.length > 8;
}
create an array
const cities = ['London', 'Liverpool', 'Totnes', 'Edinburgh']
creat a variable that users filter and parse in the function
const longer = cities.filter(isLong);
return longer and it will return Liverpool and Edinburgh as they're greater than 8 as the function states.

Like map(), we give a function to the filter() method, and filter() calls this function for every item in the array, passing in the item. If the function returns true, then the item is added to a new array. Finally it returns the new array.
Converting between strings and arrays

Often you'll be presented with some raw data contained in a big long string, and you might want to separate the useful items out into a more useful form and then do things to them, like display them in a data table. To do this, we can use the split() method. In its simplest form, this takes a single parameter, the character you want to separate the string at, and returns the substrings between the separator as items in an array.

also learn more about .split and .join

JavaScript's expressions and operators, including assignment, comparison, arithmetic, bitwise, logical, string, ternary and more.

two types of expressions: those that have side effects (such as assigning values) and those that purely evaluate.
Example = the expression x = 7 assigns x with the value 7
example + the expression 3 + 4 uses the + operator to add 3 and 4 together and produces a value, 7.

###

What data types can you store inside of an Array?
strings, numbers, objects, and even other arrays.

Is the people array a valid JavaScript array? If so, how can I access the values stored? If not, why?
The people array is valid and is called a multidimensional array. you can access the values stored by chaining two sets of square brackets. in this example of the people array if we called people [2][3] then is would return the string librarian.

List five shorthand operators for assignment in javascript and describe what they do.
= assignment - This means the value to the left is equal to the value on the right. So x = f() means that X is = to f()
+= addition assignment - This means that the value to the left is equal to itself + the value on the right. So x += f() will be x = x + f()
-= subtraction assignment - This means that the value to the left is = to itslef minus the value on the right. So x -= f() will be x = x - f()
_= multiplication assignment. This means that the value to the left is = to itself x the value on the right. So x _= f() will be x = x \* f()
/= division assignmnet. This means that the value on the left is = to itself divided by the value on the right. So x /= f() will be x = x / f()

Read the code below and evaluate the last expression and explain what the result would be and why.
let a = 10;
let b = 'dog';
let c = false;

// evaluate this
(a + c) + b;

The result is 10dog. a is equal to 10 and c is equal to false, therefore c is equal to nothing or 0. So 10 plus 0 is equal to 10. Then b is equal to the string dog. So the expression is effectivly 10 + dog. The + operator is used for both numeric addition and string concatenation. When a number is added to a string the interpreter converts the number to a string and concatenates them therefore 10 and dog are concatenated to result in 10dog.

Describe a real world example of when a conditional statement should be used in a JavaScript program.
On our website we have a button which when clicked will display or hide some content dependent on the contents current state.
we create varaible let contentVisible = false.
We then add an event listen to the button listening for a click so we can run a function. The function will state if contentVisible === false then we will grab the content by its ID and change the style.display = "block" as well as changing the value of contentVisible to true. Then in the function we will state else if contentVisible === true we will do the same but make the style.display = "none" and set the value of contentVisble back to false.

Give an example of when a Loop is useful in JavaScript.
A loop is useful when we want to loop through an array to take action on each item in the array. For example we have three div containers: div class="appleShelf", div class="orangeShelf, div class="bannaShelf". We also have an array called fruit with 12 indexes. Each index is a string containing a fruit emoji, 6 indexs contain an apple emoji, 4 contain an orange emoji and 2 contain a banana emoji. If we want to place the correct fruit onto the correct shelf (into the correct div) we can loop through the fruit array - for (let i = 0; i < fruit.length; i++) then inside the loop we can create an if else conditional to test if the index is === equal to a specific fruit - if (fruit[i] === apple emoji). Then we can state that the appleShelf div has a text content which will concatenate an apple emoji everytime the condition is met - appleShelf.textContent += "apple emoji". we would then do else if conditionals for the other fruit emojis and shelfs to place the correct fruit on the correct shelf.

let fruit = [
"🍎",
"🍊",
"🍌",
"🍎",
"🍊",
"🍌",
"🍎",
"🍊",
"🍌"
]

const fruitEl = document.getElementById("fruit-el")
fruitEl.textContent = fruit

const appleShelfEl = document.getElementById("appleShelf-el")
const orangeShelfEl = document.getElementById("orangeShelf-el")
const bananaShelfEl = document.getElementById("bananaShelf-el")

document.getElementById("sortFruit-btn").addEventListener("click", function(){
for (let i = 0; i < fruit.length; i++){
if (fruit[i] === "🍎"){
appleShelfEl.textContent += "🍎"
} else if (fruit[i] === "🍊"){
orangeShelfEl.textContent += "🍊"
} else if (fruit[i] === "🍌"){
bananaShelfEl.textContent += "🍌"
}
}
fruitEl.textContent = ""
})
