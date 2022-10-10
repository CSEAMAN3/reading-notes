# Learn Express JS - Web Dev Simplified


###### From Class Notes

In the terminal from the desktop

Enter command

mkdir name-of-project

Then enter command

cd name-of-project

Then enter command

npx create-react-app client

Once this is complete. On your desktop go to finder, projects and name-of-project. 
Open the folder, inside there will be a client folder, create another folder called server.

Now back in your terminal on your desktop make sure you are in name-of-project. Enter command

code .

This will open your project in VScode.

In VScode open a terminal and enter command

cd server

Then enter command 

npm init -y

This creates a basic package.json, the -y means say yes to everything. This is where we're going to install all our different libraries.

Inside the package.json file change:

"main": "index.js"

to

"main": "server.js"

Next in the terminal in your VScode (note - make sure you are in server) enter command:

npm i express cors dotenv nodemon axios

You will notice these are now listed in your dependencies:

express is the framework we will use to build our API

cors is crucial for us to make a connection between our react app and our backend.

dotenv is

nodemon allows us to restart our server anytime we make changes.

axios is 


Now create a file in your server called server.js.

In the terminal on VScode (note - make sure you are in server) enter command:

touch.js

You will notice the file server.js has been created in your server folder.

Inside server.js is where we are going to put all our server code.

The first thing we need to do is create our express server. 

We need to require the express library we downloaded.

Inside our server.js file type.

const express = require("express")

Then to actually set up our server we create an app variable which calls our express function. So type:

const express = require("express")
const app = express()

By calling express as a function we create an application that allows us to set up our entire server.

Then to make our server actually run we type:

const express = require("express")
const app = express()

app.listen(3000)

We parse in a port number to app.listen. 

We are saying our app right here our server is listnening on port 3000 for a bunch of different requests.

If we save that we have an app running on port 3000.

You will now see if you run the application it will state:

Cannot get /

This is simply saying we don't have any routes set up.

so when we try to get this index route /

It's saying it can't find this route.

The easiest way to set up a route is to type app. then we can call different methods.

app.get

app.post

app.put

app.delete

app.patch

These are http methods that are available.

So at this stage we want to make a get request for the url at /

so we type:

const express = require("express")
const app = express()

app.get('/', (request, response) => {
  console.log(here)
  response.send("hi")
})

app.listen(3000)

### Mern in 60 mins





















