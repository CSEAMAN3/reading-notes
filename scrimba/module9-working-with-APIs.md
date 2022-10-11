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

#### Video 12 BoredBot - JavaScript

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












