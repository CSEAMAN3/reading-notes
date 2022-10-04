# Rest & API keys

###### reference links

https://gist.github.com/brookr/5977550

#### Questions

###### Who is Roy Fielding?

Roy helped write the first web servers, that sent documents across the internet. He then he did a ton of research explaining why the web works the way it does.


###### Why don’t the techniques that we use today work well when we need to be able to talk to all of the machines in the world?


###### What is the HTTP protocol that Fielding and his friends created?


###### What does a GET do?

Get is used to request data from a specified resource.


###### What does a POST do?

POST is used to send data to a server to create/update a resource.

The data sent to the server with POST is stored in the request body of the HTTP request:


###### What does PUT do?

PUT is used to send data to a server to create/update a resource.

The difference between POST and PUT is that PUT requests are idempotent. That is, calling the same PUT request multiple times will always produce the same result. In contrast, calling a POST request repeatedly have side effects of creating the same resource multiple times.


###### What does PATCH do?

The PATCH method is used to apply partial modifications to a resource.


