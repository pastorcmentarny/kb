## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 


*JavaScript* is **single threaded**.

JAVASCRIPT

Global variable n its simplest form, this technique aims to wrap code inside a function scope.It helps decreases chances of:
clashing with other applications/libraries
polluting superior (global most likely) scope
OTHER:
B64 as way to fix escape problems
the object container (JSONObject) was not holding the precision of the original value. The JSONObject actually takes a double, not a float


##Promises
promises are a bit like event listeners except:
* A promise can only succeed or fail once (but not more and you cannot switch from success to failure). 

###A promise can be:

* **fulfilled** The action relating to the promise succeeded
* **rejected**  The action relating to the promise failed 
* **pending**   Hasn't fulfilled or rejected yet 
* **settled**   Has fulfilled or rejected

The promise constructor takes one argument, a callback with two parameters, resolve and reject.

 it's customary, but not required, to reject with an Error object. The benefit of Error objects is they capture a stack trace, making debugging tools more helpful.
 
http://www.fbloggs.com/2010/07/09/how-to-access-cross-domain-data-with-ajax-using-jsonp-jquery-and-php/
http://www.vcarrer.com/2010/11/about-jsonp-in-javascript.html

JSONP is JSON with padding, that is, you put a string at the beginning and a pair of parenthesis around it. For example:

//JSON
{"name":"stackoverflow","id":5}
//JSONP
func({"name":"stackoverflow","id":5});

The result is that you can load the json as a script file. If you previously set up a function called func, then that function will be called with one argument, which is the json data, when the script file is done loading. This is usually used to allow for cross-site AJAX with JSON data. If you know that example.com is serving json files that look like the one above, then you can use code like this to retrieve it, even if you are not on the example.com domain:



down vote	
http://en.wikipedia.org/wiki/JSON#JSONP

JSONP allows you to specify a callback function that is passed your JSON object. This allows you to bypass the same origin policy and load JSON from an external server into the javascript on your webpage.

JSONP is essentially, JSON with extra code, like a function call wrapped around the data. It allows the data to be acted on during parsing.

JSONP

* First, functions are values that may be expressed with literal notation. In geeky terms, this means JavaScript has first-class functions.
* Prototype is  a prebuilt object that simplifies the process of adding custom properties/ methods to all instances of an object. 

It means that functions are objects, with a type and a behaviour. They can be dynamically built, passed around as any other object, and the fact that they can be called is part of their interface.

Functions are first-class objects. That means that they can be created dynamically, stored, passed and returned just like any other value.
object is — a “thing” with methods and properties

A function is something that performs a particular task.

what beforeafter?


The term originally stood for Asynchronous JavaScript + XML
(XML was the format in which the browser and server communicated with each other). Today,
Ajax simply refers to the pattern of using JavaScript to send and receive data from the web server
without reloading the entire page.


Javascript basics

JavaScript keywords:
break, case, catch, continue, default, delete, do, else, finally, for, function, if, in, instanceof, new, return, switch this throw try typeof var void while with

*In an object literal, the curly braces contain members, but in a function literal, the curly braces
contain statements.

* In an object literal, the curly braces contain members, but in a function literal, the curly braces
contain statements.




Reserved Keywords

abstract  break byte case 
char class const continue  delete
do double  extends  final
 float  function goto 
implements import in instanceof int interface
long native new null package 
  return short static super
 synchronized this   transient
  typeof var void volatile
 with

 Access ( private , protected , public)
Variables ( boolean , true , false
Conditions (if ,  else , switch , default
Loop (for , while, )
Exception related( try catch finally throw throws)



function

Functions are self-contained units of a program designed to accomplish a
specified task

By definition, a function is a block of statements that not only performs some task,
but also returns a value. A

Anonymous Functions as Variables
A function definition can be assigned directly to a variable. The variable is like any other
variable except that its value is a function definition and this variable is used as a reference
to the function.

var greetings= function(){ // Anonymous function has no name
	message="Greetings to you! "; // Function definition
	return message;
}


A closure is an a anonymous function defined within another function. When the outer
function exits, it returns a reference to the inner anonymous function, making it possible
to call the inner function via the reference. A closure means that the local variables can
remain accessible to the inner function even when it seems they should have gone out of
scope. The closure causes the variables to hang around until they are no longer needed.

On the other hand, accidentally creating closures can have harmful side effects such
as Internet Explorer memory leaks and reduced efficiency of code.


Scope:

Scope of Variables in Functions. The scope of a variable describes where the variable
is visible in the program; that is, where it can be used in the program. Variables
declared outside of functions are global in scope, meaning they can be used or changed
anywhere in the program. A variable is also global if declared within a function unless
it is declared within a function with the var keyword. The var keyword makes the variable
local in scope; that is, the variable can be used only within the function where it is
defined and is no longer visible once the function ends.

Math.floor(mynumber)
.toString()
.padStart(2, '0')