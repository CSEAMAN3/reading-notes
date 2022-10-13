# Node.js

The Net Ninja - YouTube channel - Node JS tutorials for beginners

#### Node.js Actually is...

A platform which allows us to run Javascript on a computer / server

Read, delete and update files

Easily communicate with a database


#### Why is Node.js so popular

It uses JavaScript

Very fast (runs on the V8 engine & uses non-blocking code)

Huge ecosystem of open source packages

Great for real-time services (like chat)

#### What we will learn

The inner workings of Node.js
  - V8 engine
  - Modules
  - Event emitter
  - The file system

Creating a web server
  - Routing
  - Express
  - Templating

Make a Node.js application (todo app)


What you need to know already
  - JavaScript
  - HTML
  - A tiny bit about the command line

#### The V8 Engine

This tutorial is so we can understand how Node.js works

JavaSript Engines

  - Computers do not understand JavaScript

  - A JavaScript engine takes JavaScript, and converts it into something it does understand - machine code.

When we write javascript the computer does not understand it, it takes a javascript engine to convert the code into machine code so

it can be understood by the computer.

Machine Code
  - Javascript
  - C++
  - Assembly Language
  - Machine Code

Machine code is what the computer understands, but you can not write code like this as it is to messy and confusing to understand.

Assembly language sits above it, still very hard to understand and code. 

Then we have C or C++ which abstract away but still have a lot of power. 

Finally we have Javascript and is abstracted alot away from machine code.

When we write javascript we need it to be converted into machine code so the computer understands what we want it to do.

Node.js is written in C++ but as a program it allows us to write in javascript which can run on a computer or server.

The reason Node.js is written in C++ is because it uses the V8 JavaScript engine written by google which is also written in C++.

So... We know

  - Node.js is written in C++
  - At the Heart of Node.js is the V8 engine
  - The V8 engine converts our JS into machine code

Node.js is a C++ application, it takes V8 and embeds it into Node.js

So how does Node.js work with V8

Javascript -> C++ Node.js V8 -> Machine Code

When we write javascript and run it through Node.js, the javascript is parsed into V8 and converted into machine code.

#### The Global Object

When we write Javascript in a browser the global object is the window.

We can access methods and properties on that window object such as alert, scroll, set time out ect.

When we write JavaScript in Node.js the global object is no longer the window object because we're 

not in a browser. The global object in Node.js is an object called global, much like the window object

it gives us access to some methods we can use straight out of the box in Node.js.

The way We end a process in the terminal is control c on the keyboard.

Node.js can tell us where we are in a particular directory or what file we are in. 

console.log(__dirname)

The console will now tell us which directory we are in.

console.log(__filename)

The console will now tell us which the full directory and the file.

#### Function Expressions

How Would we normally make a function expression in javascript?

```
//normal function statement

function nameOfFunc(){
  console.log("Hi")
}

//invoke the function

nameOfFunc()

//What is a function expression

var funcExp = function(){
  console.log("bye")
}

//invoke the function

funcExp()

```

You will see the function expression pattern alot in Node.js

I can also parse functions from one thing to another..

```

function callFunction(fun){
  fun()
}

var funcExp = function(){
  console.log("bye")
}


callFunction(funcExp)

```

We will see this pattern alot in Node.js

#### Modules & require()

when writing a Node.js Application we don't place all our application code in one file  and just let it run.

This would be nightmare to manage and for other developers to work with, refactor, extend, ect.

So, we split our code up into logical modules, so we have different modules for different bits of code which has it's own certain

functionality in our application. We then call upon those modules whenever we need them.

Example: 

Say we had a module. some sort of utilty module that counted things for us. Then we could go ahead and create our module then 

call upon that module when we need to count something. 

create a new file called count.js

A module is essentially just another javascript file.

In count.js

```
var counter = function(arr){
  return "There are " + arr.length + " elements in this array" 
}

console.log(counter(["Chris","Louise", "Thomas"]))
```

If we now want to use this functionality elsewhere in the application for example in app.js

Well, thats where we use the require function, the require function is in the glodal object in Node.js.

This means we can use it wherever we are.

to use count.js in app.js

inside app.js
```
require("./count")
```

we write require then parenthesis, inside the parenthesis as a string we write the path to the module we require in this file.

So ./ says we want a file in the current directory followed by the file name, in this case it is count.

We do not need to put .js on the end it will automatically find that file.

So what happens if we try to use the counter function inside our app.js file.


```
require("./count")

console.log(counter(["Chris","Louise", "Thomas"]))
```

This will result in an error. The reason this will error is because the counter method is not available to us outside of the

count.js module. 

What we have to do inside the count.js module is explicitly say what part of the module we want to make availble to other files

which require this module.

The way we do that is:

```
var counter = function(arr){
  return "There are " + arr.length + " elements in this array" 
}

module.exports = counter;
```

So now when we require(./count) it will return to us what module.exports is = to. In this case counter.

What we need to do is set require(./count) = to a variable. Becuase it is returning a variable to us.

```
var counter = require("./count")

console.log(counter(["Chris","Louise", "Thomas"]))
```

Now we can use this counter function in the app.js file. This time when we run the code it will console log the string

There are 3 elements in this array


#### Modules Patterns










