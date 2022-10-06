# API

#### Reference Links




#### Questions

###### What does REST stand for?

Representational State Transfer (REST) 


###### REST APIs are designed around a ____.

REST APIs are designed around resources, which are any kind of object, data, or service that can be accessed by the client.


###### What is an identifier of a resource? Give an example.

An identifier of a resource a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:

https://adventure-works.com/orders/1


###### What are the most common HTTP verbs?

GET, POST, PUT, PATCH, and DELETE.


###### What should the URIs be based on?

Http protocol????


###### Give an example of a good URI.

When possible, resource URIs should be based on nouns (the resource) and not verbs (the operations on the resource).

https://adventure-works.com/orders // Good

https://adventure-works.com/create-order // Avoid


###### What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?

All web requests impose a load on the web server. The more requests, the bigger the load. 

Try to avoid "chatty" web APIs that expose a large number of small resources.


###### What status code does a successful GET request return?

A successful GET method typically returns HTTP status code 200 (OK). 


###### What status code does an unsuccessful GET request return?

If the resource cannot be found, the method should return 404 (Not Found).


###### What status code does a successful POST request return?

If a POST method creates a new resource, it returns HTTP status code 201 (Created).

If the method does some processing but does not create a new resource, the method can return HTTP status code 200 

and include the result of the operation in the response body. 

Alternatively, if there is no result to return, the method can return HTTP status code 204 (No Content) with no response body.


###### What status code does a successful DELETE request return?

If the delete operation is successful, the web server should respond with HTTP status code 204 (No Content), 

indicating that the process has been successfully handled, but that the response body contains no further information. 

If the resource doesn't exist, the web server can return HTTP 404 (Not Found).








