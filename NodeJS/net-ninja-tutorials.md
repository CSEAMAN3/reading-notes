# Node.js

The Net Ninja - YouTube channel - Node JS tutorials for beginners

#### Node.js Actually is... video 1

A platform which allows us to run Javascript on a computer / server

Read, delete and update files

Easily communicate with a database


#### Why is Node.js so popular video 1

It uses JavaScript

Very fast (runs on the V8 engine & uses non-blocking code)

Huge ecosystem of open source packages

Great for real-time services (like chat)

#### What we will learn video 1

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

#### video 2 installing Node JS

#### The V8 Engine video 3

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

#### The Global Object video 4

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

#### Function Expressions video 5

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

#### Modules & require() video 6

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


#### Modules Patterns video 7

In the last tutorial we created a module, count.js. We applied module.exports = counter to make the variable function accessible elsewhere

outside of the module. But what if we want to return various things, what if this was not just a counter module but a module that returned

different mathmatical things. lets rename the module to stuff.js as it's not just going to be a counter.

First we need to update our app.js to require stuff.

```
var counter = require("./stuff")

console.log(counter(counter(["Chris","Louise","Thomas"]))

```

Now lets create some different functions in the stuff module which we can use.

```
var counter = function(arr){
 return "There are" + arr.length + " elements in this array"
}

var adder = function(a, b){
 return `The sum of the two numbers is ${a + b}`
}

var pi = 3.142

```

So we have created adder and pi variables. And I want all of them to be accessible in app.js when we require the stuff module.

Remember in stuff.js we set module.exports = counter.

Module.exports is just an empty object to begin with, therefore we could add properties to this object.

So we could say module.exports.counter = counter

Now the counter property of this exports object is = to the counter function.

This also means we can add other properties which = to different functions witin the stuff module.

Example inside stuff.js
```
var counter = function(arr){
  return "There are " + arr.length + " elements in this array"
}

var adder = function(a, b){
  return `The sum of the two numbers is ${a + b}`
}

var pi = 3.142

module.exports.counter = counter
module.exports.adder = adder
module.exports.pi = pi

```

All three variables are now available outside of this module where we require them in our application.

So if we require them in our app.js. 

We need to change var counter = require('./stuff') to var stuff = require('stuff')

Counter is just one of the functions in the stuff module. So we are going to store the modules.exports object,

which now has the three properties on it (counter, adder and pi), in this variable called stuff.

Then when we wish to use a property of the modules.exports object we just use the dot notation.

Example inside app.js
```
var stuff = require("./stuff")

console.log(stuff.counter(["Chris","Louise","Thomas"]))
```

This works because stuff in our app.js is = to modules.exports the object from our stuff.js module.

So now we have...

stuff.js
```
var counter = function(arr){
  return "There are " + arr.length + " elements in this array"
}

var adder = function(a, b){
  return `The sum of the two numbers is ${a + b}`
}

var pi = 3.142

module.exports.counter = counter
module.exports.adder = adder
module.exports.pi = pi
```

and app.js
```
var stuff = require("./stuff")

console.log(stuff.counter(["Chris","Louise","Thomas"]))
console.log(stuff.adder(stuff.pi, 5))

```

The console will log There are 3 elements in this array and the sum of the 2 number is 8.142.

All the variables were made accessible in app.js from stuff.js

Now we could do this in an easier way.

We have refenced the variables giving them all a variable name setting them equal to a function 

we have then parsed that variable to the various properties in our modules.exports object.

We could cut out the middleman so to speak, we could export the variables as it is written.

Example inside stuff.js

```
module.exports.counter = function(arr){
  return "There are " + arr.length + " elements in this array"
}

modules.exports.adder = function(a, b){
  return `The sum of the two numbers is ${a + b}`
}

modules.exports.pi = 3.142
```

One more way we can do this 

```
var counter = function(arr){
  return "There are " + arr.length + " elements in this array"
}

var adder = function(a, b){
  return `The sum of the two numbers is ${a + b}`
}

var pi = 3.142

module.exports = {
  counter: counter,
  adder: adder,
  pi: pi
}
```

These are some module patters we can use to export our data or functions and make them available to other files 

when we require the modules.

#### The Event Module video 8

In the last tutorial we created a custom module called stuff, we reuired that in our app.js file and called the variable stuff.

Along with creating custom modules Node.js also ships with a bunch of inbuilt cor modules which we can use in our application.

We can require the inbuilt modules in the same way that we would require our custom modules. 

One of the inbuilt cor modules inside Node.js is called the event module. 

When we are requiring a Node.js cor module we just need to pop in the module name NOT the path to the module.

Because it is a cor module built into Node.js node will recognise the name and therefore it does not need the path.

Example

```
var events = require("events")
```

So whatever is returned on the modules.exports of the events module will be stored in the events variable.

One of the things returned on that module.exports property in this module is the event emitter.

We can use the event emitter in Node.js to create custom events and then react to those events when they are ommitted.

So if I was to write:

```
element.on("click", function(){})
```
This is an event listener. We're saying when this element ommits a click event then fire this call back function and do something.

We are reacting to an event being ommitted on this element.

We can do a similar thing in Node.js we can create our own custom events instead of things like click. These events can be 

whatever we want.

Example: Return to us on this module.exports in the events module is the events.emitter and that is a constructor.

We create a new variabl, lets call it myEmitter, set it equal to a new event.EventEmitter().

So now we're going to have our event emitter object stored here as myEmitter.

```
var myEmitter = new events.EventEmitter()
```

So now we can wire up events to this:

```
var events = require("events")

var myEmitter = new events.EventEmitter()

myEmitter.on(`someEvent`, function(mssg){
  console.log(mssg)
})
```

by calling myEmitter.on we can then create an event:

myEmitter.on('somEvent') we will call the event someEvent (just something meainingless for this example)

The when 'someEvent' occurs, when it ommits, then we want to do something. And thats going to be in the call back function:

myEmitter.on('someEvent', function(){})

Now if we want we can parse a parameter into this call back function. lets just say mssg.

myEmitter.on('someEvent', function(mssg){})

So when this event occurs, when it's ommitted, what we will do is log to the console a message (a string)

To emit this event:

```
var events = require("events")

var myEmitter = new events.EventEmitter()

myEmitter.on(`someEvent`, function(mssg){
  console.log(mssg)
})

myEmitter.emit('someEvent', 'The event was emitted')
```

We listend out for this event "someEvent" by saying .on we're then emitting that event .emit, we're then parsing the string as the mssg in the function.

So when it is emitted the function is fired and the mssg is logged to the console.

Another Example:

```
var events = require('events')
var utils = require('util')

var Person function(name){
  this.name = name
}

util.inherits(Person.EventEmitter)

var james = new Person('james')
var mary = new Person('mary')
var ryu = new Person('ryu')
var people[james, mary, ryu]

people.forEach(function(person){
  person.on('speak', function(mssg){
    console.log(person.name + ' said: ' + mssg)
  })
})

james.emit('speak', 'Hey, dudes')
ryu.emit('speak', ''I want a curry')

```

In this example we're going to require another cor module in Node.js. The util module which is short for utilities.

This is a utilities module which allows us to do various things. One of the things the Utils module allows us to do is

inherit certain things from objects built into Node.js or other objects. 

In the examplet we require utils, we then create a new object constructor var person = function(name){this.name = name}.

So when ever we create a new person we need to give it a name. Next we can use this var util module. So we want to inherit

the events emitter. So any person that is created using person will inherit the events emitter, so we can attach custom events to people.

To do his we type util.inherits() then parse through two things into this function. Firstly we parse the object constructor we want to inherit

something, in our case this is person, we want person to inherit something. The thing we want it to inherit is event.EventEmitter. So now

Person and anything using the person constructor will be able to have custom events attached to it.

So if we now make some people. We create james, mary and ryu as a new person.

So we can now wire up some event listeners to each new person we created using some custom events.

First we will store the three people in an array called people. Now because they are stored in an array is use the forEach() method

which is a javascript method that will cycle through each item in the array. For each one we will fire the callback function and it will

take the parameter of person as each item in the array then inside the function we will attach some listeners for events - person.on('speak').

So here we are taking which ever person is currently being parsed through the event and attaching a listner to it. Then as we attach the custom

event to each person as we go through the array we will declare a callback function which will take in a messg (something that they say).

So when we emit these speak events on each person it will fire the callback function take through a mssg the it will log who spoke then the mssg.

So finally if we call some events such as james.emit('speak', 'Hey, dudes'). So we can emit that event on which ever person we make that is in

the array. 

#### Reading and writing files video 9

Node can read and write files on our computer. To do this we use one of nodes cor modules called fs. 

So firstly we will creat the variable and require fs.

```
var fs = require('fs')
```

As previously mentioned it's general practice, typical naming convention, to call the variable the same as the module name.

So what can the fs module do for us?

In this tutorial we will focus on reading and writing files. 

First lets create a file to read. readMe.txt. And enter some text... yay, you read me!

now to read the file we type. fs.readFileSync() this is the method that we're going to use on this fs module that can go out and

read the file we created.

example inside app.js
```
var fs = require('fs')

fs.readFileSync()
```

fs.readFileSync() naming is node being very explicit in it's methods name, this is a syncronos method. Meaning that if we had

any code below fs.fileSync() its going to go out and fully read this file before it goes out and reads any other code. 

Essentially it's blocking the flow of the code until fs.fileSync() is complete. There is also an async version of this which

we will look at later on.

We need to parse through a couple of parameters the first being the file itself. This can either be the full path to the file or 

becuase its in the same folder as app.js we can just write the file name - readMe.txt

The second parameter i'm gonna pass through is the character encoding because we're dealing with binary data here. When we go out 

and read a file we're dealing with binary data - 0 and 1. The character encoding is going to go out and determine what those 0 and 1 mean.

In this case the character encoding is going to be utf8.

```
var fs = require('fs')

var readMe = fs.readFileSync('readMe.txt', 'utf8')
console.log(readMe)
```

We have stored the result of this in a variable. Loggin the readMe variable display the text of readMe.txt.

To recap the fs module has gone out and read the readMe.txt file syncronously using the utf8 encoding to store the file content

in the varibale readMe which we have then logged to the console.

Now lets look at how we can write a file. 

What we will do is read the readme.txt file first store it in the readMe variable then take the content of that variable and

write it to a new file. 

First lets us another method on the fs module called fs.writeFileSync(). Again this is a syncronous operation.

As the parameters we need to say first where we want the file to be written to (a file will be created called writeMe.txt) 

and then secondly the data we want to write to this writeMe.txt file (this is the data stored as readMe).

```
var fs = require('fs')

var readMe = fs.readFileSync('readMe.txt', 'utf8')

fs.writeFileSync('writeMe.txt', readMe )
```

When we run the application we see a new file created called writeMe.txt and the content will be the same as readMe.txt

To recap:

We have read a file syncronously and stored the content of that file in a variable. Then once that is complete we have used 

a second method on the fs module writeFileSync() to create a new file writeMe.txt and made the content of that file the data

we stored in the variable which was created to read the original file var readMe. 

The asyncronous versions of these methods.

Firstly we can get rid of the variable and remove the sync part. 

Example

```
fs.readFile("readMe.txt", "utf8")
```
Now this will an asyncronous method, because this is asycrounous we need a callback function to fire when the process is complete.

That is the third parameter in this method.

```
fs.readFile("readMe.txt", "utf-8", function(err, data){
  console.log(data)
})
```

We use a function which takes 2 parameters, first an error if there is one and the sencond the data we retrieve and read from the file.

For now inside the function we will log to the console the data that we retieve.

The benefit of this is that we are not blocking the code. While this is being read the rest of the code can still be processed. It is 

Asyncronous. We can do the same thing with write file. We will do it inside the function as we only want to write the file once the read

file is complete.

```
fs.readFile("readMe.txt", 'utf8', function(err, data){
  fs.writeFile("writeMe.txt", data)
})
```

#### Creating / removing directories video 10

First lets look at how we delete files with fs.

We use a method called unlink. We call it with fs.unlink("") and then parse in the file name we wish to delete. 

In this example the file we want to delete is writeMe.txt. So if we run the file you we see the writeMe.txt gets deleted.

```
var fs = require("fs")

fs.unlink("writeMe.txt")
```

You need to be careful, if we run the program again we get an error as it will state no such file exists.

Creating directories:

We can either create directories syncronously or asyncronously.

The syncronous version:

we create a directory using the fs module. We create the directory writing mkdir. We then follow this with Sync() to state this is a syncronous method.

We then parse the name of the directory we want to create in this example we create stuff.

```
var fs = require("fs")

fs.mkdirSync("stuff")
```

To delete directories we run rmdir - this is remove directory.

```
fs.rmdirSync("stuff")
```

Do these syncronously will block the code, generally we would want to perform these asyncronously.

Now to make these method asyncronously we simple remove the sync word.

Remember when we use asyncronous methods we should use a call back function to do something once this action has been completed.

We can parse this callback function through here as the second parameter. In this example we will read the readMe.txt file.

We use the fs.readFile method parsing in the file we want to read and the utf8 encoding, then we fire a callback function once 

this is complete. In the call back function we parse error as the first parameter and then the data we recieve. The data we recieve

we are going to parse through into a new file which will be in the new directory we create. We do this writing the fs.writeFile() method.

We tell it where we want the new file to be using the file path and then give it the name we want to call the file. 

secondly we tell it what we want to write to the file, in this case it is the data.

fs.writeFile("./stuff/writeMe.text", data)

```
var fs = require("fs")

fs.mkdir("stuff", function(){
  fs.readFile("readMe.txt", utf8, function(err, data){
  fs.writeFile("./stuff/writeMe.txt", data)
  })
})
```

Now when we run the file you will see, first it creates the stuff directory, reads the readMe.txt, creates the writeMe.txt inside the

stuff directory and places the content / data it copied from the readMe.txt file into the content of the writeMe.txt file.

Now if we wish to delete this directory asyncronously we type:

```
fs.rmdir("stuff")
```

If we run this node will error, it will state, the directory is not empty. This is because it has writeMe.txt inside it.

We cannot remove a directory without it being empty.

So first we need to use the fs.unlink() method to remove a file. fs.unlink("./stuff/writeMe.txt")

We do this and parse in a call back function  which once the writeMe.txt has been removed will remove the stuff directory using 

the fs.rmdir() method.

```
var fs = require("fs")

fs.unlink("./stuff/writeMe.txt", function(){
  fs.rmdir("stuff")
})


```

#### Clients and servers video 11

When we browse a website in a browser we might might request some data, at which point the client which is the browser sends a request 

to the server, the server will then handle that request and send a response to the client which in most instance will update what we see.

How do the client and server communicate with each other? This is done through a protocol.

A protocol is a set of communication rules, that two wides agree to use when communicating.

Each computer or server can be identified by its own unique ip address. If a client wants to make a request to a server then it will need

to connect to the server ip address. To do this it will open up a socket between the two computers. Essetially this is a channel with which

the communication can take place. The information which is sent is structured via differnet protocols. For example http or ftp.

These protocols are like the different langauge that both the client and server can speak. Think example a german and italian person need

to talk neither speak each others langauge but they both speak english, therefor to communicate they speak in english.

Dependant on what the client and server are trying to communicate they will use a different protocol to structure the data or information

that needs to be sent.

So ftp is for file transfer and stands for file transfer protocol. 

http is used for websites.

Once the structure of the information/data has been decided upon, for example http, the infromation is then sent down the socket between

the two computers via a protocol called TCP, so although the data is structured in a particular way, the way that it is sent from the

server to the client is via the TCP protocol. What this essentially does is split up the data into smaller little sections and

transfers them along the socket. The small sections are called packets. All of this functionality is built into our computers

and then node.js gives us a the ability to access this functionality to open the connection between two computers and send information 

between them. So if we run node.js on a server we can tell node what information we want to send out to clients when they make a 

particular response.

Ports:

A program running on a computer can listen for requests sent to a particular port number.

E.g 172.24.86.76:3000

When we send a request to a server, which node.js is living on, how do we know that the request was meant for node.js itself and not 

some other program which is also running on the server instead (like an email progam for example). How do we know we want node.js and

not the email program or any other program to deal with that request? The answer is that node.js and other programs running on the server

all listen to a particular port number, so if a request is sent to an ip address to a particular port number on that ip, if node.js is 

listening out for requests on that port it will respond, otherwise it won't. This is how we route our requests to node.js.

A typical port will look like the example above. We have the ip address 172.24.86.76 and on that computer a variety of different programs 

and then node.js might be listening to a particular port, i.e 3000, so if we send requests to this port, 3000, then it is going to be 

listening to that port and it is going to send response to us.   

#### Creating a server Video 12

Making a server in node.js. We will then make a request to that server and deal with that request in node.js.

We need to use a node.js cor module called the http module.

```
var http = require("http")
```

Now we can use a method which is given to us on this cor module to create our server. The createServer() method

```
var http = require("http")

var server = http.createServer()
```

Next we need a way to deal with any requests that come into the server. To do this we parse a function through our createServer Method.

```
var http = require("http")

var server = http.createServer(function(request, response){
  
})
```
The way this works is that whenever we send a request to this server then this function is going to fire. Inside the function we have taken the

two parameters, a request object and a response object. The request object is loaded with details about the request that has been made, the response

object is something we can use to send a response back to the client. 

Lets talk about how we do that as well as headers.

So when we make a request to a server and when we respond then as well as responding with some data/information we also respond with response headers 

and on the request we can send request headers. You can think of headers as extra information about the request or the response.

This is much like in an HTML page you have a head section, which tells the browser a little bit more about the HTML document but it's not actually

shown on the browers, well thats a little like the headers in the response and the request. The kind of thing we can put in this header are 

the content type so the browser knows what to expect, wheter that's going to be plain text or html or json as it will deal with each one in a different

way. For example it renders html on a page in a browser it doesn't do that with plain text. We can also put a status in the response headers, this is 

something like 200 which means everything is ok, or 404 if the page can't be found. 

So lets go ahead and create these response headers first of all and then we will serve up some information.

The way we write the response header is: response.writeHead() we then write the first parameter as the status and then we will parse through an

object and in here we'll enter "Content-Type":"text/plain". This is so the browser knows what to do with this content!

```
var http = require("http")

var server = http.createServer(function(request, response){
  res.writeHead(200,{"Content-Type":"text/plain"})
})
```

The next thing to do is end the response and send it to the browser. To do that we use a method called end on the response object. Inside the end 

parenthesis we can send back some information/data. We've said we're going to send back plain text so that's what we'll send "hey ninjas"

```
var http = require("http")

var server = http.createServer(function(request, response){
  response.writeHead(200,{"Content-Type":"text/plain"})
  response.end("Hey ninjas")
})
```
So here we're sending back the headers and the response body itself. So if I was to now make a requestby going to my localhost this still wouldn't work

and thats because we hae not specified a port number to listen to. We need to set up node.js to listen a particular port for requests.

If we don't do that before we send requests it won't be listening for them. We do that by selecting our variable and running the .listen() method.

Inside the parenthesis we first specify the port we're going t0 listen to. Here we use 3000. Then we'll put in the ip address which is

127.0.0.1 this is just the localhost because this is going to be a local server.

```
var http = require("http")

var server = http.createServer(function(request, response){
  response.writeHead(200,{"Content-Type":"text/plain"})
  response.end("Hey ninjas")
})

server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")
```

So now we're listening to this port on this ip address so when we get a request ot this port then it is going to respond. It going to find the

function. It is also a good idea aswell, when we're listening to a port, to log a message in the terminal.

If we now run this in node by typing node app in the terminal. If we then go to 127.0.0.1:3000 in the browser we will see the content "Hey ninjas".

If we inspect and open the network tab, if we refresh we can see the requests, I we then click on the request  we can see the response. If we go 

to headers we can see the headers that we have set. 

#### Streams and Buffers Video 13







