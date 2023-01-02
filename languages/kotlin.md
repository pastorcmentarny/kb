 ## **HONEST WARNING**
 **Content in this KB is for me ONLY.**
 It contains definitions that explain things in the way that is easiest for me to understand.
 _I am not the author of these definitions so check resources section for the origin of definitions._ 
 
 

 * Note that boxing of numbers does not necessarily preserve identity. On the other hand, it preserves equality.
 * You cannot assign a value of type Byte to an Int variable without an explicit conversion. Use toInt() and other method for that.
 * Arrays in Kotlin are represented by the Array class, that has get and set functions (that turn into [] by operator overloading conventions), and size property, 
 * If there is a name clash, we can disambiguate by using as keyword to locally rename the clashing entity:   
 ```java
import foo.Bar // Bar is accessible
import bar.Bar as bBar // bBar stands for 'bar.Bar'
```
* val means I can't never re-assing value to value
* String interpolation 
```
val letter
println("Letter : $letter") 
 ```
* public is default modifier in Kotlin
* kotlin uses unchecked exception only
* function Don't need be part of a class
* function can have default parameters. It means if you do not set specific values it will use default.
* no void keyword, we just left blank
* named parameters allow specify parameters in any order via their name
* extension functions allow you to add function to classes not owned by you (They generates statics function.Useful to cuts down on use of utils classes and it is easier to reac)
* classes and methods are final by default in Kotlin
* open keyword means class or method is not final
* sealed class is like enum on steroids
* data classis a object value .It provides all boiler plates stuff for you like: set,get.equals()/hashCode() pair,toString(),copy()
* there is no package-private as packages are used for organise your classes only
* kotlin do not have static methods
* Companion object is an object that is a companion to a particular class, and thus has access to it’s private level methods and properties.  is that they can inherit from other classes or implement interfaces and generally behave like any other singleton.
* function as first class citizens
* higher order function is a function that accept or return other function. * Higher function gives higher flexibility but it can have a performance overhead. Use inline can negate this in some cases.
* you don't need declare one parameter, you can use .. it keyword instead. 
* you cannot assign null by default ( you need indicate it null)
* Strategy Pattern allows an algorithms behaviour to be selected at runtime. In Kotlin we use function to pass (Strategy)
* Unlike Java where lambdas Kotlin lambdas can mutate values (Java 8's cannot)
* !! is not null and cannot be null. it will throw exception at
* 'let' function used to avoid explicit null checks. Useful when passing Nullable values ..
        to functions expecting non-null values
* let is useful when you  cannot change fun that you call         
* Late initialized properties . Use 'lateinit' if you don't want mark value a nullable when declared
* kotlin understand @Nullable @NonNull from javax.annotation , org.jetbrains.annotation, android.support.annotation 
* java erases all generic type information at runtime but Kotlin can reify some generic information. You cannot check generic type at runtime. You can mark inline function that using type as reified.
```kotlin
inline fun <feified T> foo(value: Any) = value is T
```
* for object types, Kotlin uses the null value to mark that a lateinit property has not been initialized and to throw the appropriate exception when the property is accessed. For primitive types, there is no such value, so there is no way to mark a property as non-initialized and to provide the diagnostics that lateinit needs to work around the type safety system.
* override fun sign() = println("I can sign documents") // method expression
* init block runs after object is constructed
* secondary constructors are provided in case if you need more than one constructor  use constructor 
* functional programming is a programming style based on immutability first class function and higher order functions
* higher order function is a functions passed or return from other function
* map A -> B 
. It's important to know, that inline functions with reified types are not callable from Java code, whereas normal inline functions are. That's probably the reason why not every type parameter used in inline functions is reified by default.

* Things get nasty when your Kotlin code has to get along with Java code (libraries are written in Java, so it happens pretty often I guess). Then, the third kind of type jumps in — T!. It’s called platform type, and somehow it means T or T?. 
* NOTE! Declaring an object property as lateinit also makes its backing field public (while keeping all accessors), which may not be what you want for a public API, so pay attention.
 * Builders. Usually, in Kotlin there is no such thing as builders, because we have default and named parameters and apply function
Reify make info a thing, make real

TODO Searled Classes
TODO with and apply
TODI SAM constructor
TODO Using Higher order Functions
TODO
    If they are mutable (i.e. might change at a later stage) use lateInit
    If they are set externally (e.g. need to pass in some external variable to set it), use lateinit. There’s still workaround to use lazy but not as direct.
    If they are only meant to initialized once and shared by all, and it’s more internally set (dependent on variable internal to the class), then use lazy. Tactically, you could still use lateinit, but using lazy would better encapsulate your initialization code.
TODO
     lateinit is super-set of lazy i.e. you could basically use lateinit for the scenario that need to be lazy but not vice-versa. But one should use lazy instead of lateinit when possible… as lateinit exposes more codes logic in the function and messier than lazy, which hides the detail away in it’s own encapsulation, and safer.

sources of information:
1) https://tech.io/playgrounds/7870/kotlin-simplified-generic-methods-with-reified-types
2) 


// we can create nested object inside class

// kotlin do  not have static members
// companion object used for factory objects and static members or use as call main from Java ...

/*// open means can be overridden , abstract musb be overridden, default cannot be overriden
abstract class Person(var firstName: String, var lastName: String) { // open is to negate  final keyword used by default
    open fun getName(): String = "$firstName $lastName"
    abstract fun getAddress(): String

}*/


/*
open class Student(firstName: String, lastName: String, _id: Int, var tutor: String = "") : Person(firstName, lastName) {
    override fun getAddress(): String {
        return ""
    }

    val id: Int

    init {
        id = _id
    }

    fun enrol(courseName: String) {
        val course = Courses.allCourses
                .filter { it.Title == courseName }
                .firstOrNull()
    }

    companion object : XmlSerializer<Student> {
        fun createUndergradute(name: String): Undergarduate {
            return Undergarduate(name)

        }

        fun createPostgard(name: String): Postgarduate {
            return Postgarduate(name)
        }

        override fun toXml(item: Student) {

        }
    }
}

 */
open class Device(name: String) { // primary constructor (better than secondary and you can use default value
    constructor(name: String, serialNumber: Int) : this(name) /// secondary
}

        val text = """
            > It is time to learn Kotlin!
            > It is my first project with Kotlin and Spring Boot 2
            > It should be as useless as all my projects :)
            ${'$'}9.99

            """.trimMargin() //  remove leading whitespace ${'$'}9.99 is used to type $


        for (letter in text) {
            println("Letter : $letter")
        }



looops

        val values = 1..10
        for (i in values step 2) {
            println(i)
        }

        line("Kotlin's for loop style// closed range  (different than java) ")
        for (i in 1..10 step 2) {
            println(i)
        }
        line("Java's for loop style Half-open range")
        for (i in 1 until 10 step 2) {
            println(i)
        }

        line("down to 1 example")

        for (i in 10 downTo 1 step 3) {
            println(i)
        }

        line("for loop for array's indecies ")

        val ints: Array<Int> = arrayOf(1, 4, 9, 16, 25)

        for (i in ints.indices) {
            println(i)
        }

        val intArray = intArrayOf(1, 4, 9, 16, 25)
        intArray.forEachIndexed { index, value -> println("@$index value is $value") }





        line("map loop")

        val ages = TreeMap<String, Int>()
        ages["Kelvin"] = 55
        ages["Sam"] = 24
        ages["Alex"] = 24
        ages["Harry"] = 26

        for ((name, old) in ages) {
            println("$name is $old years old.")
        }


        line("for loop with index")

        val numbers: IntArray = intArrayOf(1, 2, 4, 8, 16, 32)

        for ((index, value) in numbers.withIndex()) {
            println("$value is at index $index")
        }


        line("default parametes")

        private fun isItUsable(useIt: Boolean = true): String {
            return if (useIt) "YES" else "no"
        }

        println(isItUsable())
        println(isItUsable(false))
        println(isItUsable(true))





return null
    private fun returnNull(): String? {
        return null
    }

