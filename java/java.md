## **HONEST WARNING**

**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._

# THE JAVA REVISION BOOK BASICS

# DICTIONARY

## ::

    :: keyword is a way pass references of methods or constructors. Default methods cannot be accessed from within lambda
    expressions. Predicates are boolean-valued functions of one argument.

## Java

    Java is a general-purpose, object-oriented computer programming language. main principle was to  "write once, run anywhere". 
    It means Java applications are typically compiled to bytecode that can run on any Java virtual machine (JVM) regardless of computer architecture.
    Object-oriented programming based on abstract concept of real-world object where each object has state and behaviour. 
    It contains 4 significant features, such as encapsulation, inheritance, polymorphism and abstraction.

## Annotation

    Annotation is not part of the program itself. It contains information for the compiler; it helps software tools process
    and/or generate data/code.

## Abstraction

    It is the process of separating ideas and signatures. It is a commonly used component from specific implementation. 
    Implementation is left for subclasses.  
    It is used to hide specific details and only show the essential features of the object.
    An interface is a way to achieve abstraction in Java. 
    It is similar to a class with a group of methods with empty bodies without implementation, and it can contain final fields. 
    Since Java 9 default method with implementation is allowed.

### Autoboxing and Unboxing?

    It is conversion between a primitive type and its object wrapper.

 	for example
 		Stack<Integer> example = new Stack<Integer>();
 		example.push(17); 
    (autoboxing will swap 86 with new Integer(86) )

## Algorithm

    An algorithm is a recipe to instructs how to perform a task. It is a sequence of instructions that accomplishes a task
    in a finite time period. The algorithm receives zero or more inputs, produces at least one output, consists of clear and
    unambiguous instructions, terminates after a finite number of steps.

## BIG O NOTATION

    The Big-O notation is used for describing algorithm performance, scalability, execution and complexity factors in the
    worst case scenario as the number of elements in a data structure increases.

### BIG O NOTATION from best to worst:

    O(1) 	
    Constant O(log n)
    Logarithmic O(n)
    Linear O(n log n) 	
    Linear Logarithmic O(n2) 	
    Quadratic O(n3) 	
    Cubic

### List and sets:

    Structure       get     add     remove  contains
    ArrayList       O(1)    O(1)    O(n)    O(n)    
    LinkedList      O(n)    O(1)    O(1)    O(n)
    HashSet         O(1)    O(1)    O(1)    O(1)
    LinkedHashList  O(1)    O(1)    O(1)    O(1)
    TreeSet         O(logn) O(logn) O(logn) O(logn)

### Maps:

    Structure       Get     Put     Remove  ContainsKey
    HashMap         O(1)    O(1)    O(1)    O(1)
    LinkedHashMap   O(1)    O(1)    O(1)    O(1)
    TreeMap         O(logn) O(logn) O(logn) O(logn)

## Checked Exceptions

    Checked exceptions are checked at compile-time. Checked exceptions are exceptions that we can anticipate, 
    and we should be able to recover from them. If a method is throwing a checked exception, 
    it should handle the exception using try-catch block or declare the exception using the throws keyword.
    
    Examples:
    `Checked Exceptions SQLException, IOException, DataAccessException, ClassNotFoundException and InvocationTargetException.`

## Class

    It is a blueprint from which objects are created.

## Constructor

    A constructor gets invoked when a new object is created. Every class has a constructor. (You don't need to provide
    default constructor. It will be done by compiler).

## Constructor Overloading

    The constructor overloading is similar to method overloading in Java. 
    Different constructors can be created for a single class.

## The Java Collections Framework (JCF)

 	The Java collections framework (JCF) is a set of classes and interfaces that implement a commonly reusable collection of data structures.

## CopyOnWriteArrayList

    A version of ArrayList that makes a cloned copy of the underlying ArrayList to implement all operations and
    modifications. It is fail-safe, and it will never throw ConcurrentModificationException during iteration.

## Data structure

    The data structure is a container (in java will be a class) that provides storage for data elements and 
    capabilities for manipulating data items (add, remove, swap, find and so on).

    Benefits are:

    - Reusability and better code quality as a result of the use of well-tested collections framework classes.
    - Reduced Effort for code maintenance by using collection classes shipped with JDK.

## Data Types supported by Java?

    Java has 8 types (boolean, byte, char, double, float, int, long, short).

## DATE AND TIME IN JAVA 8

    What was the design principles for date and time in Java 8?
    
    * Immutability: All the classes in the new Date-Time API are immutable and suitable for multithreaded environments.
    * Separation of Concerns: The new API clearly separates human-readable date time and machine time (UNIX timestamp).
      It defines separate classes for Date, Time, DateTime, Timestamp, Timezone etc.
    * Clarity: The methods are clearly defined and perform the same action in all the classes. For example, to get the current instance, we have now() method. There are format() and parse() methods defined in all these classes rather than having a separate class for them. All the classes use Factory Pattern and Strategy Pattern for better handling. Once you have used the methods in one class, working with other classes won’t be hard.
    * Utility operations: All the new Date-Time API classes comes with methods to perform common tasks, such as plus,      minus, format, parsing, getting a separate part in date/time etc.
    * Extendable: The new Date Time API works on the ISO-8601 calendar system, but we can use it with other non-ISO calendars as well.

    Worth to know:

    * The new Java 8 java.time.
      Instant is the equivalent class to the classic java.util.Date Date in Pre-Java 8 does not represent… date. 
      Seriously, officially, date is “[…] the day of the month or year as specified by a number […]” 
      whereas in Java it represents a point in time without any specific calendar (day/month/year). 
      Many methods in Date are deprecated for a reason because they lead you to believe. 
      Date represents, you know, date.
      Timestamp (long value) or as ISO 8601, which is basically what Instant.toString() is.
    * Why Java 8 introduced new data and time classes. What was wrong with time and date?
        * Java Date Time classes are not defined consistently; we have Date Class in both java.util as well asjava.sql packages. Again formatting and parsing classes are defined in java.text package. java.util.Date contains both date and time, whereas java.sql.Date contains the only date. Having this in java.sql package doesn’t make sense. Also, both the classes have the same name, which is a very bad design itself.
        * There are no clearly defined classes for time, timestamp, formatting and parsing. We have java.text.DateFormat abstract class for parsing and formatting need. Usually, SimpleDateFormat class is used for parsing and formatting.
        * All the Date classes are mutable, so they are not thread-safe. It’s one of the biggest problems with Java Date and Calendar classes. ⦁ Date class doesn’t provide internationalization; there is no timezone support. So java.util.Calendar and java.util.TimeZone classes were introduced, but they also have all the problems listed above.

## DEADLOCK

    Deadlock is a situation when two or more threads waiting for each other to release the lock and get stuck for infinite
    time. It will only happen in the case of multithreading. How to fix deadlock? or How to avoid deadlock in Java? Real
    reason for the deadlock is not multiple threads but the way they access lock. If you provide ordered access, then the
    problem will be resolved.

## Errors

    Errors are exceptional cases that are out of the scope of the application, and that is impossible to anticipate and
    recover from them (JVM crashes, HW failure).

## Encapsulation

    Encapsulation (data hiding) is a technique that gives the ability to control access to their internal characteristics and behaviour. It is accomplished by Java access modifiers: public, private, default(no modifier)  and protected.
    * It increases usability. 
    * It improves the maintenance of code.
    * It helps object to interact with each other correctly.

## Enum

    * Only private constructors are allowed in enum types
    * Enum constants are created only once for the whole execution.
    * Enum types are final by default.
    * All enum types are Comparable and Serializable by default.

## EnumSet.

    It is a Set implementation that can be used with enum types. All the elements must come from one enum type specified
    explicitly or implicitly. It is not synchronized. NULL keys are not allowed.

# Exception

    An exception is an error event that can happen during the execution of a program and disrupts its normal flow. When an
    error occurs while executing a statement, it creates an exception object, and then the normal flow of the program halts,
    and JVM tries to find someone that can handle the raised exception.
    - Example of unchecked exceptions (NullPointerException, ArrayIndexOutOfBoundsException, ArithmeticException, IllegalArgumentException)

## GARBAGE COLLECTORS

    Garbage Collection is a process that manages the allocation and release of memory of the application. For example, It frees memory allocated to objects that are not being used by the program any more.

### Garbage First (G1).

    It a newish collector that’s recently become more stable and is in slowly increasing usage.  

### The Z Garbage Collector

    ZGC is a low-latency GC designed to work well with huge amounts of memory. The Oracle documentation refers to multi-terabyte heaps in its description of Z. Oracle introduced ZGC in Java 11. In Java 12, Oracle added performance fixes and class unloading even though Z is still in experimental status. It's only available on 64-bit Linux.

### Shenandoah

    Shenandoah GC is a garbage collector with low pause times. These times are short and predictable, regardless of the size of the heap.
    How Does Shenandoah Work? Shenandoah's design trades concurrent CPU cycles and space for pause time improvements. The forwarding pointer makes it easy to move objects, but the aggressive moves mean Shenandoah uses more memory and requires more parallel work than other GCs. But it does the extra work with very brief stop-the-world pauses.https://dzone.com/articles/java-garbage-collection-3?edition=479246&utm_source=Zone%20Newsletter&utm_medium=email&utm_campaign=java%202019-05-07

## Generics

    Generics allow us to specify the type of Object that a collection can contain, so if you try to add any element of other
    types, it throws a compile-time error. This avoids ClassCastException at Runtime because you will get the error at
    compilation.

## hashcode()

    A hashcode() is a method that returns an integer number. It is used some data structures (like theHashMap): because it
    is one of the fastest solutions around for random-access key-value storage, which means it allows objects to be
    stored/retrieved quickly in a HashMap. Objects that are equal must have the same hash code within a running process.
    Note: An alternative: SHA1. Objects with the same hash code NOT MUST be equal hashCode does not guarantee the same
    result in different executions. You may know that cryptographic hash codes such as SHA1 are sometimes used to identify
    objects (Git does this, for example).

## Hashmap //TODO improve it

    * The important characteristics of a HashMap are its capacity, its load factor and the threshold resizing.
    * Hashmap does not implement a collection interface.
    * The bucket is an array (Normally LinkedList or balanced tree)  where you store elements with the same hashcode.
    * Threshold resizing is set at 0.75f by default.
    * It can only be one null key in HashMap.
    * If two objects are equal, then calling hashCode() on both objects must return the same value. When inserting an object into a hashtable you use a key. The hash code of this key is calculated and used to determine where to store the object internally. When you need to lookup an object in a hashtable, you also use a key. The hash code of this key is calculated and used to determine where to search for the object.
    * The hash code only points to a certain "area" (or list, bucket etc.) internally. Since different key objects could potentially have the same hash code, the hash code itself is no guarantee that the right key is found. The hashtable then iterates this area (all keys with the same hash code) and uses the key's equals() method to find the right key. (Collection view of a map can be obtained using entrySet() method.
    * To obtain a collection-view of the keys, keySet() method can be used.)
    * Map.Entry interface - This interface gives a map entry (key-value pair).

## Java Heap

    Java Virtual Machine gets some memory from Operating System. JVM uses this memory for all its needs and part of this
    memory is called Java heap memory.

## Immutable objects

    In Java, Immutable objects offer a number of advantages for building reliable applications. We don’t need to write
    defensive or protective code to keep the application state consistent; our code can be simpler, more concise, and less
    error-prone than defining mutable objects.

    Some of the key benefits of immutable objects are:

      - Thread safety
      - Atomicity of failure
      - Absence of hidden side-effects
      - Protection against null reference errors
      - Ease of caching
      - Prevention of identity mutation
      - Protection from instantiating logically invalid objects
      - Protection from unintentional corruption of existing objects

## Inheritance

    Inheritance gives an object the ability to use the fields and methods of the parent class. It is helpful technique because
    it allows you to re-use code and can be used to add additional features to an existing class without modifying it.

### Does Java support multiple inheritance?

    No. Java does not support multiple inheritances. Each class can extend only one class, BUT It can implement more than one
    interface. Why? It is a design decision. Different experts have different opinions on that. I guess they didn't have a usable and error-proof solution for the C++ diamond problem.

## Java Bean (POJO)

    JavaBean is a normal Java class with with set of coding conventions rules to make a reusable software component. Implements java.io.Serializable interface Provides no argument constructor Provides getter and setter methods for accessing its properties.

## Iterator

    The Iterator interface has several methods that can iterate over any Collection. Each Java Collection contains the
    iterator method that returns an Iterator instance.

## What is JDBC?

    JDBC is a Java database connectivity technology. This technology is an API for the Java programming language that
    defines how a client may access a database, query and manipulate data. It allows the programmer to interact with the
    database without concern about what database is used.

## Java Management Extensions (JMX)

    Java Management Extensions (JMX) is a Java technology that supplies tools for managing and monitoring applications,
    system objects, devices (such as printers) and service-oriented networks. Those resources are represented by objects
    called MBeans (for Managed Bean).

## JSP

    Ancient technology.Ask Software archeologies for details.

## Lambda

    Lambda expression are cute little anonymous method.
    Lambda expression is a more compact way of writing an anonymous function or implementing a functional interface.

## LinkedHashSet

    LinkedHashSet is in some sense intermediate between HashSet and TreeSet. Implemented as a hash table with a linked list
    running through it, it provides insertion-ordered iteration that is not the same as sorted traversal guaranteed by
    TreeSet. Also, since we used a LinkedHashSet, the iteration order is the same as the insertion order. If you do not need
    this behaviour, use a HashSet for more efficiency.

## List

    Very commonly used to create an ordered list of items. This list may contain duplicates. ArrayList is an implementation
    of the List interface. A list can be made thread-safe using Collections.synchronizedList thus removing the need for
    using Vector. Here’s some more info on why Vector is essentially obsolete. Set: Similar to list but does not allow
    duplicates. HashSet implements the Set interface.

## Marshalling and Demarshalling?

    When an application wants to pass its memory objects across a network to another host or persist it to storage, the
    in-memory representation must be converted to a suitable format. This process is called marshalling, and the revert
    operation is called demarshalling.

## Map

    Useful if you have unordered items in the form of key, value pairs and require efficient retrieval, insertion,
    and deletion operations. HashMap, Hashtable, LinkedHashMap are all implementations of the Map interface.

## A managed bean - sometimes simply referred to as an MBean -

    It is a type of JavaBean, created with dependency injection. The MBean represents a resource running in the Java virtual
    machine, such as an application or a Java EE technical service (transactional monitor, JDBC driver, etc.). They can be
    used for collecting statistics on concerns like performance, resources usage, or problems (pull); for getting and
    setting application configurations or properties (push/pull); and notifying events like faults or state changes (push).

## method

    The method is a collection of statements that are grouped together, which is referred to by name and can be called.

## A method reference

    A method reference is a more compact and easy-to-read construct that replaces a lambda expression that does nothing more
    than invoking an existing method.

    Types of Method References:

    - Type Syntax Method Reference Lambda expression Reference to a static method Class::staticMethod String::valueOf s -> String.valueOf(s)
    - Reference to an instance method of a particular object instance::instanceMethod s:toString () -> “string”.toString()
    - Reference to an instance method of an arbitrary object of a particular type Class:instanceMethod String::toString s -> s.toString()
    - Reference to a constructor Class::new String::new () -> new String()

## Method Overloading

    Method overloading in Java occurs when two or more methods in the same class have the exact same name but different parameters.

## Method Overriding

    Method overriding in Java occurs when a subclass has the same method as a parent class. Overridden methods must have the same name, argument list, and return type.

## Object

    It is a particular instance of a class (with its own variables, methods, and data structures).

## OOP concepts:

    abstraction , encapsulation , inheritance and polymorphism

## Package

    It is a namespace for organizing classes, interfaces and so on in a logical structure.

## PATH environment variable

    - It is a way for the system to run the executables (javac.exe, java.exe, javadoc.exe, and so on) from any directory
      without having to type the full path of the command
    - The CLASSPATH variable is one way to tell applications, including the JDK tools, where to look for user classes. If a
      class is not found in CLASSPATH then Java throws ClassNotFoundException.

## Polymorphism

    Polymorphism (the State of having many shapes) is the ability for method to perform tasks in different ways. Subclasses of a class can define their own unique behaviours and/or re-use one of the parent class's same functionality. In Java, it is done, for example, in method overriding.

## Remote Method Invocation (RMI)

    The Java Remote Method Invocation (RMI) system allows an object running in one Java virtual machine to invoke methods on
    an object running in another Java virtual machine. RMI provides for remote communication between programs written in the
    Java programming language. It is an object-oriented equivalent of remote procedure calls (RPC), with support for the
    direct transfer of serialized Java classes and distributed garbage collection.

## Sealed classes and interfaces

    Sealed classes(interfaces) restrict which other classes(interfaces) may extend or implement them. Sealed class must have
    subclasses, so you need to have at least one subclass; otherwise, just declare plain old 'final' modifier if you don't
    want the class to have subclasses.

## SerialVersionUID

    You should always define SerialVersionUID for a serializable class and you should always define it. If you don't define
    then JVM will calculate it for you but if you modify anything you will get a different SerialVersionUID which means you
    won't be able to restore object saved by previous version of your program.

## JAVA SERVLET

    The javax.servlet.Servlet interface defines the three methods known as the life-cycle method.

    1.  init()      - the servlet is constructed, then initialized with the init() method.
    2.  service()   - Any request from the client are handled initially by the service() method before delegating to the doXxx() methods in the
    case of HttpServlet.
    3.  destroy()   - The servlet is removed from service, destroyed with the destroy() method, then garbaged collected and finalized.

## Static keyword

 	It indicates that field, method or class has a single instance for the whole class that defines it and A static variable in Java belongs to its class and its value remains the same for all its instances.

## Static Classes

    Do not allow instantiation of a static class. Always create a private constructor. Static classes should be stateless, immutable, not allow subclassing, and thread-safe. Static classes should be side-effect free and provided as utilities, such as filtering a list.

## Thread

    Thread in Java is an independent path of execution that is used to run two tasks in parallel.
    The Java Virtual Machine allows an application to have multiple threads of execution running concurrently.

## System Properties

    The System class maintains a set of properties - key/value pairs - that define traits or attributes of the current
    working environment. When the runtime system first starts up, the system properties are initialized to contain
    information about the runtime environment. It including information about the current user, the current version of the
    Java runtime, and even the character used to separate components of a filename.

## Volatile keyword

    Voltile variable in Java is a special variable which is used to signal threads, 
    compiler that this particular variables values is going to be updated by multiple thread inside Java application. 
    By making a variable volatile using volatile keyword in Java, 
    application programmer ensures that its value should always been read from main memory
    and thread should not use cached value of that variable from there own stack. 
    Volatile keyword can only be applied to variable, it can not be applied to class or method. 
    using volatile keyword along with class and method is compiler error. 
    Any variable which is shared between multiple threads should be made variable, 
    in order to ensure that all thread must see latest value of volatile variable.

# RANDOM TIPS

1. Consequently, an amount of money should never ever be stored in a floating-point data type (float, double). For
   calculations, the class BigDecimal provides an excellent facility.
2. When using streams,use ordered collection when u use dropWhile/takeWhile to avoid sneaky bugs.
3. Objects.isNull vs object == null. Objects.isNull is intended for use within Java 8 lambda filtering. However value is
   limited to helps readability for some style preference For example some guides prefere
   this: ```.stream().filter(Objects::isNull```    than: ```.stream().filter(x->x==null)```
4. The List returned by Arrays.asList() is an immutable list. Attempting to remove (or add) items to such a list results
   in an UnsupportedOperationException
5. To avoid ConcurrentModificationException we can use concurrent collection classes to avoid
   ConcurrentModificationException while iterating over a collection, for example CopyOnWriteArrayList instead of
   ArrayList.
6. If we need to sort an array of Objects, we can use Arrays.sort(). If we need to sort a list of objects, we can use
   Collections.sort(). Both these classes have overloaded sort() methods for natural sorting (using Comparable) or
   sorting based on criteria (using Comparator). Collections internally use the Arrays sorting method, so both have the
   same performance except that Collections take some time to convert the list to an array. Streams can sort collections
   too.
7. **Finally** is _not executed_ if the** System.exit** method is called _inside_ a try block.
8. equals() method is used for checking the equality of two objects defined by business logic. == (the equality)
   operator is used to compare primitives and objects.
9. What are some of the best practices relating to the Java Collection framework ?
    1. Use immutable classes provided by the Java Development Kit (JDK) as a key in a Map, in order to avoid the
       implementation of the hashCode and equals methods for our custom class.
    2. Choosing the right type of the collection to use, based on the application’s needs, is very crucial for its
       performance. For example if the size of the elements is fixed and know a priori, we shall use an ⦁ Array, instead
       of an ⦁ ArrayList.
    3. Some collection classes allow us to specify their initial capacity. Thus, if we have an estimation on the number
       of elements that will be stored, we can use it to avoid rehashing or resizing.
    4. Always use Generics for type-safety, readability, and robustness. Also, by using Generics you avoid the⦁
       ClassCastException during runtime.
    5. Return zero-length collections or arrays as opposed to returning a null in case the underlying collection is
       actually empty.
10. Serialization of variables. Variables like static and transient will be initialized to their default value after
    de-serialization because transient and static fields are never get serialized. There is an interface available to
    validate the object and its data called ObjectInputValidation. It has validateObject() method.
11. Volatile is a field modifier, while synchronized modifies code blocks and methods.
12. An example of how to use the AtomicInteger class. The java.util.concurrent.atomic package provides very useful
    classes that support lock-free and thread-safe programming on single variables. Among them, the AtomicInteger class
    is a wrapper class for an int value that allows it to be updated atomically. The class provides useful methods, some
    of which will be shown in the code snippet below. The most common use of the AtomicInteger is to handle a counter
    that is accessed by different threads simultaneously.

# FAQ

## When does ConcurrentModificationException occur?

    ConcurrentModificationException occurs when a data collection tries to modify while that collection is actively in use, as when something we are iterating on is modified.

## Concurrent Modification?

    When one or more thread is iterating over the collection, in between, one thread changes the structure of the
    collection (either adding the element to the collection or by deleting the element in the collection or by updating the
    value at particular position in the collection) is known as Concurrent Modification

## What peek() in the queue interface?

    Peek() returns the head of the queue. It does not remove any element. It returns null when the queue is empty.

## What is a heap dump ?

    A heap dump is a snapshot of your application’s memory in a point in time. It contains information such as what are the objects in memory, what values do they carry, what is their size, what other objects do they referenc It used for troubleshooting memory related, OutOfMemoryError problems.

## What is a Thread Dump?

    A thread dump is a snapshot of all threads running in the application at a point in time. It contains all the information about each thread in the application such as thread state, thread Id, native Id, thread name, stack trace,  and priority.
    It is used for troubleshooting production problems such as CPU spikes, unresponsiveness in the application, poor response time, hung threads, high memory consumption.

## Can you override static method in Java?

    No. It is worth nothing that you can declare and define static method of same name and signature in child class, this will hide the static method from parent class

## How do you convert bytes to character in Java?

    Bytes are converted to character or text data using character encoding. When you read binary data from a file or network endpoint, you provide a character encoding to convert those bytes to equivalent character. Incorrect choice of character encoding may alter meaning of message by interpreting it differently.

## What is Perm Gen space in Heap?

    It was removed in Java 8. The permanent generation is being removed in favour of  metaspace.

## What does stop-the-world mean?

    The term ‘stop-the-world’ is used to mean that all of the threads are paused in order to perform garbage collection.

# What is the difference between Exception and Error in Java?

    Exception and Error classes are both subclasses of the Throwable class.
    The Exception class is used for exceptional conditions that a user’s program should catch.
    The Error class defines exceptions that are unrecovable.

## Difference between Serializable and Externalizable in Java?

    - Serializable is a marker interface with no methods defined to allow serialization/deserialization.
    - Externalizable extends Serializable interface and add two methods defined on it e.g. readExternal() and
        writeExternal() which allows you to control the serialization/deserialization process.
    - Serializable uses default serialization process which can be very slow for some application.

## What differences exist between Iterator and ListIterator?

    - An Iterator can be used to traverse the Set and List collections. ListIterator can be used to iterate only over Lists.
    - Iterator can traverse a collection only in the forward direction. ListIterator can traverse a List in both directions.
    - The ListIterator implements the Iterator interface and contains extra functionality, such as adding an element,
      replacing an element, getting the index position for previous and next elements, etc.

## What is difference between fail-fast and fail-safe?

    - Fail fast iterator while iterating through the collection, instantly throws Concurrent Modification Exception if there
      is a structural modification of the collection. Oracle docs said: the fail-fast behaviour of an iterator cannot be
      guaranteed.
    - Fail-Safe Iterator makes copy of the internal data structure (object array) and iterates over the copied data
      structure. Any structural modification done to the iterator affects the copied data structure. So, the original data
      structure remains structurally unchanged. Hence, no ConcurrentModificationException throws by the fail-safe iterator.

## How HashMap, ConcurrentHashMap, and LinkedHashMap handles collisions ?

    A collision occurs when a hash function returns the same bucket location for two different keys.  HashMap handles collision by using a linked list to store map entries ended up in the same array location or bucket location.
    However, in the worst-case scenario, when there are many collisions, performance drop from O(1) to O(n). To address this, HashMap has a threshold. When they reach, they switch to balanced tree from linked list to handle frequently hash collisions. - Default is TREEIFY_THRESHOLD = 8 . This will improve the worst-case performance from O(n) to O(log n).

## What is the importance of hashCode() and equals() methods?

    HashMap uses Key object hashCode() and equals() method to determine the index to put the key-value pair. These methods
    are also used when we try to get value from HashMap. If these methods are not implemented correctly, two different keys
    might produce the same hashCode() and equals() output, and in that case, rather than storing it at a different location, HashMap
    will consider the same and overwrite them.

## What is the difference between HashSet and TreeSet?

//TODO improve it

## What’s difference between Streams and collections ?

    No storage. A stream is not a data structure that stores elements; instead, it conveys elements from a source such as a
    data structure, an array, a generator function, or an I/O channel through a pipeline of computational operations.
    Functional in nature. An operation on a stream produces a result but does not modify its source. For example, filtering
    a Stream obtained from a collection produces a new Stream without the filtered elements, rather than removing elements
    from the source collection. Laziness-seeking. Many stream operations, such as filtering, mapping, or duplicate removal,
    can be implemented lazily, exposing opportunities for optimization. For example, "find the first String with three
    consecutive vowels" need not examine all the input strings. Stream operations are divided into intermediate (
    Stream-producing) operations and terminal (value- or side-effect-producing) operations. Intermediate operations are
    always lazy. Possibly unbounded. While collections have a finite size, streams need not. Short-circuiting operations
    such as limit(n) or findFirst() can allow computations on infinite streams to complete in finite time. Consumable. The
    elements of a stream are only visited once during the life of a stream. Like an Iterator, a new stream must be generated
    to revisit the same elements of the source.

## What is Comparable and Comparator interface?

    - A comparable is an interface. An object that implements this interface is capable of comparing itself with another object. To implement this interface class must contain a method called compareTo.
    - A comparator object is capable of comparing two different objects. The class is not comparing its instances but some other class’s instances. This comparator class must implement the java.util.Comparator interface.
    - The main difference between these two is that you could create multiple Comparators to define multiple sorting orders based upon a different object attribute.

## _Why Collection doesn't extend Cloneable and Serializable interfaces?_

    It was a design decision to leave up to the concrete implementations of Collection how they want to maintain cloning or
    serializing gives better flexibility as Collection is an abstract representation.

## _Can you access non-static variable in static context?_

    No. A static variable in Java belongs to its class, and its value remains the same for all its instances. A static
    variable is initialized when the JVM loads the class. Suppose your code tries to access a non-static variable without
    any instance. The compiler will complain because those variables are not created yet, and they are not associated with
    any instance.

## _Difference between final, finally, and finalize?_

    - Final is a keyword that indicates that variables cannot change. The method cannot be overridden, and the class cannot be subclassed.
    - Finally is a block of code that is always executed after try/catch block. (Java 7 has a try with resources statement)
    - Finalize is a method called before is an object is a garbage collected.

## _Create a map without need to resize_

```Map map = new HashMap(1 + (int) (collection.size() / 0.75));```

    HashMap implementation doesn't quite behave like this. 
    It sets its internal threshold to threshold = (int)(capacity * loadFactor). 
    So it will resize after 75% of the collection have been inserted into the map. 
    The above code will thus always cause extra garbage.

//TODO add example

## _What are pass by reference and pass by value? Is Java pass by reference and pass by value?_

    According to specification Java is strictly pass-by-value. Read the Java Language Specification (JLS). It's spelt out,
    and it's correct. In https://docs.oracle.com/javase/specs/jls/se17/html/jls-8.html#jls-8.4.1
    
    However, based on my experience correct answer for many reviews accept only this answer: By value = changes doesn't
    affect original By reference = changes are reflected where original value is used.
    
    The object is passed by value – this means that a copy of the object is passed. If changes are made to that object, it
    doesn't affect the original value. The object is passed by reference; this means that the actual object is not passed;
    rather, a reference of the object is passed. Any changes made by the external method are also reflected in all places.

## _Why Is the String Object Immutable in Java?_

    It is a design choice for a few security, multithreading, memory optimisation reasons like:

    1. Since String is immutable, it makes them thread-safe for multithreading, and it avoids the usage of synchronisation
       for thread safety. It makes a good performance because a single String instance can be shared across different
       threads.
    2. Since String is immutable, its hashcode is cached at the creation time, and it doesn't need to be calculated again.
       This makes it a great candidate for a key in a map, and its processing is fast than other HashMap key objects. This
       is why String is the most-used object of HashMap keys.
    3. String pool is possible. Different String variables can refer to the same string variable in the pool. If String were
       not immutable, then if any variable have changed the value, it would have been reflected in other variables. String
       pool allows Java Runtime saves a lot of Java heap space.
    4. It prevents many security issues like Since String is immutable, it's value can't be changed. Otherwise, any hacker
       could change the referenced value to cause security issues in the application. As it used in the Java classloader,
       and immutability provides security that the correct class is getting loaded by the Classloader (connections to the
       database)

## _Why wait, notify and notifyAll is defined in Object Class and not on Thread class in Java?_

    It is a language design decision, and I am a software developer. I am not knowledgeable enough about language
    architecture design to comment on it. My guess is based on usage of these methods like Both wait and notifies methods
    are used for inter-thread communication.

## _When you should throw checked exception and when you should throw unchecked exception?_

    I always use unchecked exceptions. The checked exception was an interesting architecture idea, but it broke the
    Open/Closed Principle and didn't work out well in the long term. If a client can reasonably be expected to recover from
    an exception, make it a checked exception. If a client cannot do anything to recover from the exception, make it an
    unchecked exception.

## _Difference between extends Thread vs implements Runnable in Java?_

    The way how I choose it is pretty simple. If you want to add new functionality, then I will extend Thread. Otherwise, I
    will use Runnable/Callable Interface. Why? In Object-oriented programming, extending a class generally means adding new
    functionality, modifying or improving behaviours.

## _What are the differences between Abstraction and Interface, and when to use which?_

    - Abstract Class can have method implementation while Interface can implement default method only.
    - All non-default methods in an interface are implicitly abstract.
    - An abstract class can have a constructor, but an Interface can not have a constructor.
    - An abstract class may contain non-final variables. Variables declared in a Java interface is by default final.
    - You can not extend more than one abstract class. You can implement more than one InterfaceInterface
    - Abstract classes can have a main method so that we can run the application from the abstract class. The Interface can
        not have a main method.
    - If your base contract keeps on changing, then you should use an abstract class.
    - In Java8, Oracle has tried to bridge the gap between abstract class and Interface by introducing default and static
        methods in Interface. The addition of default methods removes many reasons to use abstract classes. The differences
        are the accessibility of data members and methods: abstract classes allow non-static and non-final fields and allow
        methods to be public, private, or protected while interfaces’ fields are inherently public, static, and final, and all
        interface methods are inherently public.

## _How does Java handle a class that implements two interfaces, both of which describe a default method with the same

signature?_

    It is a compilation error.

## Difference between Runnable and Callable interface in Java?

    Like Runnable, Callable also defines a single call() method, but unlike run() method, it can return values and throw exceptions.

## What is the difference between the calling start() and run() method of Thread?

    start() method also starts a new thread.
    If you call the run method directly then it will run on same Thread not on different Thread, which is what original intention would be.

## If you had to change Java, what would you do?

    I think Java is getting better and in decent pace at the moment but some synthetic sugar from Groovy,Kotlin, Scala and Apache Commons. 
    More clean up is required with removind unsafe and depracated parts. 
    For example Java Date/Time was changed in Java8

# Difference between Abstraction and Encapsulation?

    //TODO
    Abstraction and Encapsulation are complementary concepts. Abstraction
    focuses on the behaviour of an object. Encapsulation focuses on the implementation of an object’s behaviour.

# What are ways to iterate list:

    You can iterate over the list in 3 ways: using iterator, using for-each loop or stream.

# Difference between OutOfMemoryError for Java Heap Space and PermGen spac ?

    * "java.lang.OutOfMemoryError: Java heap space" - error messages denotes that Java heap does not have sufficient space andcannot be expanded further
    * "java.lang.OutOfMemoryError: PermGen space" - error message comes when the permanent generation of Java Heap is full,  the application will fail to load a class or to allocate an interned string.

# _Is Java Exception framework handles compile time errors?_

    No.
    It is used to handle runtime errors only.

# _How to decide between HashMap and TreeMap?_

    For inserting, deleting, and locating elements in a Map, the HashMap offers the best alternative. If, however, you need
    to traverse the keys in sorted order, then TreeMap is your better option. Depending upon the size of your collection, it
    may be faster to add elements to a HashMap, then convert the map to a TreeMap for sorted key traversal.

## _Difference between notify and notifyAll?_ //TODO improve it

    The main difference between notify and notifyAll is that notify method will only notify one thread, and notifyAll method
    will notify all Threads waiting on that monitor or lock. When you call, notify only one of waiting for the thread will
    be woken, and it's not guaranteed which thread will be woken, it depends on upon Thread scheduler. Is it matter? While
    if you call notifyAll method, all threads waiting on that lock will be woken up, but again all woken thread will fight
    for lock before executing remaining code and that's why wait is called on loop because if multiple threads are woken up,
    the thread which will get lock will first execute and it may reset waiting for condition, which will force subsequent
    threads to wait. In this case, notify is optimized call over notifyAll because so calling notifyAll method is just a
    waste of CPU cycles.

## _What Is the Difference Between equals() and == ?_

    The equals() method is used for checking the equality of two objects defined by business logic. == or the equality
    operator is used to compare primitives and objects.

## String.valueOf(Object) Vs. Objects.toString(Object).

    Although I typically use String.valueOf(Object) instead of Objects.toString(Object) by default when I want the string "
    null" returned if the passed-in object is null, the alternate overloaded method Objects.toString(Object, String) has the
    advantage of specifying any string returned by the method if the passed-in object is null.

## Difference between <? super T> and <? extends T> in Java ?

    https://stackoverflow.com/questions/4343202/difference-between-super-t-and-extends-t-in-java

# RESOURCES:

0. http://en.wikipedia.org/wiki/Anti-pattern#Programming_anti-patterns
1. http://www.antipatterns.com/antipatt.htm
2. https://glenndejaeger.wordpress.com/2010/04/05/programming-antipatterns/
3. http://www.javacodegeeks.com/2011/10/programming-antipatterns.html
4. http://stackoverflow.com/questions/4343202/difference-between-super-t-and-extends-t-in-java
5. http://javarevisited.blogspot.co.uk/2012/02/why-wait-notify-and-notifyall-is.html
6. http://javarevisited.blogspot.com/2012/10/difference-between-notify-and-notifyall-java-example.html
7. http://javarevisited.blogspot.sg/2011/04/synchronization-in-java-synchronized.html
8. http://www.javacodegeeks.com/2014/04/java-interview-questions-and-answers.html
9. http://javarevisited.blogspot.com/2016/09/how-to-serialize-object-in-java-serialization-example.html
10. https://dzone.com/articles/what-you-need-to-know-about-serialization
11. http://www.javacodegeeks.com/2013/07/java-exception-handling-tutorial-with-examples-and-best-practices.html
12. http://docs.oracle.com/javase/tutorial/essential/exceptions/runtime.html
13. http://javarevisited.blogspot.co.uk/2011/04/garbage-collection-in-java.html
14. http://www.odi.ch/prog/design/newbies.php
15. https://dzone.com/articles/single-responsibility
16. http://examples.javacodegeeks.com/java-basics/encapsulation-in-java/
17. http://java67.blogspot.co.uk/2015/03/top-40-core-java-interview-questions-answers-telephonic-round.html
18. http://javahungry.blogspot.com/2014/04/fail-fast-iterator-vs-fail-safe-iterator-difference-with-example-in-java.html
19. http://www.javacodegeeks.com/2013/02/40-java-collections-interview-questions-and-answers.html
20. https://www.quora.com/How-is-Hashmap-in-Java-implemented-internally-What-are-the-pros-and-cons-to-use-it-What-are-the-complexities-it-provides-for-insert-delete-and-lookup
21. http://javarevisited.blogspot.co.uk/2016/01/how-does-java-hashmap-or-linkedhahsmap-handles.html
22. http://netjs.blogspot.co.uk/2015/05/how-hashmap-internally-works-in-java.html
23. http://javarevisited.blogspot.com/2016/01/how-does-java-hashmap-or-linkedhahsmap-handles.html#ixzz4YenTvj7S
24. http://eclipsesource.com/blogs/2012/09/04/the-3-things-you-should-know-about-hashcode/
25. http://www.javacodegeeks.com/2014/03/how-hashmap-works-in-java.html
26. http://docs.oracle.com/javase/tutorial/essential/exceptions/runtime.html)
27. http://www.wellho.net/mouth/1062_Java-sorting-comparable-v-comparator.html
28. http://www.javacodegeeks.com/2013/07/java-exception-handling-tutorial-with-examples-and-best-practices.html
29. http://beginnersbook.com/2013/04/java-checked-unchecked-exceptions-with-examples/
30. http://beginnersbook.com/2013/04/java-checked-unchecked-exceptions-with-examples/
31. http://bigocheatsheet.com
32. http://www.javacodegeeks.com/2011/04/simple-big-o-notation-post.html
33. http://javarevisited.blogspot.co.uk/2012/02/why-wait-notify-and-notifyall-is.html
34. http://javarevisited.blogspot.com/2012/03/10-object-oriented-design-principles.html#ixzz3EjBs0YFQ
35. http://docs.oracle.com/javase/tutorial/java/concepts/class.html)
36. http://java67.blogspot.sg/2012/08/difference-between-treemap-and-treeset-java.html
37. http://docs.oracle.com/javase/tutorial/java/javaOO/methods.html
38. http://www.javadude.com/articles/passbyvalue.htm
39. https://examples.javacodegeeks.com/core-java/util/concurrent/atomic/atomicinteger/java-atomicinteger-example/

TODO:
https://dzone.com/articles/composition-vs-inheritance

###### ###### ######

Style Guide

1 empty before 14 QUESTION 10 Answer Subject . Keyword and Important important information. Normal information. 2 empty
lines in the end