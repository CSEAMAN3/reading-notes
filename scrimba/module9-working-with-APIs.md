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

The server hosts "an API" - exposed "endpoints" we can access for getting data from the server.

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
  
  Challenge:
  
  Get a list of blog posts from the JSON placeholder API
  
  BaseURL: https://apis.scrimba.com/jsonplaceholder/
  Endpoint: /posts
  
  Since there are so many posts, lets limit the array to just 5 items.
  
  You can use the `.slice()` array method to just grab the first 5 objects fromt he data
  
  array that comes back from the API.
  
  Log the 5 items to the console.
  
  ```
  fetch("https://apis.scrimba.com/jsonplaceholder/posts")
  .then(response => response.json())
  .then(data => {
    const postArr = data.slice(0, 5)
    console.log(postArr)
  })
  ```
  
  
  #### Video 5 BlogSpace - Display blogs on page
  
  Challenge:
  
  With the 5 blog post objects, display the `title` and `body` properties of the first
  
  5 posts on the browser.
  
  Hints
  
  create a `div` in the HTML file to store these items
  
  Loop over the items creating a string of HTML elements you can then put into the div with `innerHTML`
  
  
  create a div with an ID - i created .container
  
  My Solution was
  
  ```
   fetch("https://apis.scrimba.com/jsonplaceholder/posts")
  .then(response => response.json())
  .then(data => {
    const postArr = data.slice(0, 5)
    for (let i = 0; i < postsArr.length; i++){
      const heading = document.createElement("h3")
      const para = document.createElement("p")
      heading.innerHTML = postsArr[i].title
      para.innerHTML = postsArr[i].body
      container.appendChild(heading)
      container.appendChild(para)
    }
  })
  ```
  
  Scrimba Solution
  ```
   fetch("https://apis.scrimba.com/jsonplaceholder/posts")
  .then(response => response.json())
  .then(data => {
    const postArr = data.slice(0, 5)
    let html = ""
    let (post of postsArr){
      html += `
        <h3>${post.title}</h3>
        <p>${post.body}</p>
        <hr />
      `
    }
    document.getElementById("blog-list").innerHTML = html
  })
  ```
  
  The Scrimba solution is better as it is only maniuplating the DOM once 
  
  My solution is manipulating the DOM on every iteration of the loop.
  
  
  #### Video 6 BlogSpace - Add Styling
  
  Add style to the BlogSpace project
  
  
  #### Video 7 BlogSpace - New Post Form
  
  Challenge:
  
  Create a form with 2 inputs (each with an associated label),
  
  one for the post title (a text input) and one for tge post body
  
  (a text area element). Then add a button to the form.
  
  Dont worry about styling.
  
  
  #### Video 8 BlogSpace - Add style to the Form
  
  Challenge to style the form added to the BlogSpace project
  
  
  #### Video 9 BlogSpace - Form Submit Event Listener
  
  Solution:
  
  In Javascript
  ```
  document.getElementById("new-post).addEventListener("submit", function(event){
    event.preventDefault()
    const postTitle = document.getElementById("post-title").value
    const postBody = document.getElementById("post-body").value
    const data = {
      title: postTitle,
      body: postBody
    }
    console.log(data)
  })
  ```
  
   #### Video 10 Requests - Body
   
   The request body is the data we want to send to the server.
   
   The request body is only included when using a POST or PUT request.
   
   We need to make sure we turn the javascript object we're sending to 
   
   the server into JSON first.
   
   How do we include a body in our request?
   
   We need to add a second parameter to the fetch request which is an options object.
   
   The options object has options we can add such as body.
   
   The body option is an object and we include the properties of title and completed.
   
   title is a string and completed is a boolean set to false.
   
   To set the body to JSON we put our object inside JSON.stringify()
   
   
   
   fecth("https://apis.scrimba.com/jsonplaceholder/todos", {
    method: "POST", 
    body: JSON.stringify({
        title: "Buy Milk"
        completed: false;
      })    
   })
   .then(response => response.json())
      .then(data => console.log(data))


#### Video 11 Requests - Headers

  Headers are:
  
  Extra/meta information about the outgoing request.
  
  Can include information about Auth, body info, client info, ect.
  
  Just like with the body we can add a headers option to our options object.
  
  The value of the headers option is also an object and inside we can include 
  
  a value of "Content-Type" for the value we will use "application/json".
  
  This is telling the server I am sending JSON in the request body. So be prepared
  
  to take the json and parse it into javascript and do your thing with it.

  fecth("https://apis.scrimba.com/jsonplaceholder/todos", {
    method: "POST", 
    body: JSON.stringify({
        title: "Buy Milk"
        completed: false;
      })
      headers: {
        "Content-Type": "application/json"
      }
   })
   .then(response => response.json())
      .then(data => console.log(data))
      
      
 #### Video 12 BlogSpace - send new post to server
 
 Challenge: Send the form data to the server
 
 Solution:
 ```
 fetch("https://apis.scrimba.com/jsonplaceholder/posts")
  .then(response => ())
  .then(data => {
    const postsArr = data.slice(0, 5)
    let html = ""
    for (post of postsArr) {
      html += `
        <h3>${post.title}</h3>
        <p>${post.body}</p>
        <hr />
      `
    }
    document.getElementById("blog-list").innerHTML = html 
  })
 
 document.getElementById("new-post").addEventListener("submit", function(event){
    event.preventDefault()
    const postTitle = document.getElementById("post-title").value
    const postBody = document.getElementById("post-body").value
    const data = {
      title: postTitle,
      body: postBody
    }
    
 fetch("https://apis.scrimba.com/jsonplaceholder/posts", {
  method: "POST", 
  body: JSON.stringify(data),
  header: {
      "Content-Type": "application/json"
    }
  })
  .then(response => response.json())
  .then(data => console.log(data))
 })
 
 ```
 
  #### Video 13 BlogSpace - Add new post to the list of posts
  
  Solution:
 ```
 fetch("https://apis.scrimba.com/jsonplaceholder/posts")
  .then(response => ())
  .then(data => {
    const postsArr = data.slice(0, 5)
    let html = ""
    for (post of postsArr) {
      html += `
        <h3>${post.title}</h3>
        <p>${post.body}</p>
        <hr />
      `
    }
    document.getElementById("blog-list").innerHTML = html 
  })
 
 document.getElementById("new-post").addEventListener("submit", function(event){
    event.preventDefault()
    const postTitle = document.getElementById("post-title").value
    const postBody = document.getElementById("post-body").value
    const data = {
      title: postTitle,
      body: postBody
    }
    
 fetch("https://apis.scrimba.com/jsonplaceholder/posts", {
  method: "POST", 
  body: JSON.stringify(data),
  header: {
      "Content-Type": "application/json"
    }
  })
  .then(response => response.json())
  .then(post => {
    document.getElementById("blog-list").innerHTML = `
      <h3>${post.title}</h3>
      <p>${post.body}</p>
      <hr />
      ${document.getElementById("blog-list").innerHTML}
    `
  })
 })
 
 ```
 
#### Video 14 BlogSpace - Posts refactor

So things that aren't right in the above code. 

First we have duplicated our code. 

Second The operation that runs when the program loads (the first fetch which gets the data and updates the dom)

Later on we are also updating the DOM in the same way. We only have access to the list of posts that come back in

that function. Once the function ends we no longer have access to our posts array, which is why we duplicate it on

the end of our new blog post:

Solution: 

create a globalscope empty array - postsArray

inside of the first fetch

instead of creating the first variable (const postsArr = data.slice(0, 5))

set the postsArray array to data.slice(0, 5) this is the array that comes back. 

Then create a function called renderPosts whos job is to update the dom based on what the current

state of postsArray. This way the first and last fetch requests can simply update postsArray and

then call render posts.

The renderPosts function now creates an empty string, loops through postsArray and sets the html += to add the

next index. It them manipulates the DOM setting blog-list innerHTML to the html.

This process can then be removed from the first and final fetch. In the first fetch

we make the empty array = the data we get back from the response and then call renderPosts function

to render on the page. In the final fetch we unshift the data(now called post) to the array and call the function

renderPosts.

```
let postsArray = []

function renderPosts(){
  let html = ""
    for (post of postsArray) {
      html += `
        <h3>${post.title}</h3>
        <p>${post.body}</p>
        <hr />
      `
    }
    document.getElementById("blog-list").innerHTML = html 
}

fetch("https://apis.scrimba.com/jsonplaceholder/posts")
  .then(response => ())
  .then(data => {
    postsArray = data.slice(0, 5)
    renderPosts()
  })
 
 document.getElementById("new-post").addEventListener("submit", function(event){
    event.preventDefault()
    const postTitle = document.getElementById("post-title").value
    const postBody = document.getElementById("post-body").value
    const data = {
      title: postTitle,
      body: postBody
    }
    
 fetch("https://apis.scrimba.com/jsonplaceholder/posts", {
  method: "POST", 
  body: JSON.stringify(data),
  header: {
      "Content-Type": "application/json"
    }
  })
  .then(response => response.json())
  .then(post => {
    postArray.unshift(post)
    renderPosts()
  })
 })


```

#### Video 15 reset the form

Add code to the final fetch to clear the inputs.

Solution:

Create global variable titleInput and bodyInput

Change where we hav used the selectors

Then change the value to be an empty string at the end.

```
let postsArray = []

const titleInput = document.getElementById("post-title")
const bodyInput = document.getElementById("post-body")

function renderPosts(){
  let html = ""
    for (post of postsArray) {
      html += `
        <h3>${post.title}</h3>
        <p>${post.body}</p>
        <hr />
      `
    }
    document.getElementById("blog-list").innerHTML = html 
}

fetch("https://apis.scrimba.com/jsonplaceholder/posts")
  .then(response => ())
  .then(data => {
    postsArray = data.slice(0, 5)
    renderPosts()
  })
 
 document.getElementById("new-post").addEventListener("submit", function(event){
    event.preventDefault()
    const postTitle = post-title.value
    const postBody = post-body.value
    const data = {
      title: postTitle,
      body: postBody
    }
    
 fetch("https://apis.scrimba.com/jsonplaceholder/posts", {
  method: "POST", 
  body: JSON.stringify(data),
  header: {
      "Content-Type": "application/json"
    }
  })
  .then(response => response.json())
  .then(post => {
    postArray.unshift(post)
    renderPosts()
    post-title.value = ""
    post-body.value = ""
  })
 })
```

Alternatively we can use .reset()

```
let postsArray = []

const titleInput = document.getElementById("post-title")
const bodyInput = document.getElementById("post-body")
const form = document.getElementById("new-post") 

function renderPosts(){
  let html = ""
    for (post of postsArray) {
      html += `
        <h3>${post.title}</h3>
        <p>${post.body}</p>
        <hr />
      `
    }
    document.getElementById("blog-list").innerHTML = html 
}

fetch("https://apis.scrimba.com/jsonplaceholder/posts")
  .then(response => ())
  .then(data => {
    postsArray = data.slice(0, 5)
    renderPosts()
  })
 
 form.addEventListener("submit", function(event){
    event.preventDefault()
    const postTitle = post-title.value
    const postBody = post-body.value
    const data = {
      title: postTitle,
      body: postBody
    }
    
 fetch("https://apis.scrimba.com/jsonplaceholder/posts", {
  method: "POST", 
  body: JSON.stringify(data),
  header: {
      "Content-Type": "application/json"
    }
  })
  .then(response => response.json())
  .then(post => {
    postArray.unshift(post)
    renderPosts()
    form.reset()
  })
 })
```

#### Video 16 REST

What is REST?

Representational State Transfer

Rest is a design pattern to provide a standard way for clients and servers to communicate. 

Priciples of REST:

Client and server separation. 

How would you best describe what REST is to your non-technical friend?

a. A standardized way to have your computer, like your laptop, get or send information to another computer (like a server).


What does a RESTful API usually return in response to incoming requests?

a. Because the API is RESTful the server is'nt in charge of figuring out how to display the data.

These days the most common form of data is JSON so the RESTful API will pretty much always return JSON data.


What kind of client devices can make use of RESTful API?

a. All of them can recieve JSON data and turn that into something visible to the end user.

#### Video 16 REST API design

Principles of REST

Client and Server seperation: see previous video notes.

Statelessness:

When the client makes a request to the server the server doesn't maintain any memory of that request so when a request 

is sent to a server the server fufills that request if it can and sends back a response and then forgets everything about

that request and the client that made the request. If the client needs the server to know more information it will need to

send that every single time it makes a request. Often this is called session state.

Accessing Resources:

This is the entire interaction between client and server is the client asking the server to send it some sort of resource.

Interacting with resources: using stadardized URL endpoints:

Bicycle Shop API
BaseUrl: https://mikesbikes.com/api

  Endpoints:
    
    /bikes
    
    This /bikes endpoint will likely support a couple of different methods including the GET and POST methods.
    
According to RESTful API design if I send a GET request to an Endpoint like  /bikes which is a noun I should be 

returned an array of bikes. An array of JSON data that represents the bikes available on mikesbikes.com.

Because the Endpoint ends in a noun the resource its reffering to is a collection of that noun.

This also makes sense with a post request to an Endpoint that ends in a noun like / bikes. 

A post request is a way for me to add new data. A POST request to /bikes would mean that want to add a new bike to

the collection of bikes. This may be something an admin of mikesbikes.com may do not just any user.

With RESTful API design it goes deeper. When you include an ID to your API Endpoint. 

  /bikes/id: (e.g. /bikes/123)
  
Endpoints like this are another key component of RESTful API design.

When we see the :id as a part of your URL it is not the literal text :id it is a placeholder for the id of one 

specific bike in the collection of bikes.

For Example the Endpoint may be /bikes/123

Here 123 represents the id for one of the specfic bikes in the collection of bikes.

So methods that would make sense with Endpoints like /bikes/123 might be: 

A GET request.

The difference between a get request on /bikes and /bikes/123 is:

/bikes - This will return an array, an array of objects, each bike in the collection of bikes.

/bikes/123 - This will return an object, one of the object from the array returned from /bikes 

So it will be an object, one specific bike in the collection of bikes.

A PUT request method may also be used on an Endpoint like /bikes/123.

A PUT request is when we are updating a resource. A PUT request is most likly on an Endpoint with an

id as we most likely want to update a single bike. If the bike in /bikes/123 has a price increase a

PUT request to this Endpoint could update the price.

A DELETE request will also most likely be made to an Endpoint with an ID to delete that one resource.

Something to point out is that our API endpoints only include nouns and in this case id aswell.

Good API design will not include verbs as a part of your API endpoint.

Quiz:

1) What does it mean for the server to be "Stateless"?

It forget the interaction after the response is sent. 

* In the mikes bikes example, what URL endpoint (and request method) would you expect to use in order
to accomplish the following:

2)  Retrieve a list of all the bikes that are sold

  GET request to /bikes

3) Retreive deleted information about the bike with ID of 42?

  GET request to /bikes/42

4) Update the price of the bike with the ID of 21?

  PUT request /bikes/21

5) Add a new bike to the list of bikes being sold?

  POST request /bikes

6) Remove the bike with the ID of 56 from the list of bikes?
 
   DELETE request /bikes/56


#### Video 17 Nested Resources

Nested Resources and URL parameters

From previous videos:

  /bikes
    GET
    POST
    
  /bikes/:id (e.g. /bikes/123)
    GET
    PUT
    DELETE
  
  /bikes/:id/reviews (e.g. /bikes/123/reviews)
  
  
###### QUIZ

1) How is a nested resource URL like /bikes/123/reviews
   different from an endpoint like /reviews?
   
   bikes/123/reviews - return an array of reviews about that specific bike
   
   /reviews - return an array of all reviews on the site.

2) What URL might you use to GET the review with an ID of 5 on the bike with the ID of 123?
   
   /bikes/123/reviews/5

3) Descibe a "URL Parameter" in your own words:

  A variable inside the URL that acts as a placeholder for th real value.
  
  (oftentimes they replace the ID of the resource)


#### Video 18 JSON Placeholder API

Challenge: Get all the comments from the blog post with ID of 2 and log to the console:

* BaseUrl: https://apis.scrimba.com/jsonplaceholder/
* Endpoint: ??? (Check JSON placeholder docs: https://jsonplaceholder.typicode.com/guide/ and look for the "listing nested resources" section)

```
fetch("https://apis.scrimba.com/jsonplaceholder/posts/2/comments")
.then(response => response.json())
.then(data => console.log(data))
```

#### Video 19 Query Strings

Alot of documentation may refer to query string as parameters.

Query Strings - A way to filter the results we get back.

A common task is to recieve a list of bikes but to have filtered it down is some way or another.

Bicycle shop API
  BaseUrl: https://mikesbikes.com/api
  
    /bikes - This would get all of the bikes back that are available
    
Something you may have seen before in URL is a ? . This allows us to introduce a query string 

In this example we don't only want to get back all the bikes on the API, instead we want to say only

the bikes where the type property of the bike resource is set to mountain.

    /bikes?type=mountain
    
The portion at the end that starts with a ? and then has a something = something else is called a query string of the URL.

The ? is always the way to begin a query string. You can add properties to the query string with an ampersand (&).

Example: /bikes?type=road&brand=trek

Usually somewhere in the process the computer will translate this query string into an object.

So where type=mountain this will turn into an object where the property/key of type has a value of mountain.

{type: mountain}

Where you have multiple properties it simple becomes an object with multiple properties:

{
  type: "road"
  brand: "trek"
}


You can keep adding key value pairs in your query string using the ampersand (&).

Example: /bikes?type=hybrid&brand=trek&color=gray

this will create an object:

{
  type: "hybrid",
  brand: "trek",
  color: "gray"
}

###### QUIZ

At mike's bikes, they also sell bike racks (endpoint is /bikeracks)

What would you expect the endpoints to be for the following tasts:

1) Get a list of all bikeracks sold on the site?

a. /bikeracks

2) Get a list of all bike racks available in the physical store right now

  (Assume a query called "available" that is a boolean true/false)
  
a. /bikeracks?available=true


3) Get a list of all "Thule" - brand bike racks that can hold 4 bikes?

  (Assume there are "brand" and "numBikes" queries)
  
a. /bikeracks?brand=thule&numBikes=4

Query string are embeded everywhere 


#### Video 20 Query String Practice





