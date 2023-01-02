## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._


1.  Test code is just as important as production code. It is not a second-class citizen. It requires thought, design, and care. It must be kept as clean as production code. What makes a clean test? Three things. readability, readability, and readability. Readability is perhaps even more important in unit tests than it is in production code. What makes tests readable? Clarity, simplicity, and density of expression. If you don’t keep your tests clean, you will lose the very thing that keeps your production code ﬂexible. It is unit tests that keep our code ﬂexible, maintainable, and reusable. The reason is simple. If you have tests, you do not fear to make changes to the code. True unit tests run extremely quickly without any runtime infrastructure to set up.It will boost your productivity.
2.  Rules for clean tests based on FIRST rules: (FIRST is acronym for Fast, Independent, Repeatable, Self-validating, Timely)
    -   FAST Tests should be fast.
    -   INDEPENDENT TESTS should not depend on each other.
    -   REPEATABLE Tests should be repeatable in any environment. It should run on production, QA and developer's machine.
    -   SELF-VALIDATING. The tests should have a boolean output. Either they pass or fail.
    -   TIMELY. The tests need to be written in a timely fashion. Unit tests should be written just before the production code that makes them pass.
3.  It is a good practice to start testing with a try-catch-finally statement when you are writing code that could throw exceptions. This helps you define what the user of that code should expect, no matter what goes wrong with the code that is executed in the try block.
4.  When you learn third-party APIs is a good to writes to understand how they work. These tests will come handy when you third-party APIs is updated so then you can run your tests to see is they break anything.. (Jim Newkirk calls such tests Learning tests. )
5.  Having dirty tests is as bad (if not worse) than having no tests. Dirty test means that it doesn't need to follow quality standards and name convention.
6.  Well-written unit tests are also expressive. A primary goal of tests is to act as documentation for example.
7.  Refactoring is an iterative process full of trial and error, inevitably converging on something that we feel is worthy of a professional.
8.  Test boundary condition.
9.  Exhaustively test near bugs. Bugs tend to congregate. When you find a bug in a function, it is wise to do an exhaustive test of that function. You’ll probably ﬁnd that the bug was not alone.
10. Automate the normal case: You don't have to automate every situation; just automate the known, normal situations. If anything is abnormal, make the automation stop and let humans step in. 
11. The pre-live environment is very important part of testing.
12. Putting assertion in test teardown method.
13. Performance testing is a technique to determine how a system performs in terms of responsiveness and stability under a particular workload. Type of tests: Load testing, stress testing, soak testing (It helps memory leaks and other 'time bomb issues').
14. Tests should be idempotent. The same input produces the same output. For the particular set of inputs that are then compared to an expected output. When the expected output does not match the actual output, the test fails. If tests fail.
15. When you work on support task, the very first thing to do is write a unit test to recreate the bug.
16. In test is worth to give a meaningful name for a constant that is deﬁned as null as it helps readability. For example UNUSED_MODEL.
17. Automate things is better because Manual things slow things down and increase the chance of error.
18. Tests with random data should be logged. We had no way of tracking the differences between various runs of the same test because the test code being run was exactly the same. 
19. We start work on a new feature by writing failing acceptance tests that demonstrate that the system does not yet have the feature we’re about to write and track our progress towards completion of the feature.
20. We write the acceptance test using only terminology from the application’s domain.It helps to understand what the system should do, without tying us to any of our initial assumptions about the implementation or underlying technologies. 
21. Where do we start when we have to write a new class or feature? The simplest thing that could possibly work but simple should not be interpreted as simplistic. We prefer to start by testing the simplest success case. Once that’s working, we’ll have a better idea of the real structure of the solution and can prioritize between handling any possible failures we noticed along the way and further success cases.
22. A test called testBidAccepted() tells us what it does, but not what it’s for. 
23. The point of a test is not to pass but to fail. We want the production code to pass its tests, but we also want the tests to detect and report any errors that do exist. A “failing” test has actually succeeded at the job it was designed to do.
24. Make sure you have tests before you refactor. Important when you dealing with legacy code.
25. A great QA engineer is able to provide exact reasons to the developer, rather than simply saying a test case “failed”.
26. An integration test suite will typically take much longer to run (sometimes hours) than a unit test suite which should take no more than 5-10 minutes. Integration tests are also typically more subject to volatility. While the integration test I wrote in this article should be stable if it breaks, it should be cause for concern. When connecting to a development database, you can’t always be 100% confident the database will be available or that your test data will be correct or even present. So a failed integration test doesn’t necessarily mean the code is incorrect.
27. Questions to ask yourself when writing tests:
    -   I've tested a number of cases manually. Are these cases covered by tests? If no, write tests covering these cases.	
    -   Are the boundaries of the code under test, themselves tested? Each boundary introduces an assumption, which introduces risk since it might be false. Consider higher level tests that each test more of the code. 
29. Are boundaries of the problem domain tested? The most common of these are off-by-one errors, so often good to check each side of a numerical boundary. Yes, some code will be re-tested, but the increase of confidence is worth the cost.
29. Bottleneck is where system oversubscribe to resource.
30. JMeter is great for model user behaviour /stories . Gatling is great system testing.
31. I don’t think there is any value in spending time wrapping the whole of a legacy system in unit  Tests as this can be very costly in developer’s time let along financially expensive. When you do need to change/modify older code though, it is worth trying to write characterization tests that document the behaviour of the code you are trying to modify. 
32. Stimulus and response have to go together in order for an association to be made. If Pavlov rang the bell then fed his dogs an hour later they'd never make the connection. That's why we don't make the connection between the bugs we write when they're found, weeks later, by QA.
33. Run stability tests. Close to average load should be produced against the system for at least 12 hours. This is the real test of how the GC behaves.
0.  Don't let your tests micromanage your code. 
0.  Dan North says, “The goal of testing is to increase the confidence for stakeholders through evidence”. Evidence can be provided by our tests. Increasing doesn’t necessarily mean to reach the 100% of piramid test. 
0. A test is not a unit test if:   
   0. communicates to the database
   0. communicates via the network
   0. deal with the file system
   0. depends on any of your other unit tests
0.  It is not about piramind is about right amount of tests foe specific scenario
    *   Critical code - This is the code that breaks often, gets most of new features and has a big impact on application users
    *   Core code - This is the code that breaks sometimes, gets few new features and has medium impact on the application users
    *   Other code - This is code that rarely changes, rarely gets new features and has minimal impact on application users.
0.  Try to write tests that work towards 100% coverage of critical code. If you have already done this, then try to write tests that work towards 100% of core code. Trying however to get 100% coverage on total code is not recommended. In summary, write unit and integration tests for code that
    *   breaks often
    *   changes often
    *   is critical to the business
0.  Converting production bugs to test
0.  Encode every single bug you find as a test, to ensure that you’ll notice if you ever encounter it again.
0.  If youb join to legacy project for pay attention to the existing bugs and try to cover them with tests. After a while your tests will have covered the critical part of the code, since by definition all tests have verified things that break often. 
0.  Automate input validation tests, as well as verification authentication and authorization features.
0. Testing types:
   0. Unit Testing - verifies that each application function (module) returns the correct value for a given input
   0. Component/Integration Testing - n the application containe
   0. UI Testing
   0. Performance Testing
   0. Soak Testing to find memory leakis
   0. Security Testing

0. It is not about piramind is about right amount of tests foe specific scenario
 * Critical code - This is the code that breaks often, gets most of new features and has a big impact on application users
 * Core code - This is the code that breaks sometimes, gets few new features and has medium impact on the application users
 * Other code - This is code that rarely changes, rarely gets new features and has minimal impact on application users.



Almost no unit tests because there is no business logic

Lots and lots of integration tests for the external communications, the db storage, the invoice system

No UI Tests because there is a no UI

here for example is a lot integration test


Try to write tests that work towards 100% coverage of critical code. If you have already done this, then try to write tests that work towards 100% of core code. Trying however to get 100% coverage on total code is not recommended.

In summary, write unit and integration tests for code that

breaks often

changes often

is critical to the business

if you find yourself routinely changing existing tests just to make them pass when a new feature is added then your tests are not testing what they should be testing.

converting production bugs to test


if youbjoin to legacy project for pay attention to the existing bugs and try to cover them with tests. After a while your tests will have covered the critical part of the code, since by definition all tests have verified things that break often. 

add this link TO KBhttp://blog.codepipes.com/testing/software-testing-antipatterns.html

Automate input validation tests, as well as verification authentication and authorization features.
. Encode every single bug you find as a test, to ensure that you’ll notice if you ever encounter it again.

