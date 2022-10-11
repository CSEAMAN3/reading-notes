# Module 9 working with APIs

## Intro to APIs and BoredBot

#### Video 1 - Api module intro

Bob Ziroll

We learn APIs to access real data.

Build more intersting apps

Prepare to learn full-stack

In this module:

Basics & BoredBot

URLs, REST & BlogSpace

Aysnc Javascript and War

Dasboard Capstone 

#### Video 2 - What is an API

What does API stand for? 

Application Programming interface

An API is any tool that helps connect your program with someone else's program.

Restuarant Analogy

###### Getting data from a server

The server hosts "an API" - exposed "endpoints" we can accessfor getting data from the server.

Note - the server does not give us access to everything, just the things they want us to have.

###### Pre-written code that does cool stuff

DOM API (.getElementById)

Array methods API (.filter, .map)

3rd party packages

+ many more 

This is a list of all the APIs that are available. 

https://developer.mozilla.org/en-US/docs/Web/API

#### Video 3 - Clients and Servers

###### What is a client?

Any device that connects to the internet to get data from somewhere.

The client makes requests and recieves responses.

###### What is a server?

A computer that accepts requests from the client asking for something,

then responds to the client with that thing, for example:

HTML page, an image or file, or just plain data.

#### Video 4 Requests and Responses

What is the request-response cycle?

###### What is a Request?

When a device asks for a resource (data, image, HTML page, authentication token) ect.

Requires a connection to the internet.

###### What is a Response?

The reply to the request.

Could contain the resource (HTML, JSON, data, ect.) asked for by the client.

Could contain a response saying the client isn't authorised to recieve the resource.

#### Video 4 BoredBot intro

A button and when you press it calls out to an API called the Bored API wihch gives you an

Idea of something to do incase you're bored.

#### Video 5 JSON Review

JSON stands for Javascript object notation.

JSON is called Javascript object notation because it looks like javascript.

Exmaple of JSON..

```

{
  "name": "Joe Schmoe",
  "age": 42,
  "gender": "male",
  "hobbies": [
    "skiing",
    "surfing",
    "piccolo"
   ]
}

```

You will notice a major difference between JSON and javascript is the keys in the object need to be surrounded by "".

As long as your keys are in double quotes your values can be any valid javascript. string, number, boolean.

Mostly JSON files will be a single object or an array of objects.

jsonlint.com is a great site to use to validate you have written your JSON file correctly.

You can use the inspect tool and go to network to see the network requests. See which JSON requests are taking place.

#### Video 6 First fetch

Example code:

```
fetch('http://example.com/movies.json')
.then(response => response.json())
.then(data => console.log(data));
```

changed url

```
fetch("https://dog.ceo/api/breeds/image/random")
.then(response => response.json())
.then(data => console.log(data));
```

.then recieves a function that will take a response and returns response.json
.then then console logs the data through another function.

If we run the console we see the json that is coming back:

It is an object that has two properties: A message property which has an image on it and a status property which says success.

The console
```
{message: "https://images.dog.ceo/breeds/terrier-australian/n02096294_6213.jpg", status: "success"}
```

#### Video 7 .then() and asynchronous javascript

Important to understand:

The code you write inside of your .then() function, the order in which this is executed may be different than you expect.

Example code to demonstrate

```

console.log("The first console log")


fetch("https://dog.ceo/api/breeds/image/random")
.then(response => response.json())
.then(data => console.log(data));

console.log("the second console.log")

```

As we currently understand the we would think the code would render in the following order:

The first console.log
The console.log from fetch .then(data => console.log(data))
The second console.log

however this is how the code will run:

The console will display
```

The first console log
The second console log
{message: "https://images.dog.ceo/breeds/terrier-australian/n02096294_6213.jpg", status: "success"}

```

Asynchronous means its happening out of order out of time.

The beuaty of our .then() block is they don't block the other code in your javascript program from running.

In the example they allowed the second console.log to run before the response from the fetch request ever

came back from the server.

#### Video 8 Dog API Fetch and DOM Practices

Challenge. 

Fetch a random image from the dog API again.

Access the DOM and insert the URL you got from the API as an image `src` property

(probably easiest if you create the image completely here in JS and add it as the 

innerHTML of another element in the DOM).

We need to write the fetch and parse in our URL.

Next with our then() we want to say with the response that comes back we're going to change the body

of the respnse from JSON into javascript. That is what .JSON does.

```
.then(response => response.json())
```

Then we will have access to the data. data is an object and it has a message property that can be used.

```
fetch("https://dog.ceo/api/breeds/image/random")
  .then(response => response.json())
  .then( data => {
    document.getElementById("image-container").innerHTML = `
      <img src="${data.message}" />
  }
```

#### Video 9 fetch idea from Bored API

challenge :

1) Fetch a random activity from the bored API

url: https://apis.scrimba.com/bored/api/activity

2) Display the text of the activity in the browser.


```
fetch("https://apis.scrimba.com/bored/api/activity")
  .then(response => response.json())
  .then(data => {
    console.log(data)
    document.getElementById("activity-name").textContent = data.activity
  }
```

#### Video 10 Aside - apis.scrimiba.com?

Why we're using apis.scrimba.com and not https://www.boredapi.com/api/activity

This is logistical stops the lesson becoming obsolete. The api data has been placed onto scrimba servers.


#### Video 11 BoredBot - HTML

Building html code for boredbot site.

#### Video 12 BoredBot - CSS

Building css code for boredbot site.

#### Video 13 BoredBot - JavaScript

Building Javascript code for boredbot site.

```
document.getElementById("btn-btn").addEventListener("click", function(){
  fetch("https://apis.scrimba.com/bored/api/activity")
  .then(response => response.json())
  .then(data => {
    console.log(data)
    document.getElementById("activity").textContent = data.activity
  }
})
```

#### Video 14 BoredBot - Extra styling

Uses text content to change the heading from bored bot to happy bot
Uses classList.add to add a styled classname to the body

These are added to the event listener function, inside the fetch and the .then() function after we have recieved the data.

#### Video 15 Section Recap

###### Topics Covered

Servers and Clients

Request-Response Cycle - WRRC - web request response cycle

APIs

JSON

fetch syntax

+ BoredBot project

## URLs, REST & BlogSpace

#### Video 1 Intro

###### Topics

Requests

URLs (parameters, queries)

REST API Design

+ BlogSpace project


#### Video 2 HTTP Requests

Recap request response cycle

Request - A client asks for a resource from a server

Response - A server responds (whether it worked or not) to the client.

What does HTTP stand for? Hypertext Transfer Protocol

Definition - A protocol is an agreed-upon, standard way of doing something.

HTTP is a protocol for determining how hypertext (text) should be transfered over the internet.

Components of a request:

1) Path (url)

2) Method - these include GET, POST, PUT, DELETE, PATCH, OPTIONS, ect

3) Body

4) Headers

Challenge

Send a request to the JSON Placeholder API using fetch
URL: https://apis.scrimba.com/jsonplaceholder/posts

Documentation: https://jsonplaceholder.typicode.com

log the response data to the console.

```
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
  .then(response => response.json())
    .then(data => console.log(data))
```

###### Quiz
 
 1) What does HTTP stand for?

 a. HyperText Transfer Protocol
 
 2) How would you describe what a protocol is to a complete newbie?

 a. A protocol is an agreed-upon standard way of doing something.
 
 3) Which part of this URL describes the protocol?:

  https://apis.scrimba.com/jsonplaceholder/posts
  
 a. https descibes the protocol.  HyperText Transfer Protocol Secure is https://
  
    ftp:// is the file transfer protocol
  
    SMTP is the simple mail transfer protocol 
  
 4) if you had to guess, which request method (GET, POST, PUT, DELETE) would you 
    
    think we made in the previous challenge when we asked for data from the JSON placeholder API?
    
 a. The GET Metod. fetch if no other parameters or information is provided accept for the URL 
    it will assume that you're sending a GET request to get data from this URL.
    
    
#### Video 3 URLs and Endpoints

Path (URL) - Address where your desired resource "lives"

The URL for an API can be split into two portions.

BaseURL vs. Endpoint

  Base URL: https://apis.scrimba.com/jsonplacholder
  
  The Base URL is the portion of the URL that will not change no matter what kind of resource your getting from this API.
  
  For Example: https://apis.scrimba.com/jsonplacholder this will not change.
  
  Endpoint: /posts
  
  The Endpoint is the specific resource at that base URL that I want to get.
  
  For Example: The /posts Endpoint which represents a list of blog posts that live at this API
  
  So when you put the Base URL and the Endpoint together you get the full API
  
  Full URL: https://apis.scrimba.com/jsonplaceholder/posts
  
  In many cases there are various endpoints we can access for example the jsonplaceholder API has /users or /albums.
  
  If you were to click the link above your browser would send a GET request to the URL you're linking to.
  
  If that API / URL contains an HTML pageas a resource then your browser will load it like normal.
  
  Your browser won't load an HTML page it will load is the JSON response. It's able to display that and you can see the JSON in the browser.
  
  In chrome use the extention JSON formatter.
  
  ###### Quiz
  
  1) What's the difference between a Base URL and an Endpoint?

  a. The Base URL is the part of the URL that won't change regardless of which resource we want.
  
     The Endpoint specifies which resource we want to get.
 
  ***
  Given the following URLs from an API:

    https://blahblahblah.com/api/v2/users
    https://blahblahblah.com/api/v2/products
    https://blahblahblah.com/api/v2/products/123
    
  
  2) Which part is the Base URL?

  a. https://blahblahblah.com/api/v2
  
  3) What are the Endpoints?

  a. /users, /products, /products/some id of a product here
  
    With /users and /products we would expect to get an array back as the response (array of users and an array of products)
    
    When we request /products/123 you can get a single product (an object) amongst the list products that are available.
  
  
  #### Video 3 Requests - Methods
  
  GET, POST PUT DELETE, PATCH, OPTIONS
  
  The Method is telling the server which type of request you're making / What your intention with that method is.
  
  GET Request - getting data
  
  POST Request - Adding new data / send new data to a server / database. Note I am not asking the server to send data back!
  
  PUT Request - Updating existing data. This can also add new data if the data you're trying to update doesn't exist.
  
  DELETE Request - Removing data
  
  When we use fetch as we have as we don't specify a Method it assumes you are making a GET request.
  
  Example: fetch("https://apis.scrimba.com/jsonplaceholder/todos")
  
  There is a way in the fetch API to specify the request Method. You achieve this by using a second parameter.
  
  So the first parameter is the URL or the path of where im trying to access.
  
  The second parameter is an options object. Inside the object I can specify a key called method: and tell it the value i.e the methodt type.
  
  Example: fetch("https://apis.scrimba.com/jsonplaceholder/todos", {method: "GET"})
  
  This is explicitly telling fecth to perform a GET request / set the method of the request ot GET
  
  For GET this is not nesseccary as it is the default method.
  
  However for POST:
  
  fetch("https://apis.scrimba.com/jsonplaceholder/todos", {method: "POST"})
  
  For post we would also need to include the body 
  
  fetch("https://apis.scrimba.com/jsonplaceholder/todos", {method: "POST", body})
  
  Point is we can change the method of the request using fetch by providing the second parameter.
  
  
  #### Video 4 BlogSpace - Get first 5 blog posts
  
  
  
  










