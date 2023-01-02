## **HONEST WARNING**

**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._

# A

## ACK

ACK is short for acknowledgment.

## Algorithm

It is a step-by-step procedure for 'recipe' like calculations.

## ArrayList

ArrayList is a resizable-array implementation of the List interface. It is internally implemented as an object array,
which can increase the size as necessary to support more number of elements in the collection. It is possible to specify
the initial capacity of an ArrayList through the constructor ArrayList(int initialCapacity)  and later increases the
capacity using void ensureCapacity(int minCapacity), if necessary, to ensure that it can hold at least the number of
elements specified by the minimum capacity argument.

An ArrayList is faster and better as it supports random access to its elements. Traversing a linked list or inserting an
item in the middle is very expensive as you have to iterate over each item and is very likely to have cache misses. If
you need to perform processing on multiple items of the list in a single iteration then the overhead of iterations can
be lesser inLinkedList than that of anArrayList which involves copying array element multiple times.

## Aspect-Oriented Programming

Aspect Oriented Programming(AOP) is the important part of the Spring Framework. The Aspect-Oriented Programming used for
separating cross-cutting concerns (for example logging, security etc.) from the business logic of the application.

# B

## Boilerplate code

It is the sections of code that have to be included in many places with little or no alteration"

# C

## Caching

It is the concept of storing the generated results and using the stored results instead of generating them repeatedly if
the same request arrives in the near future. This can be done on the client, the server, or on any other component
between them, such as a proxy server. Caching is a great way of enhancing the service performance,

## Container

The containers is a groups of processes isolated from others using various constrains techniques available in Linux
like: resource constrains (control groups), security constraints(permissions, SELinux)  and namesspaces (PID, network,
mount etc.)
Container runtimes are tools that modify these resource constraints, security, and namespaces and launch the container.

a container registry a web service where you storefrom which they could be pulled,

Container engines are programs that can pull container images from container registries and reassemble them onto
container storage. Container engines also launch container runtimes (see below).

a container runtime configuration. The runtime configuration combines input from the caller/user along with the content
of the container image specification. For example, the caller might want to specify modifications to a running
container's security, add additional environment variables,

a container runtime that reads the container runtime specification; modifies the Linux cgroups, Linux security
constraints, and namespaces; and launches the container command to create the container's PID 1. At this point, the
container engine can relay stdin/stdout back to the caller and control the container (e.g., stop, start, attach).

Container orchestrators are tools used to coordinate the execution of containers on multiple different nodes.

Optimise your container images:

1. First pass: Clean up after yourself removing cached files from an image to recover space

As with everything in life, moderation is key.

## Content Security Policy (CSP)

The HTTP Content-Security-Policy response header allows web site administrators to control resources the user agent is
allowed to load for a given page. With a few exceptions, policies mostly involve specifying server origins and script
endpoints. This helps guard against cross-site scripting attacks (XSS).
(Source: https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)

# D

## Database

"A database is an organized collection of data, generally stored and accessed electronically from a computer system.

## Data structure?

Data structure is a container (in java will be a class) that provides storage for data elements , and provide
capabilities for manipulate data items (add, remove, swap, find and so on). Benefits are:
⦁ Reusability and better code quality as result of the use of well tested collections' framework classes. ⦁ Reduced
effort for code maintenance by using collection classes shipped with JDK.

## /dev/null

/dev/null is a special file called the null device in Unix systems.It is 'blackhole because it immediately discards
anything written to it and only returns an end-of-file EOF when read.

## Dependency management

It helps manage all the libraries required to make an application work and helps to keep track, update libraries faster
and easier, as well as solve the problem then one package will depend on another package.

# E

## Encapsulation

hiding of data implementation by restricting access

# F

## What is Framework?

//TODO A framework is a set of classes and interfaces which provide a ready-made architecture. An optimal
object-oriented design always includes a framework with a collection of classes such that all the classes perform the
same kind of task.

# H

## Hexagonal Architecture (ports and adapters).

//TODO

## HTTP

stands for Hypertext Transfer Protocol. It's a stateless, application-layer protocol for communicating between
distributed systems to allow two systems to communicate via remote calls.

HTTP uses a simple request and response mechanism.

HTTP has two strategies to counter these problems. The simplest is called HTTP persistent connection, sometimes also
known as keep-alive. HTTP will simply reuse the same TCP connection once a single request-response pair is done.

# I

## IaaS

Infrastructure as a Service. Cloud providers only provide the hardware needed to run applications.

# L

## Locks

Locks can make sure that the sequence of language operations are going to be performed in isolation to other concurrent
threads working with that same resource. Locks cannot garantee atomicity, which I explained Atomicity, in particular,
guarantees that each compound action is treated as a single "unit of work," which either succeeds completely or fails
completely. If any of the compound actions constituting a unit of work fails to complete, the entire unit of work fails
and the data is left unchanged (Wikipedia). As I have shown in my post, Java cannot guarantee that without adding extra
code, like exception handling, to intrinsic and explicit locks.

## Linked List

The LinkedList data structure contains an ordered set of data elements (know as nodes) such that each element contains a
link or reference to its successor (next element). The last element (or tail) of the sequence points to a null element.
The linked list itself contains a reference to the first element of the list, which is called the head element.
LinkedList in Java is a doubly-linked list implementation of the List interface. In a doubly-linked list, every node
points to its previous and next node. Other interfaces it implements are Serializable, Cloneable, and Deque (with
super-interface as Queue).

## Logging
Logging is basically a huge journal of the activity of a system or application. 
Source: (https://www.ncsc.gov.uk/information/log4j-vulnerability-what-everyone-needs-to-know)

# M

## Microservices Architecture?

* A microservice architecture is a software development technique that structures an application as a collection of
  loosely coupled services.
* The services are fine-grained and the protocols lightweight, thus improving application modularity, making it easier
  to understand, develop, and test. It parallelizes development by enabling small autonomous teams to develop, deploy,
  and scale their respective services independently.
* Microservice can be polyglot, it means you can use different language for different project

# O

## BIG O NOTATION

What do you know about the big-O notation? It is depressing way to describe how badly algoritmic perfomance sucks. The
Big-O notation is used for describing algorithm performance, scalability, execution and complexity factors in the worst
case scenario as the number of elements in a data structure increases.

BIG O NOTATION from best to worst:

* `O(1) -> O(logn)->O(n)->O(nlogn)->O(n^2)->O(2^n)->O(n!)`
* `O(1) - Constant O(log n)  - Logarithmic O(n) - Linear O(n log n) - Linear Logarithmic O(n2) - Quadratic O(n3) - Cubic`

List and sets Structure : get : add : remove : contains

* ArrayList O(1) : O(1) : O(n) : O(n)
* LinkedList O(n) : O(1) : O(1) : O(n)
* HashSet O(1) : O(1) : O(1) : O(1)
* LinkedHashList O(1) : O(1) : O(1) : O(1)
* TreeSet O(logn) : O(logn) : O(logn) : O(logn)

Maps Structure : Get : Put : Remove : ContainsKey:

* HashMap : O(1) : : O(1) : O(1) : O(1)
* LinkedHashMap O(1) : O(1) : O(1) : O(1)
* TreeMap O(logn) : O(logn) : O(logn) : O(logn)

# P

## PaaS

Platform as a Service. The cloud provider provides you a platform - an operating system or managed software (databases,
programming languages, web application platforms) - on top of the hardware.

# R

## Reactive Programing

Reactive Programming Reactive programming is a programming paradigm that delivers three benefits: resource efficiency,
consistency and composability of data APIs, and robustness. It delivers better resource efficiency by making it trivial
to write code that does a good job of freeing up otherwise idle threads for reuse.

## Reactive Streams

It is a specification. For Java programmers, Reactive Streams is an API. Reactive Streams gives us a common API for
Reactive Programming in Java.

The Reactive Streams API consists of just 4 interfaces.

* **A publisher** is a provider of a potentially unbounded number of sequenced elements, publishing them according to
  the demand received from its Subscribers.
* **A subscriber** will receive call to Subscriber.onSubscribe(Subscription) once after passing an instance of
  Subscriber to Publisher.subscribe(Subscriber).
* **A subscription** represents a one-to-one lifecycle of a Subscriber subscribing to a Publisher.
* **A processor** represents a processing stage—which is both a Subscriber and a Publisher and obeys the contracts of
  both.

## Reactive Systems

**Reactive Systems** are **_Responsive_**, **_Resilient_**, **_Elastic_** and **_Message Driven_**. As result, Reactive
Systems are more flexible, loosely-coupled and scalable. This makes them easier to develop and amenable to change.

* **_Responsive_** The system responds in a timely manner if at all possible.
* **_Responsiveness_** is the cornerstone of usability and utility, but more than that, responsiveness means that
  problems may be detected quickly and dealt with effectively. The system stays responsive in the face of failure.
* **_Resilience_** is achieved by replication, containment, isolation and delegation. The system stays responsive under
  varying workload.
* **_Elastic_**: The system stays responsive under varying workload. Reactive Systems can react to changes in the input
  rate by increasing or decreasing the resources allocated to service these inputs.
* **_Message Driven_**: Reactive Systems rely on asynchronous message-passing to establish a boundary between components
  that ensures loose coupling, isolation and location transparency.

# S

## A sorting algorithm

It is an algorithm that puts elements of a list in a certain order.

## Seagulling

It is when someone comes in at the last minute and poops all over your work.

## Software design pattern

A software design pattern is a general, reusable solution to a commonly occurring problem within a given context in
software design. Why Do We Need Design Patterns? Proven Solutions to common and widely known problems Easy to reause
Helps communication (more easily communicate with one another about potential solutions to a given problem.)

## REST

REST stands for Representational state transfer. It is an architectural style for distributed hypermedia systems (for
example HTTP). REST is not a "standard".

### CRUD operations using HTTP verbs

#### HTTP Verb (CRUD verb)

#### POST (Create)

POST is used for creating an entity. When resource is successfully created, an id of the newly created entity is
returned as part of the response to this HTTP request.

```POST on /song/1001 will create a new song with employee id 1001```

#### GET (Read)

GET retrieves data from the server (nothing else).

GET request on /song/1001, you can retrieve details of that song.

#### PUT (Update)

PUT is Similar to POST, but used to update an existing entity and requires the id of existing resource.

PUT request type on /song/1001 can be used to update details of song with id 1001

#### DELETE (Delete)

DELETE removes the resource from the server. You need to pass the id of the resource to be deleted.

DELETE method on /song/1001 can be used to remove data for that id.

### OTHERS

#### TRACE

TRACE provides a means to test what a machine along the network path receives when a request is made. As such, it simply
returns what was sent.

#### HEAD

HEAD is same as the GET method for a resource, but returns only the response headers without body.

#### OPTIONS

OPTIONS allows a client to request information about the request methods supported by a service.

#### CONNECT

CONNECT primarily used to establish a network connection to a resource (usually via some proxy that can be requested to
forward an HTTP request as TCP and maintain the connection). Once established, the response sends a 200 status code and
a “Connection Established” message.

### HTTP REQUEST:

* **VERB** - _one of the HTTP methods_
* **URI** - _the URI of the resource on which the operation is going to be performed_
* **HTTP Version** - _the version of HTTP used_
* **HEADER** - _the metadata as a collection of key-value pairs of headers and their values._
* **BODY** - _content_

### HTTP RESPONSE:

* **CODE** - _The 3-digit code which contains the status of the request._
* **HEADER** - _The metadata and settings about the response message._
* **BODY** - _It contains the representation if the request was successful._

# I

## IP

IP — Internet Protocol The IP in TCP/IP is short for Internet Protocol. IP implements packet-switched networking. It has
a concept of hosts, which are machines. The IP protocol specifies how datagrams (packets) are sent between these
hosts.The IP Header An IP packet consists of a header and a payload. The payload contains the actual data to be
transmitted, while the header is metadata.

# S

## SaaS

Software as a Service. The cloud provider offers a software product on the cloud - like Google Docs.

## SL4J

SLF4J is a façade for various logging frameworks

## Statelessness

A RESTful service is stateless and does not maintain the application state for any client

## SYN

It stands for synchronize sequence numbers.

# T

## TCP

TCP — Transmission Control Protocol. It’s so common that the entire suite of protocols is often referred to as TCP/IP.
It is a reliable data transfer protocol that ensures that the data sent is complete and correct and requires to
establish a connection.

TCP is built on top of IP. The Transmission Control Protocol provides reliable, ordered, error-checked delivery of a
stream of data between programs. With TCP, an application running on one device can send data to an application on
another device and be sure that the data arrives there in the same way that it was sent.

## (Database) Transaction

A "_unit of work_" that need be performed **together** or **not at all**.

# Trunk based development

Trunk based development is one of VCS (version control system)  branching model for git with main focus on all
developers work from a single branch (main, master or trunk whatever you like to call it).

While Git Flow like branching model is not wrong or not popular anymore but it causes a few issues from time to time
that bite my team:

* out of sync branches
* using rollback cause lots of work to re-sync all other branches
* housekeeping takes longer, and we are not the best branch cleaners.

TbD resolve these problems:

* Simplify branch model. You have the main branch and feature branches. You do your fantastic work in pair. You submit
  PR. Somebody reviews that (and in the future, Sonarcube will pick up code style issues automatically. Stay tuned for
  the presentation next showcase). You merge to master and deploy to any environment.
* Rollback can happen from the master branch, where you simply re-deploy the previous master branch to prod using
  Jenkins job with parameters. Is it any drawbacks? I am sure , I will discover shortly.

## Sources:

* https://trunkbaseddevelopment.com/
* https://www.toptal.com/software/trunk-based-development-git-flow

# U

## UTF

UTF is an abbreviation for UCS Transformation Format (UCS -> Universal Character Set.).

# X

## XSSCross-site scripting (XSS)

It is a type of computer insecurity vulnerability typically found in Web applications (such as web browsers through
breaches of browser security) that enables attackers to inject client-side script into Web pages viewed by other users.
In general, cross-site scripting refers to that hacking technique that leverages vulnerabilities in the code of a web
application to allow an attacker to send malicious content from an end-user and collect some type of data from the
victim.

# Changelist:

* 2021.1 - Quick cleanup
* 2020.2 - add UTF definition
* 2020.1 - add 1 definition, dictionary cleanup
* 2019.1 - Quick cleanup
* 2018.1 - First Version


Collection pipelines are a programming pattern where you organize some computation as a sequence of operations which compose by taking a collection as output of one operation and feeding it into the next. (Common operations are filter, map, and reduce.)

usuflness :
Laziness. large_list
.map{|e| slow_complex_method (e)}
.take(5)
With such code, you would spend a lot of time evaluating slow_complex_method on lots of elements and then throw away all the results except the top 5. Laziness allows the underlying platform to determine that you only need the top five results,
Parallelism
Many of the pipeline operations naturally work well with parallel invocation. If I use map the results of using it for one element don't depend on any of the other elements in the collection. So if I'm running on a platform with multiple cores, I can take advantage of that by distributing the map evaluations across multiple threads.

Immutability
Collection-pipelines naturally lend themselves to immutable data structures. When building a pipeline it's natural to consider each operation as generating a new collection for its output.

check operation catalog for details https://martinfowler.com/articles/collection-pipeline/#op-catalog
https://martinfowler.com/articles/collection-pipeline/