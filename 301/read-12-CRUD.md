# CRUD

###### Links

https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/

https://www.youtube.com/channel/UCFbNIlppjAuEX4znoulh0Cw

### Status Codes Based On REST Methods

In your own words, describe what each group of status code represents:

100’s
These are informational status codes. They inform the client that the header part of the request has been recieved by the server and that it will attempt to complete the commnad requested. This could be attempting a differnet protocol or telling the client that its request will fail before they start sending the body.

200’s
These are success codes. tbc

300’s
These are redirection codes. tbc

400’s
These are the client error codes. tbc

500’s
These are the server error codes. tbc

What is a status code 202?
This is oftern used for asyncronous processing. It tells the client the request was valid but it's processing will happen at sometime in the future.

What is a status code 308?
Permenant redirect.

What code would you use if an update didn’t return data to a client?


What code would you use if a resource used to exist but no longer does?


What is the ‘Forbidden’ status code?


Why do we need to pull our MongoDB database string out of our server and put it into our .env?
What is middleware?
What does app.use(express.json()) do?
What does the /:id mean in a route?
What is the difference between PUT and PATCH?
How do you make a default value in a schema?
What does a 500 error status code mean?
What is the difference between a status 200 and a status 201?

