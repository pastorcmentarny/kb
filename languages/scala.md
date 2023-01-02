# SCALA NOTES:
Constructor, scala ????
auxiliary constructors
First class definition????

-------------
 all operators are actually methods.
 
 Scala allows non-alphanumeric method names.
 
-------------
Scala provides a complete mixin solution, called traits.


as part of learning scala do algorithms
-------------
"a guard is a boolean expression that must evaluate to true if the program execution is to continue in the branch in question.
(...)
guard code is a check of integrity preconditions used to avoid errors during execution.
(...)
Guards can be used to augment pattern matching with the possibility to skip a pattern even if the structure matches.  "


So what's that?
well 

val train = ("expensive", "ver" , "C")
val bus = ("1", "2", "3")
val car = ("First", "Second","Third")

for (tup <- List(tupA, tupB)) {
  tup match {
    case (thingOne, thingTwo) if thingOne == "First" =>
        println("A double tuple starting with 'Good'.")
    case (thingOne, thingTwo) =>
        println("This has two things: " + thingOne + " and " + thingTwo)
  }
}



~~~~	Chapter 2. Type Less, Do More


Scala also requires you to initialize a var when it is declared. 

Scala encourages you to use immutable values whenever possible. 

Note :	The var and val keywords only specify if the reference can be changed to refer to a different object (var) or not (val). They don’t specify whether or not the object they reference is mutable.

Method decleratation

 Method definitions start with the def keyword, followed by optional argument lists, a colon character ‘:’ and the return type of the method, an equals sign ‘=’, and finally the method body. 
-------------
The first line uses the val keyword to declare a read-only variable named book.

The upper method definition begins on the second line with the def keyword, followed by the method name and an argument list, the return type of the method, an equals sign ‘=’, then the method body.


the last expression in a function is the return value


object  is a singleton in Scala!(Scala uses objects for situations where other languages would use “class-level” members, like statics in Java.


a short-hand for the function literal. Previously we wrote it as follows.

	(s:String) => s.toUpperCase()

We can shorten it to the following expression.

	_.toUpperCase()
-------------
scala, I DON'T UNDERSTAND
Binding Nested Variables in Case Clauses ?
-------------
triples of double quotes
-------------
he string literals bounded by triples of double quotes are also called multi-line string literals. 

Task 

1. calculate day left until next 
isFridayThirteen


Defs
-------------
<- left-arrow operator is called a generator, so named because it’s generating individual values from a collection for use in an expression.
for example (animal <- zoo)
  println(animal)
-------------

 In Scala, any method with a name that ends with a colon ‘:’ actually binds to the right, while all other methods bind to the left.
 -------------
Pattern matching is a powerful and elegant way of extracting information from objects, when used appropriately.

Most of the time, you want to avoid the problems of “switch” statements that know a class hierarchy, because they have to be modified every time the hierarchy is changed.
-------------
Scala tricks

* Always declare return types for methods, especially when defining methods for a public API.
(It will protect you agains weird looking error, when a more general return type is inferred than what you expected. )


* parameterize the initial map declaration to avoid type mismatch;
flashcards

*println statements invoke toString implicitly on the instances returned by get.
	val stateCapitals = Map(
	  "Alabama" -> "Montgomery",
	}
	println( "Alabama: " + stateCapitals.get("Alabama") )

* Map.get are automatically wrapped in a Some, when there is a value in the map for the specified key. Note that the Scala library doesn’t store the Some in the map, it wraps the value in a Some upon retrieval. Conversely, when we ask for a map entry that doesn’t exist, the None object is returned, rather than null.

	val stateCapitals = Map(
	  "Alabama" -> "Montgomery",
	}
	println( "Alabama: " + stateCapitals.get("Alabama") )
	println( "Unknown: " + stateCapitals.get("Unknown") )
	
	(On console you will see:
	Alabama: Some(Montgomery)
	Unknown: None

* method getOrElse method returns either the value in the Option, if it is a Some instance, or it returns the second argument we passed to getOrElse, if it is a None instance. the second argument to getOrElse functions as the default return value.

getOrElse is the more defensive of the two methods. It avoids a potential thrown exception. 

Most languages would return null (or the equivalent) when there is no “real” value to return. You learn from experience to expect a possible null. Using Option makes the behavior more explicit in the method signature, so it’s more self-documenting.

thanks to Scala’s static typing, you can’t make the mistake of attempting to call a method on a value that might actually be null. 

 Still, you should avoid using null in your code. 
Scala has to support null,becuse Because Scala runs on the JVM and .NET and because it must interoperate with other libraries, 

Tony Hoare, who invented the null reference in 1965 while working on an object-oriented language called ALGOL W, called its invention his “billion dollar mistake” [Hoare2009]. Don’t contribute to that figure.
-------------

Be careful when choosing the names of members of traits. If two traits have a member of the same name and the traits are used in the same instance, a name collision will occur even if both members are private.

============
Avoid var fields when possible (in classes as well as traits). Consider public var fields especially risky

============

how is a lazy val different from a method call? In a method call, the body is executed every time the method is invoked. For a lazy val, the initialization “body” is evaluated only once, when the variable is used for the first time.


Scala is not lazy by default, but it does offer support for working with infinite data structures. 

============

, type safety is the extent to which a programming language discourages or prevents type errors. A type error is erroneous or undesirable program behaviour caused by a discrepancy between differing data types for the program's constants, variables, and methods (functions), e.g., treating an integer (int) as a floating-point number (float). 
============
Functional Programming?

Don’t all programming languages have functions of some sort? Whether they are called methods, procedures, or GOTOs, programmers are always dealing in functions. Functional programming is based on the behavior of functions in the mathematical sense, with all the implications that starting point implies.

====

In mathematics, functions have no side effects. Consider the classic function sin(x).

Add a comment
y = sin(x)

No matter how much work sin(x) does, all the results are returned and assigned to y.

====

Referential Transparency. You can call such a function anywhere and be confident that it will always behave the same way. If no global state is modified, concurrent invocation of the function is straightforward and reliable.

====

An implication of compsability is that functions can be treated as values. In other words, functions are first class, just like data.
====

Composability is a system design principle that deals with the inter-relationships of components. A highly composable system provides recombinant components that can be selected and assembled in various combinations to satisfy specific user requirements. In information systems, the essential features that make a component composable are that it be:


=====


 first class? In computer science, a programming language is said to have first-class functions if it treats functions as first-class citizens. Specifically, this means the language supports passing functions as arguments to other functions, returning them as the values from other functions, and assigning them to variables or storing them in data structures.


stateless:[citation needed] it treats each request as an independent transaction, unrelated to any previous request. 

http://stackoverflow.com/questions/1283830/scala-closures-on-wikipedia
http://gleichmann.wordpress.com/2010/11/15/functional-scala-closures/


====

When a function takes other functions as arguments or returns a function, it is called a higher-order function. In mathematics, two examples of higher-order functions from calculus are derivation and integration.

====

 Short for mutual exclusion object. In computer programming, a mutex is a program object that allows multiple program threads to share the same resource, such as file access, but not simultaneously. 
 
 alleviate - łagodzić
 
 
 Actor is an object that receives messages and takes action on those messages.
 
 eschewing - stroniąc
 
 
 If you see an Actor’s mailbox size ballooning unexpectedly, you’re probably sending messages of a type that the Actor doesn’t know about. Include a catchall case (_) when pattern matching received messages to find out what’s harassing your Actors.

=====


 In functional programming variables are immutable.
 
 
 =========
 
 Immutability is difficult when you’re not used to it. If you can’t change a variable, then you can’t have loop counters, for example.
 
 ======
 However, immutability has enormous benefits for concurrency. Almost all the difficulty of multithreaded programming lies in synchronizing access to shared, mutable state. If you remove mutability, then the problems essentially go away. It is the combination of referentially-transparent functions and immutable values that make functional programming compelling as a “better way” to write concurrent software
 
 mmutability greatly reduces regression bugs, many of which are caused by unintended state changes in one part of a program due to intended changes in another part. There are other contributers to such non-local effects, but mutability is one of the most important.
 
 
 =====
 
 A software regression is a software bug which makes a feature stop functioning as intended after a certain event (for example, a system upgrade, system patching or a change to daylight saving time).[1] A software performance regression is a situation where the software still functions correctly, but performs slowly or uses more memory when compared to previous versions.
 
 
 ========
 algorithms and design patterns in scala


 type List[+A] = scala.collection.immutable.List[A]
  val List = scala.collection.immutable.List

Note that pairs of declarations like type List[+] = … and val List = … are effectively “aliases” for the companion class and object, respectively.

(sealed keyword)

There is an alternative solution if you know that the case class hierarchy is unlikely to change and you can define the whole hierarchy in one file. In this situation, you can add the sealed keyword to the declaration of the common base class. When sealed, the compiler knows all the possible classes that could appear in the match expression, because all of them must be defined in the same source file. So, if you cover all those classes in the case expressions (either explicitly or through shared parent classes), then you can safely eliminate the default case expression.

Using sealed has one drawback. Every time you add or remove a class from the hierarchy, you have to modify the file, since the entire hierarchy has to be declared in the same file. This breaks the Open-Closed Principle ([Meyer1997] and [Martin2003]), which is a solution to the practical problem that it can be costly to modify existing code, retest it (and other code that uses it), and redeploy it.

Avoid sealed case class hierarchies if the hierarchy changes frequently (for an appropriate definition of “frequently”).
 
 
 ==============
SCALA 7



Unit	
Serves the same role as void in most imperative languages. Used primarily as a function return value. There is only one instance of Unit, named (). Think of it as a tuple with zero items.

Nothing	
all other types	
Nothing is the subtype of all other types. It has no instances. It is used primarily for defining other types in a type-safe way,


Predef	
AnyRef	
An object that defines and imports many commonly-used types and methods.



===============

Whenever you define a main method to use as the entry point for an application, Scala requires you to put it in an object. However, at the time of this writing, main methods cannot be defined in a companion object. Because of implementation details in the generated code, the JVM won’t find the main method. 


===============



Vocabulary: (ok , n/i  d/u

Actor 
(ok)
 An autonomous sender and receiver of messages in the actor model of concurrency.

annotation
(ok)
	A way of attaching “metadata” to a declaration that can be exploited by the compiler and other tools for code generation, verification and validation, etc.

anonymous class  An anonymous class is a synthetic subclass generated by the Scala compiler from a new expression in which the class or trait name is followed by curly braces. The curly braces contains the body of the anonymous subclass, which may be empty. However, if the name f


anonymous function  Another name for function literal.

apply   You can apply a method, function, or closure to arguments, which means you invoke it on those arguments.

Aspect-Oriented Programming 

 (Sometimes called Aspect-Oriented Software Development) An approach to cross-cutting concerns, where the concerns are designed and implemented in a “modular” way (that is, with appropriate encapsulation, lack of duplication, etc.), then integrated into all the relevant execution points in a succinct and robust way, e.g. through declarative or programmatic means. In AOP terms, the execution points are called join points, a particular set of them is called a pointcut and the new behavior that is executed before, after, or “around” a join point is called advice. 

Auxiliary Constructor 

 A secondary constructor of a class, declared as a method named this with no return type. An auxiliary constructor must invoke the primary constructor or a previously defined auxiliary constructor as the first or only statement in its method body.

bound variable   A bound variable of an expression is a variable that's both used and defined inside the expression. For instance, in the function literal expression (x: Int) => (x, y), both variables x and y are used, but only x is bound, because it is defined in the expression as an Int and the sole argument to the function described by the expression.

by-name parameter   A parameter that is marked with a => in front of the parameter type, e.g., (x: => Int). The argument corresponding to a by-name parameter is evaluated not before the method is invoked, but each time the parameter is referenced by name inside the method. If a parameter is not by-name, it is by-value. 

by-value parameter   A parameter that is not marked with a => in front of the parameter type, e.g., (x: Int). The argument corresponding to a by-value parameter is evaluated before the method is invoked. By-value parameters contrast with by-name parameters.

closure   A function object that captures free variables, and is said to be "closed" over the variables visible at the time it is created.

companion class  A class that shares the same name with a singleton object defined in the same source file. The class is the singleton object's companion class. 

companion object  A singleton object that shares the same name with a class defined in the same source file. Companion objects and classes have access to each other's private members. In addition, any implicit conversions defined in the companion object will be in scope anywhere the class is used.

currying 
  A way to write functions with multiple parameter lists. For instance def f(x: Int)(y: Int) is a curried function with two parameter lists. A curried function is applied by passing several arguments lists, as in: f(3)(4). However, it is also possible to write a partial application of a curried function, such as f(3).
  Currying 

 Converting an N argument function into a sequence of N functions of one argument, where each function except for the last returns a new function that takes a single argument that returns a new function, etc., until the last function that takes a single argument and returns a value.

define   To define something in a Scala program is to give it a name and an implementation.

Dependency Injection 

 A form of inversion of control, where an object’s external dependencies are given to it, either programmatically or through a DI framework that is driven by configuration information. Hence, the object remains “passive”, rather than taking an active role in resolving dependencies. The injection mechanism uses constructor arguments or field setters provided by the object. DI minimizes the coupling of objects. They only need to know about the abstractions of their dependencies.

for comprehension   Another name for for expression.

function literal  A function with no name in Scala source code, specified with function literal syntax. For example, (x: Int, y: Int) => x + y.

generator   A generator defines a named val and assigns to it a series of values in a for expression. For example, in for(i <- 1 to 10), the generator is "i <- 1 to 10". The value to the right of the <- is the generator expression.

Duck Typing?

First Class 

 An adjective indicating that the applicable “thing” is a first-class value in the language, meaning you can assign instances to variables, pass them as function parameters, and return them from functions
 
 Higher-Order Functions 

 Functions that take other functions as arguments or return a function value.
 
 Inversion of Control 

 The idea that an object should not instantiate it’s own copies of external dependencies, but rather rely on other mechanisms to supply those dependencies.
 
 Lazy 

 Immutable variables (vals) can be declared lazy, meaning they will only be evaluated when they are read. This feature is useful for expensive evaluations that may not be needed.
=========


A trampoline is a loop that works through a list of functions, calling each one in turn. 

=====================

package lab

object Overridding {

  def main(args: Array[String]): Unit = {
    var change2 = new Changeable2
    println(change2.fixedMethod)

  }

  class NotFixed {
    final def fixedMethod = "fixed"
  }

  class Changeable2 extends NotFixed {
    override def fixedMethod = "not fixed" // ERROR
  }

}

/*
 *	conversely - con·verse·ly - /ˈkänvərslē/
 * 		Introducing a statement or idea that reverses one that has just been made or referred to.
 *   
 *   When overriding a concrete member,
 *   Scala requires the override keyword.
 *   It is optional when a subtype defines (“overrides”) an abstract member. 
 *   Conversely, don’t use override unless you are actually overriding a member.
 *   
 *   Requiring the override keyword has several benefits.
 *   - It catches misspelled members that were intended to be overrides. 
 *   		The compiler will throw an error that the member doesn’t override anything. 
 *   - It catches a potentially subtle bug that can occur
 *   		if a new member is added to a base class where the member’s name collides with an older derived class member 
 *     		that is unknown to the base class developer. 
 *    		That is, the derived-class member was never intended to override a base-class member.
 *     		Because the derived class member won’t have the override keyword, 
 *       	the compiler will throw an error when the new base-class member is introduced. 
 *   - Having to add the keyword reminds you to consider what members should or should not be overridden. 
 *   
 *   Java has an optional @Override annotation for methods. 
 *   It helps catch errors of the first type (mispellings),
 *    but it can’t help with errors of the second type, 
 *    since using the annotation is optional.
 */
 
 ==========================



