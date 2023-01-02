 ## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 

## What is RESTFul Web Service?

## What are the differences between HTTP and REST?
HTTP is a stateless, application-layer protocol for communicating between distributed systems
REST is not a standard . It is an architectural style for distributed hypermedia systems. REST is a design style for protocols,

## Difference between POST and PUT?
POST is a method to create a new resource and get id, if resource was created successfully. I
PUT is a method to update existing resource. It can be used to create an new resource with given id. 
The key difference between PUT and POST is that.No matter how many times you send a PUT request, the results will be same. Making a POST multiple times may result in multiple resources getting created on the server.
Another difference is that, with PUT, you must always specify the complete URI of the resource.


Request
Operation
PUT http://MyService/Persons/
Won't work. PUT requires a complete URI
PUT http://MyService/Persons/1
Insert a new person with PersonID=1 if it does not already exist, or else update the existing resource




POST http://MyService/Persons/
Insert a new person every time this request is made and generate a new PersonID.
POST http://MyService/Persons/1
Update the existing person where PersonID=1

Difference between HEAD and GET?
HEAD returns only the response headers with an empty body. 
GET HEAD returns only the response headers with a body.


What do you understand by payload in RESTFul? [TODO improve it]
Payload means data which passed inside request body also payload is not request parameters. So only you can do payload in POST.




## REST example OF crud CRUD-based APIs 
It contains instances, mimicking the (c)reate, (r)ead, (u)pdate, and (d)elete lifecycle pattern. The CRUD pattern is useful when we have a collection of resource instances that represent content or state. It often follows this familiar pattern:

* **GET**       /airplane                   – the list of all available airplane types
* **GET**       /airplane/{airplaneType}   – get specific airplane type
* **PUT**       /airplane/airbus380           - update the airplane type
* **PATCH**     /airplane/{airplaneType}   – update specific fields for airplane type
* **POST**      /airplane                   – Create a new airplane type
* **DELETE**    /airplane/{airplaneType}   – Delete a specific airplane




REST is about constraining the way we interact between client and server, to take advantage of what the protocol (in this case, HTTP) offers. These constraints give us freedom to focus on our API design:

Uniform interface – requests from different clients look the same, whether the client is a browser, mobile device, or anything else
Client-server separation – the client and the server act independently and the interaction between them is only in the form of requests and responses
Stateless – the server does not remember anything about the user who uses the API, so all necessary information to process the request must be provided by the client on each request. Note: this isn’t about storing server-side state
Layered system – the client is agnostic as to how many layers, if any, there are between the client and the actual server responding to the request. This is a key principle of HTTP, allowing for caching servers, reverse proxies, and access security layering – all transparent to the client sending the request
Cacheable – the server response must contain information about whether or not the data is cacheable, allowing the client and/or intermediaries (see layered constraint, above) to cache data outside of the API server
Code-on-demand (optional) – the client can request code from the server, usually in the form of a script, for client-side execution
Again, there is nothing about REST requiring a resource with a CRUD-based lifecycle. CRUD is a pattern we can apply to our APIs, but it isn’t a requirement for composing a REST-based API.


POST /articles/{articleId}/submit
POST /articles/{articleId}/approve
POST /articles/{articleId}/decline
POST /articles/{articleId}/publish

GET /search?q=api
GET /postal-code-to-region?postalCode=78701
POST /calc-sales-tax

TODO:
https://github.com/yangshun/tech-interview-handbook/blob/master/preparing/cheatsheet.md


UI
REST requires each resource to have at least one URI. 
The actual operation is determined by an HTTP verb. The URI should not say anything about the operation or action.

This URL has following format: Protocol://ServiceName/ResourceType/ResourceID

This is typical convention:
Use plural nouns for naming your resources.
Avoid using spaces as they create confusion. Use an _ (underscore) or – (hyphen) instead.
A URI is case insensitive. I use camel case in my URIs for better clarity. You can use all lower-case URIs.
You can have your own conventions, but stay consistent throughout the service. 


Query Parameters in URI
The preceding URI is constructed with the help of a query parameter:

http://MyService/Persons?id=1


The basic purpose of query parameters is to provide parameters to an operation that needs the data items.

ttp://MyService/Persons/1?format=xml&encoding=UTF8

The robustness principle
To create web APIs that are easy to evolve, follow the robustness principle, summarized as “Be conservative in what you do, be liberal in what you accept.”

In the context of web APIs, this principle can be applied in several ways:

Every API endpoint should have a small, specific goal that follows only one of the CRUD operations. Clients should be in charge of aggregating multiple calls as needed.
Servers should communicate expected message formats and schemas and adhere to them.
New or unknown fields in message bodies should not cause errors in APIs, they should just be ignored.

# TIPS and Tricks:
1. The query parameter approach works just fine and REST does not stop you from using query parameters. However, this approach has a few disadvantages. Increased complexity and reduced readability, which will increase if you have more parameters.Search-engine crawlers and indexers like Google ignore URIs with query parameters. 
0. Documenting a RESTful Service RESTful services do not necessarily require a document to help clients discover them. Due to URIs, links, and a uniform interface, it is extremely simple to discover RESTful services at runtime. The method OPTION can be used effectively in the process of discovering a service. This does not mean that RESTful services require no documentation at all. There is no excuse for not documenting your service. You should document every resource and URI for client developers. 
0. Using headers for versioning is more in line with RESTful practices