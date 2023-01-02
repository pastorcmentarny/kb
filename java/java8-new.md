

## INTERFACE

Java 8 extends interface with two new concepts: _default_ and _static_ methods.

###### Advanced info:
* Private and protected access in interfaces were postponed to Java 9.

### Default methods

Default method in interface provide default implementation of method so it allows backward compatibility 

_Default method_ is **a method on interface with implementation**. Using this features should reduce amount of classes needed.

They allow adding new methods to existing interfaces without breaking the binary compatibility with the code written for older versions of those interfaces.
The **difference between** _default methods_ and _abstract methods_ is that **abstract methods are required to be implemented**.
#### Tips and Tricks
* _Default method_ **_cannot_** be accessed from within _lambda expressions_.
* _Default method_ **_cannot_** refer to _equal, hashcode _or_ toString_. If you need them then you need use _abstract class_.

### Static method in interface

#### Tips and Tricks
* **Don't overuse it**.
* **Don't convert** _lambda_ to _method interface_ as you will need **revert** that change when you need pass extra parameters
* Remember thant while normal _static method_ you **can refer** from any _sub class_ , _static method on interface_  **can refer** from _interface_ only.

## FUNCTIONAL INTERFACE

_A functional interface_ is any interface that **contains only one abstract method**. _A functional interface_ may contain **one or more default methods or static methods**.

If you writing your own _functional interface_ then **add @FunctionalInterface** . It is a optional because **any interface with one abstract method is a functional interface** but
 by adding this annotation  you protect yourself (or other developer) against future accidental break and it helps explain intention of this interface.
_Interface_ can extend another _functional interface_. If extended _interface_ do not declare any new abstract methods then it is still _functional interface_.

#### Tips and Tricks
* For make your debugging life easier  put functional interface as parameter last, because error messages cause in functional interfaces can be .. challenging.
* Checked exception does not compile in functional interface.Use wrapper that convert to unchecked exception.
* Instances of functional interfaces can be created with lambda expressions, method references, or constructor references.

#####//TODO 
* Check java.util.function package

###### Advanced info:

How looks resolving a method implementation:
1. A concrete implementation in the class wins
2. The lowest implementation in the implemented interfaces wins
3. If there are multiple implementations available through different interfaces that are on different paths up through the class hierarchy, the program doesn’t compile.

## LAMBDAS (known as closures)

_Lambda_ expressions **enable you to pass functionality as an argument to another method, to treat functionality as method argument**. Lambda is a block of code (like an anonymous inner class).

Syntax: LambdaParameters -> LambdaBody
    -> Lambda operator
     () indicates no parameters.
If to use a lambda expression, you need to implement a functional interface.
_Lambdas_ may return a value. The _return statement__ **is not required** if the _lambda_ body **is** just **a one-liner**.
_Lambdas_ may reference the class members and local variables (implicitly making them effectively final if they are not).
_Lambdas_ **use target typing** which is awesome but it has side effect. You **cannot** do **method overloading because compiler may be not able to figure out which method to use**.
_Lambdas expressions_ are **lexically scoped** so it doesn't have shadowing issue(when declaration shadows the declaration of the enclosing scope). Declarations in a _lambda expression_ are interpreted just as they are in the enclosing environment.

Types of Method References
| Type                          |	Syntax                |	Method Reference    |	Lambda expression   |
Reference to a static method    |   Class::staticMethod	String::valueOf	 s -> String.valueOf(s)

Reference to an instance method of a particular object	instance::instanceMethod	s:toString	 () -> “string”.toString()
Reference to an instance method
of an arbitrary object of a particular type	Class:instanceMethod	String::toString	 s -> s.toString()
Reference to a constructor	Class::new	String::new	
 () -> new String()

#### Tips and Tricks
* Avoid put Type on Lambda (You don't need do that except when compilers needed it) .
* You should put type of lambda only when you debugging.
* Lambda prefer immutability.  (tip by Stephen )
* Prefer Expression lambdas over block lambdas. If you need block lambadas then extract as method.
* You cannot use Checked exception in lambdas .If this happen you need convert checked exception into unchecked exception
* One thing to keep in mind: default and static methods do not break the functional interface contract and may be declared
* It is important to remember Lambada is one of Java 8 that helps reduce the verbosity.It is important that readability is most important and sometimes extra code is not the enemy.

###### Advanced info:
You can serialize lambda expressions but you should not. It has to do with fact that synthetic constructs can vary among different Java compiler implementations. which means that .class files can vary among different implementations as well. Consequently, you may have compatibility issues if you serialize an inner class and then deserialize it with a different JRE implementation.

#### target typing

Context determines type of the lambdas is.

#### Effectively final

Effectively final is a concept that compiler worked out for you that variable is don't change it .

## STREAMS
Streams are another feature that were added with Java 8. It provides a different way of performing operations on a Collection. 

Stream operations are divided into intermediate and terminal operations, and are combined to form stream pipelines. A stream pipeline consists of a source (such as a Collection, an array, a generator function, or an I/O channel); followed by zero or more intermediate operations such as Stream.filter or Stream.map; and a terminal operation such as Stream.forEach or Stream.reduce.
Intermediate operations return a new stream. They are always lazy; executing an intermediate operation such as filter() does not actually perform any filtering, but instead creates a new stream that, when traversed, contains the elements of the initial stream that match the given predicate. Traversal of the pipeline source does not begin until the terminal operation of the pipeline is executed.

Terminal operations, such as Stream.forEach or IntStream.sum, may traverse the stream to produce a result or a side-effect. After the terminal operation is performed, the stream pipeline is considered consumed, and can no longer be used; 

A java.util.Stream represents a sequence of elements on which one or more operations can be performed. Stream operations are either intermediate or terminal. While terminal operations return a result of a certain type, intermediate operations return the stream itself so you can chain multiple method calls in a row.    
java.util.Collection like lists or sets (maps are not supported). 
Streams works on principle that many loops are very similar as they looks like 'design patterns for doing looping'.
Streams is a 'abstraction' of that.
 Stream operations are either intermediate or terminal.
 Terminal operations return a result of a certain type
 Intermediate operations return the stream itself

Design goal for the stream was simple parallelism.
Parallel stream is good for single threaded application.
Parallel streams are bad, if there are many concurrent call to this method as use one shared execution pool. As many methods fights for the same pool.

#### Tips and Tricks
* Streams are not always more readable.
* Streams are painful to debug.
* Think twice before use parel stream as they are only few cases when they are beneficial.
* If you have problem with debugging bugs in stream then extract lines (extract local variable) that cause problem. It will save you lots of time.
* You CANNOT reuse streams because after use any terminal operation the stream is closed. For example this:
```
        IntStream stream = IntStream.range(1,10);
        stream.forEach(System.out::println);
        stream.forEach(System.out::println); //This will throw java.lang.IllegalStateException

        java.lang.IllegalStateException: stream has already been operated upon or closed
        	at java.util.stream.AbstractPipeline.sourceStageSpliterator(AbstractPipeline.java:279)
        	at java.util.stream.IntPipeline$Head.forEach(IntPipeline.java:557)

```
* Streams can be infinite, if you design them to be. If you don't want that make sure you set some limits (using .limit() )
* Don't overuse streams
* Collections not Map
* Streams prefer immutability
* Pipelining is a chain of various stream operations. 


####//TODO Collector interface

Learn it!

## OPTIONAL

_Optional_ is a useful tool . It has 2 states present when it has value. empty when it does not.
**Variable** of type _Optional_ **must never be null**. Otherwise it pointless.
**Use** _Optional_ **instead of null on public return types as it seems how it was designed to use.**
Optional is a class.It increase memory use  and reduce performance  a bit.

#### Tips and Tricks
* Don't use as parameters.
* Don't use ifPresent method use orElse instead
* One thing to note is the specialised versions (e.g. OptionalInt) do not have an ofNullable, although we can still do a test and manually get an OptionalInt.empty() if we want.
* rElseGet() is that orElse() will always be executed if the Optional<T> is null or not. But orElseGet() will only be executed when Optional<T> is null.
## DATE AND TIME
New  Date and Time Api Java 8 has very useful property: Immutability which means thread safe.
Use specific class implementation (LocalDate,LocatTime ) that match your need.
The Duration provides quantity or amount of time in terms of seconds and nanoseconds.
General rule is Interface is on the left ,Concrete implementation on the right. owner for Date and time use Concrete is on left and right (Creator didn't explain why)

It has nanosecond precision
LocalDate date = LocalDate.of(2016,7,30)

// LocalDate is date without time in Java 8 // LocalTime is time without date in Java 8 // LocalDateTime is both date and time e.g. LocalDate + LocalTime // but without Timezone information

Read more: http://javarevisited.blogspot.com/2017/01/how-to-create-localdatetime-in-java-8.html#ixzz4X9otMana
 LocalDateTime vs ZonedDateTime
ZonedDateTime has information about time zone while LocalDateTime does NOT

Useful method:
``` java
Duration.between(LocalDateTime.now(),LocalDateTime.now().plus(4,DAYS)).getSeconds();
Period.between(LocalDate.now(),LocalDate.now().plus(4,DAYS)));
```
#### Tips and Tricks
* Use instead Joda-Time.
* Don't use java.util.Date or java.util.Calendar
* Use http://www.threeten.org/threeten-extra/ if you need extra features.
* LocalDateTime  date and time information without timezone
## MAPS

Maps do not support stream (there is no stream() method, but they have few enchantments that allows you to create streams 
on  the keys (map.keySet().stream()), values (map.values().stream() ) or entries ( map.entrySet().stream()) .

#### Tips and Tricks
* ``` putIfAbsent``` prevents us from writing additional if null checks; 

### OTHER

* You can now use the same annotation multiple times for one method,class and so on.
* Java is not a functional language, so don't follow functional suggestion blindly in Java as this is object-oriented language.
* No permGen anymore :)
* If you upgrating project to use Java 8 you need have a good test coverage.

## PREDICATE

A Predicate is Boolean expression which returns either true or false. Predicate a functional interface . It used use to evaluate a condition on group/collection of similar objects such that evaluation can result either in true or false.

> In mathematics, a predicate is either a relation or the boolean-valued function that amounts to the characteristic function or the indicator function of such a relation. A function P: X→ {true, false} is called a predicate on X.
 (Source: Wikipedia)


## METHOD REFERENCE

##TODO
a generic interface.
 ## DATE and TIME
 
 What's wrong with old Date?
 * Date is mutable.
 * It has many deprecated methods as they are misleading (as they suggest to represent date, which is not truth as Java's Date represents point in time without any specific calendar (day,month or year))
 * java.sql.Date extends java.util.Date .However it violating Liskov substitution principle.
 java.util.Date.toInstant() works as expected but java.sql.Date.toInstant()fails unconditionally with UnsupportedOperationException
 
Things to remember: 
 * Converting Instant to ZonedDateTime in any way without providing explicit ZoneId is probably a bug.
 * It is important to understand Why is all of this important? When you make an agreement with your client that something is supposed to take one day vs. 24 hours this may actually make a huge difference on certain days. (https://dzone.com/articles/guide-to-time-and-date-in-java-part-2) 
 * Store and send time either as a timestamp (long value) or as an ISO 8601 which is basically what Instant.toString() does as per the documentation.
 
time and calendars. For example, some people believe that the time difference between two locations is always constant.
* First is daylight savings time

##Interface

### Functional interface
Functional interfaces provide target types for lambda expressions and method references.
 Each functional interface has a single abstract method, called the functional method for that functional interface, to which the lambda expression's parameter and return types are matched or adapted.
 FunctionalInterface. This annotation is not a requirement for the compiler to recognize an interface as a functional interface, but merely an aid to capture design intent and enlist the help of the compiler in identifying accidental violations of design intent.
 
Examples:
 The java.lang.Runnable and java.util.concurrent.Callable are two great examples of functional interfaces
 
### Default method
 They allow adding new methods to existing interfaces without breaking the binary compatibility with the code written for older versions of those interfaces.
 The difference between default methods and abstract methods is that abstract methods are required to be implemented. But default methods are not.
 
 before declaring method as default it is better to think twice if it is really needed as it may cause ambiguity and compilation errors in complex hierarchies. 
 
## Lambdas
Lambda expressions allows you treat functionality as method argument, or code as data.
The return statement is not required if the lambda body is just a one-liner.


### Method reference
Method reference allows you refer to the existing method by name (useful  a lambda expression does nothing but call an existing method). 
Method references provide the useful syntax to refer directly to exiting methods or constructors of Java classes or objects (instances)

## STREAM
A stream is a sequence of elements. 
A pipeline is a sequence of stream operations, which in this example is filter- map-forEach. I
gregate operations typically accept lambda expressions as parameters

### The map Method
Once you have a Stream object, you can use a variety of methods to transform it into another Stream object. The first such method we’re going to look at is the map method. It takes a lambda expression as its only argument, and uses it to change every individual element in the stream. Its return value is a new Stream object containing the changed elements

## OTHER
The arrow token, ->

### Function
**Interface Predicate<T>**  Represents a predicate (boolean-valued function) of one argument.
**interface Consumer<T>**  Represents an operation that accepts a single input argument and returns no result. Unlike most other functional interfaces, Consumer is expected to operate via side-effects.
**interface Function<T,R>**  Represents a function that accepts one argument and produces a result.


 

 
#### **Functional Interface**

**Definition:**
A functional interface has exactly one abstract method. Since default methods have an implementation, they are not abstract. If an interface declares an abstract method overriding one of the public methods of java.lang.Object, that also does not count toward the interface's abstract method count since any implementation of the interface will have an implementation from java.lang.Object or elsewhere.
An instances of functional interfaces can be created with lambda expressions, method references, or constructor references.
**Docs:** https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html

Add @FunctionalInterface to Your Functional Interface


#### **Method References**
 
 
#### Optionals

Please don't use it as the field of a Java-Bean.


##Resources
* https://www.javacodegeeks.com/2014/05/java-8-features-tutorial.html
* https://docs.oracle.com/javase/tutorial/java/javaOO/lambdaexpressions.html
* http://blog.joda.org/2014/11/optional-in-java-se-8.html
* https://www.youtube.com/watch?v=wOks4LW6I24
* https://blog.jooq.org/2014/06/13/java-8-friday-10-subtle-mistakes-when-using-the-streams-api/
* Java-8-best-practices by Stephen-Colebourne
* http://zeroturnaround.com/rebellabs/how-your-addiction-to-java-8-default-methods-may-make-pandas-sad-and-your-teammates-angry/
* https://blog.jooq.org/2014/06/13/java-8-friday-10-subtle-mistakes-when-using-the-streams-api/
* https://aboullaite.me/java-9-enhancements-optional-stream/
* https://dzone.com/articles/dipping-into-java-8-streams