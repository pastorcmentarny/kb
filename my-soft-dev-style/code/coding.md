## **HONEST WARNING**

**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._

# CODING

## CLASSES AND METHODS:

1. Functions should do one thing .They should do it well. They should do it only. Functions should either do something
   or answer something, but not both.
2. The ideal number of arguments for a function is zero (niladic). Next comes one (monadic), When a function seems to
   need more than three arguments, it is likely that some of those arguments can be wrapped into a class of their own.
   It sounds like cheating, but it’s not. When groups of variables are passed together, they are likely part of a
   concept that deserves a name of its own.
3. Dependent Functions. If one function calls another, they should be vertically close and the caller should be above
   the callee, if at all possible.
4. The first rule of classes is that they should be small. The second rule of classes is that they should be smaller
   than that. As with functions, smaller is the primary rule when it comes to designing classes.
5. The class should have less than 500 lines, and most of those ﬁles are less than 200 lines.
6. Classes should have a small number of instance variables. Each of the methods of a class should manipulate one or
   more of those variables. In general the more variables a method manipulates the more cohesive that method is to its
   class. A class in which each variable is used by each method is maximally cohesive.
7. When cohesion is high, it means that the methods and variables of the class are co-dependent and hang together as a
   logical whole.
8. Use static factories over constructor to have a better readability.
9. Return Empty Collections Instead of null.
10. Make methods final by default. If you do need to override a method (Should you?), remove the final keyword. It is
    good because:
    - You will never accidentally override any method.
    - This specifically applies for static methods, where “overriding” (actually, shadowing) hardly ever makes sense.
11. With this, I’m referring to methods that return values and have side effects at the same time. For instance,
    consider a method that takes a string, writes that string to a file, and then returns a Boolean indicating whether
    or not the operation succeeded. This is “ask and tell,” because invoking the method involves telling the API to do
    something (write to the file) and asking it a question (“what happened?”).

## COMMENTS and DOCUMENTATION:

1. Comments should explain why the class is here not what it does. It is the only role of comment in the documentation.
   The code itself should be written in the way that explains the purpose.
2. Use comments when they add readability to code. Comments should be reserved for technical notes about the code and
   design. It should be used in case where lack of commenting will increase time need to perform changes in code.
3. Comment all method that solves a particular bug. It will help remember you a solution and helps understands somebody
   why you choose your algorithm to solve it. Comment all workaround method that solves problems related to bugs/
   limitation in third-party libraries /frameworks etc.
4. If you need document the actual current behaviour of the system, you can use ADR architecture decision recorder.
5. Inaccurate comments are far worse than no comments at all.
6. A comment may be used to amplify the importance of something.
7. Don't comment bad code, rewrite it.
8. Comments can be useful to explain complicated regex or sql statements


## DEBUGGING:

1. Debugging issues is the skill of diving into only those component parts that might possibly be causing the observed
   undesirable behavior.
2. Spend more time trying to figure things out for yourself before asking for help. Ask for help regards Design or
   Product Discussions . If you’re debugging, then you need to learn how to find your own bugs.

## ERROR HANDLING:

1. Create informative error messages and pass them along with your exceptions. Mention the operation that failed and the
   type of failure. If you are logging in your application, pass along enough information to be able to log the error in
   your catch.
2. Treat try/catch as transactions. Your catch has to leave your program in a consistent state, no matter what happens
   in the try.
3. Silent failures. Some of the hardest bugs to track down have (in part) been caused by code that silently fails and
   continues instead of throwing an error.

## EXCEPTIONS:

1. Use unchecked exception. Yes, checked exception may have some benefits but, it is clear now that they aren’t
   necessary for the production of robust software. The price of checked exceptions is an Open/Closed Principle
   violation.

## INTERFACES:

1. A well-deﬁned interface does not offer very many functions to depend upon, so coupling is low. A poorly deﬁned
   interface provides lots of functions that you must call, so coupling is high.

## NAMES:

1. Naming is very important because 90 percent of what make software readable.
2. The name of a variable, function, or class, should answer all the big questions: why it exists, what it does, and how
   it is used.
3. Name must be descriptive, pronounceable and searchable.
4. Use computer science (CS) terms, algorithm names, pattern names, math terms, and so forth.
5. Describe what an object does without using any conjunctions (“and,” “or”).
6. Don't use similar names for wildly different behaviours.
7. NAME CONVENTION:
    - newXXX a new collection
    - deleteXXX a delete collection
    - getXXX a get collection
    - saveXXX save a collection
    - createXXX create item in collection
    - updateXXX update item in collection
    - readXXX read item in collection
    - addXXX add item to collection
    - removeXXX remove item from collection
    - Verb-noun-where
8. ```_``` international symbol of I don't care. (Interesting fact: ```_``` has at least 7 version of it in Scala.
   As ```_```is not allow anymore do NOT rename it to  ```__```
9. Name vars
    - Choose good variable names. var custList = dbconn.executeQuery(query);
    - Use good initializer information. var outputStream = new ByteArrayOutputStream();
    - Don't worry about "programming to the interface" with vars.
10. Names and meaning can drift apart over time. The vocabulary used by a team evolves. Yesterday’s words may not be
    today’s words. Tidy names one at a time. Make things a little easier for the next reader. You will have time to tidy
    that other name later.

# VARIABLES:

1. Instance variables, should be declared at the top of the class.
2. Variable Declarations. Variables should be declared as close to their usage as possible.
3. Do not store formatted data. Once data is formatted, it is eternally lost and unavailable to computing / data
   processing.
4. Never use Boolean object as return as it is three-valued return value return and it will produce
   NullPointerException.
5. A 'magic number' is a literal value that appears in a program. For example: total = 1.08 * price; 1.08 is a magic
   number because it appears out of the blue, and it's unclear from this line of code what it means. It's generally
   better to replace magic numbers with Named Constants. Simply extract such a number to a constant and give it a
   meaningful intention-revealing name, so that we can all keep understanding our code. Do not create a single constants
   class as it will grow up quickly and it will become being completely unreadable.
6. Values and Objects. It’s important to distinguish between values that model unchanging quantities or measurements and
   objects that have an identity. Values and Objects. values are immutable, so they’re simpler and have no meaningful
   identity; objects have stated, so they have identity and relationships with each other.
    - Values are immutable instances that model ﬁxed quantities. They have no individual identity, so two value
      instances are effectively the same if they have the same state. This means that it makes no sense to compare the
      identity of two values; doing so can cause some subtle bugs—think of the different ways of comparing two copies of
      new Integer(999). That’s why we’re taught to use string1.equals(string2) in Java rather than string1 == string2.
      string1.equals(string2) in Java rather than string1 == string2.
    - Objects, on the other hand, use mutable state to model their behavior over time.
7. Classes representing values should have the same properties as primitive types. Primitive types represent basic
   values like int or char in Java. Primitive types have no identity and are immutable
8. Mutable Object As Key It is a general advice that you should use an immutable object as a key in a Collection.
   HashCode works best when calculated from immutable data. If you use Mutable object as key and change the state of the
   object so that the hashCode changes, then the store object will be in the wrong bucket in the Collection

## GENERAL:

1. Duplication may be the root of all evil in software. Duplication manifests itself in many forms:
    - Lines of code that look exactly alike.
    - Duplication of implementation.
    - Ways to eliminate the duplication is for example to Use the TEMPLATE METHOD removing higher-level duplication.
2. The team should agree to a single set of formatting rules and all members should comply. Why ? It helps to have an
   automated tool that can apply those formatting rules for you.
3. Wrapping third-party APIs is a good practice. When you wrap a third-party API, you minimize your dependencies upon
   it: You can choose to move to a different library in the future without much penalty. Wrapping also makes it easier
   to mock out third-party calls when you are testing your own code.
4. Few things about Null
    - Returning null from methods is bad. Arrays or Collections should never be null. Return Empty Collections Instead
      of Null.
    - Never return null arrays or lists from API methods.
    - Null does not help in finding the error.
    - Null does not allow to distinguish I/O errors from the File instance not being a directory.
    - Never use a Boolean object as return as it is three-valued return value return and it will produce
      nullpointerexception.
5. Software systems should separate the startup process when the application objects are constructed and the
   dependencies are “wired” together. One way to separate construction from use is simply to move all aspects of
   construction to main or module.
6. The majority of the cost of a software project is in long-term maintenance. The clearer the author can make the code,
   the fewer time others will have to spend understanding it.
7. Many inexperienced programmers believe that the primary goal is to get the program working. Once it’s “working,” they
   move on to the next task, leaving the “working” program in whatever state they ﬁnally got it to “work.” Most seasoned
   programmers know that this is professional suicide. The best software usually is written three times: First, you
   write the software to prove to yourself (or a client) that the solution is possible. Others may not recognize that
   this is just a proof-of-concept, but you do. The second time, you make it work. The third time, you make it work
   right.
8. Keeping code clean is relatively easy. If you made a mess in a module in the morning, it is easy to clean it up in
   the afternoon. Better yet, if you made a mess ﬁve minutes ago, it’s very easy to clean it up right now.
9. When you see commented-out code, delete it! Don’t worry, the source code control system still remembers it.
10. Building a project should be a single trivial operation.
11. Dead code (unused statement, method and so on) is code that isn’t executed. Give it a decent burial. Delete it from
    the system. The problem with the dead code is that after awhile it starts to smell. The older it is, the stronger
    the odor becomes. This is because the dead code is not completely updated when designs change. It still compiles,
    but it does not follow newer conventions or rules. It was written at a time when the system was different. When you
    ﬁnd dead code, do the right thing.
12. Use Explanatory Variables. One of the more powerful ways to make a program readable is to break the calculations up
    into intermediate values that are held in variables with meaningful names.
13. Prefer Polymorphism to If/Else or Switch/Case.
14. Ways to improve your coding skills:
    - Pair programming
    - Code review
    - TDD
15. Readability of code is most important because most programmers spend the most time on .. read code not write it.
16. You should use enum types anytime you need to represent a fixed set of constants.
17. Consistent code matters because:
    - The code is quicker and easier to read.
    - It is easier to spot the error.
    - It is more reusable for similar problem solution.
18. Use an iterative design approach. Don’t spend time trying to make code perfect before you've spent time trying to
    make the code work. You’ll never, ever get it right completely in your head. You have to get those fingers banging
    on a keyboard and produce code that runs and does what’s expected. The problem is that developers tend to make one
    of two common mistakes; either they spend too much time thinking and not enough time actually doing, or they don’t
    spend enough time improving their first solution. Follow the mantra first stated by Kent Beck: “make it work, make
    it right, make it fast” — and in that order.
19. (Monitoring) to set up alerts whenever a new NullPointerException (or any other exception) is introduced into the
    system. Check it out. Log check for NullPointerException if too many alerts.
20. Use static factories over constructor to have a better readability
21. Use URI over URL, because equal and hashcode are not well designed as they referring to IP address while URI refers
    to text
22. Keep the code as simple as possible, so it’s easier to understand and modify. Developers spend far more time reading
    code than writing it, so that’s what we should optimize for readability.
23. Defensive Programming is about deciding on the trade-off between robustness (keep running if there is a problem you
    can deal with) and correctness (never return inaccurate results). Protect your code from invalid data coming from
    “outside”. Establish “barricades” – everything outside of the boundary is dangerous, everything inside of the
    boundary is safe. Choose a strategy to deal with bad data: return an error and stop right away (fast fail), return a
    neutral value, substitute data values, … It must be clear and consistent.
24. Keep the code as simple as possible, so it’s easier to understand and modify. Developers spend far more time reading
    code than writing it, so that’s what we should optimize for readability.Write the Test That You’d Want to Read.
25. Package structure dms.pastor.[project].[feature].[subfeature]
26. Deal with legacy code. We should add smoke tests as a build verification step to our deployment pipeline (create one
    if it does not exist). Once smoke tests are in place, we can be confident that we won’t break anything terribly.
27. Hence, we need to make sure the core components behave as expected. Hence, choose a core component and start
    testing. Writing unit tests will automatically refactor the legacy code a little bit.
28. Some boilerplate code exists in Java became they improve readability and allow you to see sneaky bugs (normally
    auto-generated by IDE) and problematic debugging.
29. Don't optimize before you know it is necessary. you need to define how fast your application code has to be by
    specifying a maximum response time for all API calls or the number of records that you want to import within a
    specified time frame.
30. Use a profiler to find the real bottleneck in performance. It gives you a better understanding of the performance
    implications of your code and allows you to focus on the most critical parts.
31. IDE. Write code more quickly with saved snippets and text shortcuts.
32. Fix one thing at time.
33. Wrap checked exception to unchecked exception.
34. Understand the requirements; design the system; AND THEN WRITE THE CODE.
35. A Basic Programming Pattern: Filter First, Map Later. Why? Because an index reduces the algorithmic complexity of a
    query algorithm from O(N) (scanning the entire table for matches) to O(log N) (scanning a B-tree index for the same
    matches).
36. use of generic types as root values has been (... and, will be) a big source of problems, so I recommend users to
    consider avoiding it when possible. As you have found it can be made to work, but there's bit extra code, and can be
    non-obvious to tackle.Workaround include use of helper class that binds type (class AbstractParentList extends
    List<AbstractParent>), to achieve the end result by passing non-generic
    type.https://github.com/FasterXML/jackson-module-kotlin/issues/83
37. Don't use wildcard on return type, because:
    - Wouldn't make the API any more flexible.
    - Would force user to deal with wildcard type explicitly.
    - User should not have to think about wildcards to use your API.
38. Boolean.getBoolean() doesn't do what you think.
39. List<String> IS NOT a subtype of List<Object> (good for compile-time type safety ,but inflexible.
0. The code restorer. Somebody whose job isn't to "recreates the same thing but better" (a common wish that almost
   always fails) but instead takes the existing codebase and slowly reshapes it to make it manageable again. Add some
   tests here, break down that ugly class there, remove unused functionality, and give it back improved.
0. Coding guidelines help us to write consistent code. It should not matter which developer in your team has written the
   code you are looking at. Coding guidelines are only useful if every team member takes them seriously. That's why the
   whole team has to agree on the guidelines once they are finished.
0. As code evolves, locally-optimized programming decisions can leave messes where there is a shorter, clearer
   alternative. Tidy up by fixing these spots one at a time. Replace "if (flag == true)" with "if (flag)" (assuming your
   programming language supports this). Replace “collection.size == 0” with “collection.isEmpty”.
0. Expressions can start simple and then grow. At each step, it is easier to add to the expression than to factor out
   parts. That's where tidying comes in.
0. Tidy expressions by extracting parts and giving the temporary variable a suggestive name. Turn
   this:``return new Point(…long-expression to compute x…, …long-expression to compute y, which is interesting for different reasons than x…) "
   into:``    x := expression to compute x; y := expression to compute y; return new Point(x, y);``
   0.The technique is to build your software to "fail fast." Bugs are easier to find and fix, so fewer go into
   production. Use Assertions to test quickly, write custom assert to add a meaningful message and other useful
   information to debug. If you use a global exception handler, avoid catch-all exception handlers in the rest of your
   application ugs add a lot of expense and risk to our projects—not to mention, they're a pain in the neck to figure
   out.
   
