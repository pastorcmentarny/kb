## **HONEST WARNING**

**Content in this KB is for me ONLY.**
It contains definitions that explain things in a way that is easiest for me to understand.
_I am not the author of these definitions, so check the resources section for the origin of definitions._

* MockitoAnnotations.initMocks(this); initializes fields annotated with Mockito annotations.
* NullPointerException auto-unboxing caveat. In rare cases when matching primitive parameter types you *must* use relevant intThat(), floatThat(), etc. method. This way, you will avoid NullPointerException during auto-unboxing. Due to how java works, we don't really have a clean way of detecting this scenario and protecting the user from this problem.
* Since Mockito any(Class) and anyInt family matches perform a type check, thus they won't match null arguments. Instead, use the isNull matcher.
* Once created, a mock will remember all interactions.
* By default, for all methods that return a value, a mock will return either null, a primitive/primitive wrapper value, or an empty collection, as appropriate. For example, 0 for an int/Integer and false for a boolean/Boolean.
* Stubbing can be overridden: for example, common stubbing can go to fixture setup, but the test methods can override it. Please note that overriding stubbing is a potential code smell that points out too much stubbing
* Once stubbed, the method will always return a stubbed value, regardless of how many times it is called.
* the Last stubbing is more important - when you stubbed the same method with the same arguments many times. In other words: the order of stubbing matters, but it is only meaningful rarely, e.g. when stubbing exactly the same method calls or sometimes when argument matches are used, etc.
* Argument matches Mockito verifies argument values in natural java style: by using an equals() method. Sometimes,   when extra flexibility is required, then you might use argument matches:
  * you can also verify using an argument matcher (they can also be written using Java 8 Lambdas)
  * The natural matching style using equals() with occasional anyX() matches tend to give clean & simple tests. If you are using argument matchers, **all arguments have to be provided by matches**. If any of them is not matcher, then it will throw an exception. verify(mock).someMethod(anyInt(), anyString(), eq("third argument")); if any of them are not using matchers they will   throw exception
* If stuff is hard to test, it usually indicates the design could be better, so do refactor for testability!
* Mockito naturally uses equals() for argument matching. Many times, this is option is clean and simple.
* Verifying an exact number of invocations / at least x / never times(1) is the default. Therefore using times(1) explicitly can be omitted.never() is an alias to times(0)
* Verification in order is flexible - you don't have to verify all interactions one-by-one but only those that you are interested in testing in order. verifyNoMoreInteractions() is not recommended to use in every test method. Use when needed  (It he) overspecified, less maintainable tests.
* recommend simply stubbing with thenReturn() or thenThrow(), which should be enough to test/test-drive any clean & simple code.
* Spying on real objects Real spies should be used carefully and occasionally, for example, when dealing with legacy code.
* Sometimes, it's impossible or impractical to use when(Object) for stubbing spies. Therefore when using spies, please consider doReturn|Answer|Throw() family of stubbing methods.
* Watch out for final methods. Mockito doesn't mock final methods, so the bottom line is: when you spy on real objects + you try to stub a final method = trouble.
* it is recommended to use ArgumentCaptor with verification but not with stubbing.
* In a way ArgumentCaptor is related to custom argument matchers (see Javadoc for ArgumentMatcher class). Both techniques can be used for making sure certain arguments where passed to mocks. However, ArgumentCaptor may be a better fit if:
* custom argument matcher is not likely to be reused. You just need it to assert on argument values to complete verification of the partial mock warning: Object-oriented programming is less tackling complexity by dividing the complexity into separate, specific, SRPy objects. How does partial mock fit into this paradigm? Well, it just doesn't... Partial mock usually means that the complexity has been moved to a different method on the same object. In most cases, this is not the way you want to design your application.
* However, there are rare cases when partial mocks come in handy: dealing with code you cannot change easily (3rd party interfaces, interim refactoring of legacy code etc.) However, I wouldn't use partial mocks for new, test-driven &  well-designed code.
* Smart Mockito users hardly use this feature because they know it could be a sign of poor tests. Instead of reset() please consider writing simple, small and focused test methods over lengthy, over-specified tests.
* First potential code smell is reset() in the middle of the test method. This probably means you're testing too much.
* Don't harm yourself. reset() in the middle of the test method is a code smell (you're probably testing too much).
* Behavior Driven Development style of writing tests uses // given // when // then comments as fundamental parts of your test methods. This is exactly how we write our tests, and we warmly encourage you to do so!
* @Captor simplifies the creation of ArgumentCaptor - useful when the argument to capture is a nasty generic class, and you want to avoid compiler warnings @Spy - you can use it instead spy(Object). @InjectMocks - injects mock or spy fields into the tested object automatically.
* Mockito cannot warn you about mocking final methods,  be vigilant.
* Cannot mock equals(), hashCode(). Firstly, you should not mock those methods. Secondly, Mockito defines and depends upon a specific implementation of these methods. Redefining them might break Mockito. t in most scenarios, a mock returning a mock is wrong.
* Mockito throws exceptions if you misuse it so that you know if your tests are written correctly. The gotcha is that Mockito does the validation **next time** you use the framework
* Sometimes, we need to the stub with different return value/exception for the same method call. /Any consecutive call: prints "foo" as well (the last stubbing wins).
* We recommend simply stubbing with thenReturn() or thenThrow(), which should be enough to test/test-drive any clean & simple code. However, if you do have a need to the stub with the generic Answer interface
* Stubbing void methods requires a different approach from when(Object) because the compiler does not like void methods inside brackets..example doThrow(RuntimeException.class).when(mockedList).clear();
* You can use doThrow(), doAnswer(), doNothing(), doReturn() and doCallRealMethod() in place of the corresponding call with when(), for any method. It is necessary when you
  * stub void methods
  * stub methods on spy objects (see below)
  * stub the same method more than once, to change the behaviour of a mock in the middle of a test.
  * but you may prefer to use these methods in place of the alternative with when(), for all of your stubbing calls.
* Real spies should be used carefully and occasionally, for example, when dealing with legacy code.
* Mockito *does not* delegate calls to the passed real instance; instead, it actually creates a copy of it.
* Watch out for final methods. Mockito doesn't mock final methods, so the bottom line is: when you spy on real objects + you try to stub a final method = trouble. Also, you won't be able to verify those methods as well.  
