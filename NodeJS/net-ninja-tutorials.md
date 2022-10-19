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

Buffer: 

Temporary storage spot for a chunk of data that is being transferred from one place to another.

The buffer is filled with data, then passed along.

Transfer small chunks of data at a time.

Stream: 

It is a stream of data that flows over time from one place to another. 

Buffers and streams allow us to start consuming data before it all arrives.

Why do you need to know this?

Can create streams to read and write files in node.js to transfer data. We can increase performance.

This is also true when dealing with requests from our server and we're sending data back to our client to be consumed.

#### Readable Streams Video 14

Streams:

Writable streams - allow node.js to write data to a stream.

Readable streams - allow node.js to read data from a stream.

Duplex - can read and write a stream.

For this example we have used the code form previous video, commented out as it will be needed.

First we're going to look at creating a read stream. There is also a readMe.txt file created with lorem ipsom inside.

The readMe.txt is what we will be reading in the readable stream. 

To create our read stream we need to use the fs core node module. We use this module to read a file. This time we're reading it through a stream.

First we need to get that module var fs = require("fs")

To create a readable stream we need to use a method called createReadStream

We store it in a variable var myReadStream = fs.createReadStream()

What we need to do is specify and tell node.js which file we want to read through this stream. We want to read readMe.txt

To do this we will use the 

__dirname 

property on the global object which will get me my current directory we will then concatinate it with the file name.

We will now create a read stream which will read this file. 

What will happen is we're going to read this a little bit at a time. It will find the readMe.txt data then this data will be read a small amount at

a time through the stream it will then fill up the buffer then that buffer is going to parse that data on in chunks to this variable.

We can recognise when we recieve one chunk of data. We can to that because this createReadStream inherits from the event emitter.

There is an event called data on the createReadStream which allows us to listen for whenever we recieve any kind of data or any kind

of chunk of data from this stream. We will set up a listener that will listen out for that and then fire a function everytime we recieve something.

myReadStream.on('data', function(chunk){
  console.log("new chunk recieved")
  console.log("chunk")
}) 

and this data is called a chunk. If we now run this in node,  we will see the log. 

You will see the chunk is just a buffer it is not the text itself we're not reading it. This is because we have not specified the character encoding.

utf8 needs to be specified. 
```
var myReadStream = fs.createReadStream(__dirname + "/readme.txt", "utf8")
```

By making utf8 as the character encoding we will now see the text that we want.





```
var http = require("http")

var fs = require("fs")

var myReadStream = fs.createReadStream(__dirname + "./readMe.txt", "utf8")

myReadStream.on('data', function(chunk){
  console.log("new chunk recieved")
  console.log("chunk")
}) 

//var server = http.createServer(function(request, response){
//  response.writeHead(200,{"Content-Type":"text/plain"})
//  response.end("Hey ninjas")
//})

//server.listen(3000, "127.0.0.1")
//console.log("yo dawgs, now listening on port 3000")
```

#### Writable Streams Video 15

We will create a writable stream so we can send data along that to somehwher else.

In the last tutorial we created a read stream and we read readMe.txt, we listend out for the data event and fired a function whenever we

recieved a piece of data. Now we're going to create a writeable stream so that we can write this data that we recieved to that write stream 

and send it somewhere else. To do that we create a variable called myWriteStream and set this = to fs. and use the method called 

createWriteStream(). Now we need to tell it where we want to create it to. Where is the data going to. So we want to create a write me text file 

so are variable will look like this:

```
var myWriteStream = fs.createWriteStream(__dirname + '/writeMe.txt')
```
So this has created a write stream which we can write on to and send data to the path /writeMe.txt.

But how do we do that? We will do that everytime we recieve a new chunk of data from the read stream.

so we will read:

```
var myReadStream = fs.createReadStream(--dirname + '/readMe.txt', 'utf8')
```

and then eveytime we recieve a chunk of data:

```
myReadStream.on('data', function(chunk){
  console.log('new chunk recieved')
})
```
it will fire the function so now we can write the chunk of date to the write stream and send it to the new location writeMe.txt.

We do that using the myWriteStream variable that we stored the write stream in. We use that in the myReadStream.on function.

We then use a method on it called write() then in the parenthesis we put the data we want to write, in our case it is chunk.

```
var http = require("http")
var fs = require("fs")

var myReadStream = fs.createReadStream(__dirname + '/readMe.txt', 'utf8')
var myWriteStream = fs.createWriteStream(__dirname + '/writeMe.txt', 'utf8')

myReadStream.on('data', function(chunk){
  console.log('new chunk recieved')
  myWriteStream.write(chunk)
})
```
Step by step

We are reading this file readMe.txt by ctreaing a read stream

Everytime we recieve a chunk of data we fire a function as we have an event listener myReadStream.on

When we get that chunk of date we log to the console.

Then we are calling the write stream we created myWriteStream which can write to the path /writeMe.txt

When we call the write stream we say go ahead and write to it and the data we want to write to it is the chunk of data we just recieved.

So if we run the program now you will see it create the writeMe.txt and it will write the data to it.

There is another way to do this which is even quicker and that is by using pipes. 

#### Pipes Video 16

Becuase reading data from a read stream and then transfering that data to the write stream is very common in node.js therefore node has created a 

more elegant way to do it. That is by using pipes.

Currently we a recieving data down a stream, we're filling up a buffer, when it is full it sends on a chunk of data, then we're manually listnening

out for this event when we recieve the data. We then get that chunk of data and manually write it to our write stream and send it somewhere else.

A pipe can help us do exactly the same thing. Take data from a read stream and then pipe it into a write stream. 

Once the buffer sends out the data instead of manually listening for it when we recieve the chunk of data the pipe just automatically does that for us.

It then pipes it to the write stream that we want to send our data to. So we don't have to manually llisten for the data event and we dont have to 

manually write to a write stream the pipe does that for us.

So how doe we do this in the code:

We still need to create a read stream to read date from.

And we still need to create a write stream because that is where we will write the data.

The change is where we are manually listening for the data event and writing to the stream.

So we remove that part of the code and instead on the readable stream we can use a method called pipe.

myReadStream.pipe()

We can only use this method on readable streams because we are piping from a readable stream to a writabel stream.

Thats the whole act. We can't pipe from a writeable stream as it can't read from that.

So we need to pipe the data from the readable stream to the writeable stream. 

```
myReadStream.pipe(myWriteStream)
```

All the code we wrote before is doing the same thing. Our code should now look like:

```
var http = require("http")
var fs = require("fs")

var myReadStream = fs.createReadStream(__dirname + '/readMe.txt', 'utf8')
var myWriteStream = fs.createWriteStream(__dirname + '/writeMe.txt', 'utf8')

myReadStream.pipe(myWriteStream)
```

So now we will return to the server we created a few tutorials back.

```
var http = require("http")
var fs = require("fs")

var myReadStream = fs.createReadStream(__dirname + '/readMe.txt', 'utf8')
var myWriteStream = fs.createWriteStream(__dirname + '/writeMe.txt', 'utf8')

myReadStream.pipe(myWriteStream)

var server = http.createServer(function(request, response){
  response.writeHead(200,{"Content-Type":"text/plain"})
  response.end("Hey ninjas")
})

server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")

```
Because we're going to use the idea of piping from a readable stream to a writable stream to send data to a user.

The last time we created a server we sent back some plain text and the plain text was "Hey ninjas"

So what if we want to send back the content of this readMe.txt. Well we can read from the file and write to the writable stream

response.end and send it to the data. We can do that where we liten for data events or we can use the pipe method.

So we need to take our code and past it into our server variable:

```
var http = require("http")
var fs = require("fs")

var server = http.createServer(function(request, response){
  response.writeHead(200,{"Content-Type":"text/plain"})
  
  var myReadStream = fs.createReadStream(__dirname + '/readMe.txt', 'utf8')
  var myWriteStream = fs.createWriteStream(__dirname + '/writeMe.txt', 'utf8')
  myReadStream.pipe(myWriteStream)
  
  response.end("Hey ninjas")
})

server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")

```

So currently we are reading our data myReadStream and Writing the data myWriteStream to writeMe.txt. But we don't want to do that.

We want to send it to our client. We want to send it to our response stream. Remember the response object is a writable stream

which we can write data to. 

So we can remove:

```
var myWriteStream = fs.createWriteStream(__dirname + '/writeMe.txt', 'utf8')
```

and instead of piping it to my write stream we pipe it to the response.

```
myReadStream.pipe(response)
```

and now we can get rid on the repsonse.end("Hey Ninjas") as myReadStream.pipe(response) will end the response.

It sends data down the stream to the client. Now if we save it and run it and go to port 3000 we will see all the data we read and wrote. 

We have sent the data down a stream which is much better for perfomance than reading the whole file and then sending it.

To recap, we created a server, we have a request object and response object, this response object is a writable stream so we can write to it.

We then wrote our response headers saying writeHead setting the status to 200 and setting the content type text/plain because that is

what we're reading. We then create the read stream which uses the fs module to create a read stream and reads the contents of the file. We

also specify the utf8 encoding so we get it back in the expected characters. We have then taken that read stream and piped it into the response 

stream and that is doing all the heavy lifting for us listening to that data event and whenever we get data streaming it to the user bit by bit

so they recieve data quicker. 

#### Serving HTML pages Video 17

we create an html page index.html.

Similar to the previous code, however we make some changes.

We change the content-type to text/html so then the browser knows what to do with html.

We change the file we are reading to /index.html

The code will read as:

```
var http = require("http")
var fs = require("fs")

var server = http.createServer(function(request, response){
  response.writeHead(200,{"Content-Type":"text/html"})
  
  var myReadStream = fs.createReadStream(__dirname + '/index.html', 'utf8')
  myReadStream.pipe(res)
})

server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")
```

#### Serving JSON Video 18

On The last tutorial we sent html to the browser to the client, we did that via a read stream and then piping it to the response.

In this tutorial we will send back some json insteaad. This time we will not use streams. I'm just going to send it to the response object

directly by using the end method. So how do we do this!

We currently have this code set up.

```
var http = require("http")
var fs = require("fs")

var server = http.createServer(function(request, response){
  response.writeHead(200,{"Content-Type":"text/html"})
  
  var myReadStream = fs.createReadStream(__dirname + '/index.html', 'utf8')
  myReadStream.pipe(res)
})

server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")
```

First we need to chnage the content-type to application/json because this is what we are sending to the browser.

Next lets create an object with some properties that we want to send back as json: var myObj = {name: "Ryu", job: "ninja", age: 29}.

Now that we have our object we want to send this back as json to the client. We do that coding: response.end() now wecant just enter myObj into

the parenthesis as .end expects either a string or a buffer and are object is neihter of those its an object. So we need to turn it into a string

and that string needs to be in json format. We can do that using JSON.stringify. So we have response.end(JSON.stringfy(myObj)).

If we now run that code we will see returned in the browser on localhost:3000 we will see all that data returned to us as json a json string.

```
var http = require("http")
var fs = require("fs")

var server = http.createServer(function(request, response){
  response.writeHead(200,{"Content-Type":"application/json"})
  var myObj = {
    name: "Ryu",
    job: "Ninja",
    age: 29
  }
  
  response.end(JSON.stringify(myObj))
  
})

server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")
```

So why would we want to return some json to someone? Why would someone request this in a browser? Imagine we had some javascript running on the

front end of our applicstion in the browser. Now that javascript might make this request, not in localhost:3000 and this string may be an API endpoint

thats going to return som json. Imagine the request was to localhost:3000/api/ninjas and its going to send us back this data. Now we've not done routing

in this tutorial but just imaging this url returned the json then we can return that to the front end javascript in the browser so then it can 

do something with that json. It could output that json to the screen in a particular area in the html and update the view for the user. And thats 

why we do it typically.

#### Basic Routing Video 19

```
var http = require("http")
var fs = require("fs")

var server = http.createServer(function(request, response){
  console.log("Request was made: " + req.url)
  response.writeHead(200, {"Content-Type":"text/plain"})
  response.end("feed me popcorn")
  
server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")
})
```
Here we have a server set up and when we make a request to this server we're writing our headers on the response object and then we're ending the

response by sending a string "feed me popcorn". And you can see the Content-Type is set to text/plain. So if we run this we will see in the browser

on localhost:3000 the string "feed me popcorn". It  doesn't matter what url i put, for example - localhost:3000/api, we will still have the string

shown on the page in the browser. So no matter what request I make i am getting the same data feed back. In a real world application we will want

to distinguish between differnet url's and send them data dependant on what they are requesting. For example if the request localhost:3000/home

we will want to send them the index page / home page. or localhost:3000/contact we would want to send them the contact page. And if the request

localhost:3000/api we will want to send them some data. To do this we need to set up a routing system in node.js. If you notice in the code when ever

we make a request to the server we logging to the console and we're accessing a property on the request object called url. So we are listening to what

ever the user is typing into the address bar and we can log that to the console. So we know what they're requesting, therfore we can use this to

check what they've requested and then send them data dependant on that request.

So lets do that, let's get rid of this response and do a simple if statementto check what they're requesting and then send them something 

dependant on that request. We will say if the request .url is strictlly equal to "/home" or if request .url is strictly equal to just "/"

then we want to send them the index.html file. So lets do that - we write our request headers with the status and the Content-Type, we then need to

create a read stream to read this file we tdo this with fs.createReadStream and parse the file we want to read in the current directory and

concatinate it with /index.html we then need to pipe that to the response object and that will send it to us.

So in our code we have

```
var http = require("http")
var fs = require("fs")

var server = http.createServer(function(request, response){
  console.log("Request was made: " + req.url)
  if (request.url === "/home" || request.url === "/"){
    response.writeHead(200, {"Content-Type": "text/html"})
    fs.createReadStream(__dirname + "/index.html").pipe(response)
  }
  
server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")
})
```
Now in the browser if we go to localhost:3000/home then we should get the homepage.  However if we type anything else the browser will 

time out after searching as it can't find anything. So we can specify some more routes. We do this by folling up our if statement with 

else if.

```
var http = require("http")
var fs = require("fs")

var server = http.createServer(function(request, response){
  console.log("Request was made: " + req.url)
  if (request.url === "/home" || request.url === "/"){
    response.writeHead(200, {"Content-Type": "text/html"})
    fs.createReadStream(__dirname + "/index.html").pipe(response)
  } else if(request.url === "/contact"){
    response.writeHead(200, {"Content-Type": "text/html"})
    fs.createReadStream(__dirname + "/contact.html").pipe(response)
  }
  
server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")
})
```

We have set up a route to our contact.html page. If we go to the browser and search either localhost:3000/home or localhost:3000/contact we 

will be served the relevant page.

So what if we want to send back some json instead. Like some kind of api endpoint. We can create another else if and do that:

```
var http = require("http")
var fs = require("fs")

var server = http.createServer(function(request, response){
  console.log("Request was made: " + req.url)
  if (request.url === "/home" || request.url === "/"){
    response.writeHead(200, {"Content-Type": "text/html"})
    fs.createReadStream(__dirname + "/index.html").pipe(response)
  } else if(request.url === "/contact"){
    response.writeHead(200, {"Content-Type": "text/html"})
    fs.createReadStream(__dirname + "/contact.html").pipe(response)
  } else if(request.url === "/api/ninjas"){
    var ninjas = [{name:"Chris", age: 39},{name: "Louise", age: 40}]
    response.writeHead(200, {"Content-Type": "application/json"})
    response.end(JSON.stringify(ninjas))
  }
  
server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")
})
```

We have set our else if with the endpoint "/api/ninjas" then inside created a variable = to an array of objects. In each object we give the

properties of name and age. In a real world application we would get this data from a database rather than just difining it here. So were going to

send this data as json to the browser to the client. First we set response.writeHead to status 200 and content type to application/json. Now lets

send that to the browser with response.end. Remember .end expects a string or a buffer so we need to stringify the json we send. If we save and run

search for localhost:3000/api/ninjas we will get the json data back. 

So we have set up several routes. However still if we search for something that is not set up then we won't get anything back. Ideally what we want

to do is send the user a 404 page to say we have not found what you're looking for. To do that we will set up a catch all at the bottom.

We will do this in an else at the end of the if else statement. So if the user has typed in anything else other than the routes we have specified

then we'll send a 404 page.

```
var http = require("http")
var fs = require("fs")

var server = http.createServer(function(request, response){
  console.log("Request was made: " + req.url)
  if (request.url === "/home" || request.url === "/"){
    response.writeHead(200, {"Content-Type": "text/html"})
    fs.createReadStream(__dirname + "/index.html").pipe(response)
  } else if(request.url === "/contact"){
    response.writeHead(200, {"Content-Type": "text/html"})
    fs.createReadStream(__dirname + "/contact.html").pipe(response)
  } else if(request.url === "/api/ninjas"){
    var ninjas = [{name:"Chris", age: 39},{name: "Louise", age: 40}]
    response.writeHead(200, {"Content-Type": "application/json"})
    response.end(JSON.stringify(ninjas))
  } else{
    response.writeHead(404, {"Content-Type": "text/html"})
    fs.createReadStream(__dirname + "/404.html").pipe(response)
  }
  
server.listen(3000, "127.0.0.1")
console.log("yo dawgs, now listening on port 3000")
})
```

You'll see we can still send something, we can set up a 404.html page which will be sent. If we run the application and enter a url endpoint 

that is not specified we will be served the 404.html page.

#### The node package manager Video 20

For short the node package is known as npm.

In the last tutorial we looked at basic routing, this coudl become tiresome. Fortunately there is a package called express that will really 

help us slim this down and create web applications on node. To do that we need to know about the node package manager. 

The npm comes installed with node.js when you installed that. It is basically a just a bunch of command line tools which can help us install

third party packages or modules to help out with our node projects. Express is one of these packages and there are many more.

A node package is essentially a bunch of code that someone else has written and it helps us perform a certain type of task within node.js

applications. For example the express package helps us with routing and templating and such. The idea is that we can load these packages into

our node application and then use thier functionality in our code. The way we do that is using the npm. Using the npm we can install packages

update packages or even publish our own pakages for other people to use. On the npm website www.npmjs.com

Here we install express using npm install express in the terminal. You will see a huge number of pakages have been installed and express is amongst

them. The extra files are dependencies, Express depends on these other modules - node has recognised that and installed the other pakages for us

aswell. We don't need to work with these other packages directly, we've just installed express the other modules were installed with it so express 

can work properly. Now we can use express in our application.

As we're not going to do that yet we will uninstall express to do that we enter the command npm uninstall express  into the terminal. 

#### Package.json Video 21

In the last tutorial we talked about npm and how we can us it to install packages into our application.

You can install one package you can install 10 packages but either way it is a good idea to keep track of which packages your installing and

which packages your application depends on. The dependencies your application depends on. In node.js we can do that. We can use a package.json

file to keep track of all of those packages that we depend on. We can either create this manually or we can use a command in node.js to do it for us.

to do this we enter the command npm  init. When we run this is will ask us several questions about our project. First it asks for a nam, it will

suggest a default, it will then ask us what version, version 1 will be default thats fine, it will then ask us for a description which we can fill in.

It will the ask us for the entry point of our application, default will be app.js this is fine, it will then aska test command, we don't have one of

those thats fine git repository just hit enter, keywords you can fill in, author enter you. Licence is fine as it is. Is this ok? yes. Answering all

these will go ahead and create a pakage.json file. One of the cool things about this package.json file is that it can keet track of our dependancies

that we need to run our application. Say we install some packages and our application depends on those, now if we pass on our code to another developer

we don't normally pass on the packages aswell, just our core application code that we have written. For that developer to run our application the will

need to install the same packages that we did becuase our application depends on them. They know what packages to install as they are listed in the 

package.json file. How do we add them to this file how does it keep track of it. When we install a package in node.js using the npm we can pass through

a save flagand that will save that pakage as a dependency in the package.json file.

So if we install express again - npm install express -save - this is to say look this is a dependancy. 

It will go ahead and install express as normal, then once it has installed express it will update the package.json file. You will see 

dependencies listed and express as an item in the list on the package.json file.

Now if we unistall express npm uninstall express. This will remove all those files express is now uninstalled. However you will notice express 

is still listed in our dependencies. The reason it does that is because even though we don't have express installed we have listed it as a 

dependency so it is telling us we need to install this for our application to work. To unlist it as a dependancy we just unlist it.

Now lets say we have a list of dependencies and we pass our code on to another developer, if they want to install all of the ses pakages

they don't need to do them all manually. They can use one command which is npm install. When we run this node will look for this package.json

file, find the dependencies and every dependency list will install into the version they're running. 

#### Installing Nodemon Video 22

Now we know how to use the npm and how to install pakages. Before we start with express I want to install nodemon.

Nodemon is a package for when you're developing, what it does is monitor your application files so when it is running in a browser and

we're listening to a server, if we make a change in a file, nodemon will monitor that so when we save the file it restarts the server 

automatically for us.

When you install it you can install it with a g flag: npm install -g nodemon. This g flag means we are installing it globally.

This means no matter what application we work with on our computerwe can use nodemon. 

So if we install using npm install -g nodemon we will not see the files on VSCode as they will install somewhere else globally.

the way this now works is instead of running npm start / node app to run our application we run nodemon app.js on. 

Note: we have currently been using nodemon server in the server on the terminal to run our application.

This is a much better way of working as we it refreshes everythime we save with out having to enter any commands for it to work.

#### Introduction to express Video 23

Express
  
  - Easy and flexible routing system
  - integrates with many templating engines
  - contains a middleware framework

We're going to start afresh from the code in previous tutorials and create an express app.

make sure express is installed npm install express -save to save it in the dependencies.

The first thing we need to do to use express is require it in our code. Express is jsut a module written in javascript which we can 

use in our application. So to require this we enter the following code into our server.js.

const express = require("express")

We now have access to this module. What we need to do next is set up what is known as an express app. That way we get acces to all of the

functionality that express comes baked with. To do that we store it in a variable called app:

const app = express()

App equals express invoked because what is returned to us, on module.exports in this module, is a function. So we go ahead and fire that function

when we call app so then we have access to all of the different methods on express which help us with things such as routing.

Now we also need to listen to a port. To do this in express we use:

app.listen()

We give app.listen a port number, so app.listen(3000) so we are now listening oon port 3000.

In the code so far we have our express app running and now we're listening to a port. but how do we respond to requests?

When we set up the app variable we are given access to a variety of mehtods on it that can help us respond to requests.

These methods all corresspond to the type of requests being made. They are what is known as http verbs or methods.

Http methods are the types of requests we make. 

  - GET
  - POST
  - DELETE
  - PUT

These are all requests that wor in the same way as each other. However each different type of request contains a specific peice of information 

attached to it to say to the server what kind of request it is. Then it is up to the server to look at what type of request it is and then treat 

that type of request in a particular way.

By using express in node we can respond to each of these different types of requests very easily. The way we do that is by using the 

methods that express provides us with:

Responding to requests:

  - GET - app.get("route", fn)
  - POST - app.post("route", fn)
  - DELETE - app.delete("route", fn)

First we going to stick with the get requests, typing a url into the address bar and then getting something back from the server.

So we are listening to a port and we want to respond to a get request.  We know we can do this using app.get().

The first thing we put inside the get method is the route. So app.get("route"). What is a user going to type in so that we can respond in this 

particular way. For now lets just set the route to /. So we have:

```
const express = require("express")

const app = express()

app.get("/")

app.listen(3000)
```

Following the route we're going to fire a function when the user requests this root directory. The function will take the request object and 

response object but express has extended these objects and added additional functionality to them.

```
const express = require("express")

const app = express()

app.get("/", (request, response)=>{})

app.listen(3000)
```

So when a user goes to /it will fire the function. We can respond to it in a particular way. For now lets jsut send a string. 

to this we use response.send() and parse our string into the parenthesis:

```
const express = require("express")

const app = express()

app.get("/", ()=>{
  response.send("This is the homepage")
})

app.listen(3000)
```

If we now run this using nodemon and view in a browser we will get this string back as our repsonse.

Express has listened for this get request when it recieves that request it fires the function and on the response object 

it uses the express method .send and in this instance it sends the string.

Notice we have not specified the Content-Type here in the headers. Express is clever enough to know what this is and do it for us.

Now lets set up another route. Well listen for the endpoint of /contact and we will change our response to a string that says 

"this is the contact page".

```
const express = require("express")

const app = express()

app.get("/", (request, response)=>{
  response.send("This is the homepage")
})

app.get("/contact", (request, response)=>{
  response.send("this is the contact page")
})

app.listen(3000)
```

So in the address bar if we go to localhost:3000/contact we will see the response - this is the contact page.

You can see how much easier this is to set up a route than before without express.

Don't worry for now about just sending strings, we will look at sending html pages and other things such as json.

To recap:

We required the module express, then set up our express app setting app equal to express invoked, then we listened to a port, 

then we set up our routes using get requests with app.get, we responded to the / and then the /contact request. When we did that we fired 

the functions which take the request and response object extended by express, we used the send method on the response object to send a string.

Express identified it was a string there was no need for us to tyoe in the "Content-Type".

#### Route Parameters Video 24

At the moment we are just responding to static requests "/" and "/contact". But what if we wanted some kind of dynamic request. For example say 

we had a social network site and one particular route would be /profile/theID of that profile. Now I wouldn't want to set up a response method

to each ID seperatly. I want to recognise when someone is requesting  a profile page and then grab that id from the url so I can do

something with it. We can do that using route variables or route parameters.

So lets go ahead a create another get method which is going to respond to a particular request. Lets respond to the request /profile/:id

so we want to view a profile then we want to view the id of the profile. To do this we use a colon : then id.  So the request may be 

/profile/123 and that id may corresspond to a particular person in a database. So we can make some kind of database query and then return that

data from the database and inject is into our html and return it to the user. This is a little bit beyond the scope of this tutorial for now

we're just looking at route parameters. Once we have enetered our endpoint "/profile/:id" we will fire a function which again will take our 

request and response objects as parameters so then we can actually access this id in the endpoint //profile/:id that the user input and requested

on the request object. For now we will use the response.send method and send some text back to the user stating "You requested to see a profile

with the id of" then we will concatenate the id that the user has entered. But how do we access it? We access it on the request object by saying

request.params.id - this is callingthe request object, request. , followed by the property, params , which is going to store the :id parameter in

it, request.params. , and then we just need to state the parameter name which is id. So we have request.params.id

```
const express = require("express")

const app = express()

app.get("/", (request, response)=>{
  response.send("This is the homepage")
})

app.get("/contact", (request, response)=>{
  response.send("This is the contact page")
})

app.get("/profile/:id", (request, response)=>{
  response.send("You requested to see a profile with the id of " + request.params.id)
})



app.listen(3000)
```

If we run this and open the browser entering into the address bar localhost:3000/profile/123 it will return the response on the page:

You requested to see a profile with the id of 123

If we enter into the address bar localhost:3000/profile/678341 it will returnt the response on the page:

You requested to see a profile with the id of 678341

We have successfully accessed this parameter that we parsed through on our request by using request.params

Where we state the parameter in the endpoint, we could call it anything we like it doesn't have to be id. We could use the parameter of

name so app.get("/profile/:name"). then in our response we just change id to name also to match: 

response.send("You requested to see a profile with the id of " + request.params.name)

Now in the brower if we search localhost:3000/profile/louise 

We will see the returned response of:

You requested to see a profile with the id of louise

So this is a very cool way to set up routes when the routes are dynamic and change and it has the same structure that all profiles have.

So we are saying look for when profile is in the url the / somethingand bring me back that something on the params so I can do something 

with it, maybe query a database and then return some data dependant on it. 

#### Templating Engines Video 25



























