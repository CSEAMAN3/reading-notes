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


















