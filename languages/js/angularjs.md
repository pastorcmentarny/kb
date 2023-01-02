## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 


# AngularJS

## Definitions
AngularJS extends HTML with ng-directives.

The **ng-app** directive defines an AngularJS application.

The **ng-model** directive binds the value of HTML controls (input, select, textarea) to application data.

The **ng-bind** directive binds application data to the HTML view.

AngularJS **directives** are HTML attributes with an data-ng prefix. 

AngularJS expressions bind AngularJS data to HTML the same way as the ng-bind directive.

AngularJS **modules** *define* AngularJS applications.

AngularJS **controllers** *control* AngularJS applications.

The **ng-app directive** defines the application, the **ng-controller directive** defines the controller.

AngularJS expressions can be written inside double braces: {{ expression }} and can be written inside a directive: ng-bind="expression".

AngularJS expressions are much like JavaScript expressions: They can contain literals, operators, and variables.

AngularJS Expressions vs. JavaScript Expressions
* Like JavaScript expressions, AngularJS expressions can contain literals, operators, and variables.
* Unlike JavaScript expressions, AngularJS expressions can be written inside HTML.
* AngularJS expressions do not support conditionals, loops, and exceptions, while JavaScript expressions do.
* AngularJS expressions support filters, while JavaScript expressions do not.

AngularJS has a set of built-in directives which you can use to add functionality to your application.

## APPLICATION
The AngularJS application is defined by  ng-app="myApp". The application runs inside the <div>.

## MODULE

The module is a container for the different parts of an application.
The module is a container for the application controllers.
_Controllers always belong to a module._

```javascript
var app = angular.module("myApp", []);  

```
The [] parameter in the module definition can be used to define dependent modules. Without the [] parameter, you are not creating a new module, but retrieving an existing one.

Global functions should be avoided in JavaScript. They can easily be overwritten or destroyed by other scripts.

AngularJS modules reduces this problem, by keeping all functions local to the module.

AngularJS lets you extend HTML with new attributes called Directives.

AngularJS has a set of built-in directives which offers functionality to your applications and you define your own directives.

The ```{{ firstName }}``` expression, in the example above, is an AngularJS data binding expression. 

Data binding in AngularJS binds AngularJS expressions with AngularJS data.

```{{ firstName }}``` is bound with ```ng-model="firstName".```

The **ng-repeat** directive actually clones HTML elements once for each item in a collection.

The **ng-repeat** directive used on an array of objects:

The **ng-app directive** defines the  ***root element*** of an AngularJS application.

The **ng-app directive** will ***auto-bootstrap*** (automatically initialize) the application when a web page is loaded.

The **ng-model** directive can also:

* Provide type validation for application data (number, email, required).
* Provide status for application data (invalid, dirty, touched, error).
* Provide CSS classes for HTML elements.
* Bind HTML elements to HTML forms.


##DIRECTIVES

In addition to all the built-in AngularJS directives, you can create your own directives.

New directives are created by using the .directive function.

When naming a directive, you must use a camel case name, w3TestDirective, but when invoking it, you must use - separated name, w3-test-directive:

You can invoke a directive by using:
```javascript
    app.directive("domFooter",function () {    
        var year = new Date().getFullYear();       
        return{       
            template : "<h3>Created and crafted by Dominik. &Omega;" + year + "</h3>"            
        };
    }
```

* Element name ```<dom-footer></dom-footer>```
* Attribute ```<div dom-footer></div>```
* Class ```<div class="dom-footer"></div>```
* Comment ```<!-- directive: dom-footer -->```

You can restrict your directives to only be invoked by some of the methods:
```javascript
    app.directive("domFooter",function () {    
    
        var year = new Date().getFullYear();
        
        return{
            restrict: "A",
            template : "<h3>Created and crafted by Dominik. &Omega;" + year + "</h3>"
            
        };
    }
```

The legal restrict values are:

* **E** for **Element name**
* **A** for **Attribute**
* **C** for **Class**
* **M** for **Comment**
(By default the value is EA)
 
 
## Two-Way Binding

The binding goes both ways. If the user changes the value inside the input field, the AngularJS property will also change its value:
 
If the property in the ng-model attribute does not exist, AngularJS will create one for you.
 
**ng-empty** : _the view not contains any value_
**ng-not-empty** : _the view contains a non-empty value_
**ng-touched** : the control has been blurred **???**
**ng-untouched** : ? **???**
**ng-valid** : _the model is valid_
**ng-invalid** : _the model is invalid_
**ng-dirty** : _class tells you that the form has been modified by the user_
**ng-pending** :  any $asyncValidators are unfulfilled **???**
**ng-pristine** : _class tells you that the form has not been modified by the user_
**ng-valid-[key]** : for each valid key added by $setValidity

9from: https://docs.angularjs.org/api/ng/directive/ngModel
 
 
Data binding in AngularJS is the synchronization between the model and the view.
 
The HTML container where the AngularJS application is displayed, is called the view.

You can use the ng-bind directive, which will bind the innerHTML of the element to the specified model property: ```<p ng-bind="description"></p>```or ```{{description}}``` or you can use the ng-model directive on HTML controls to bind the model to the view.

When data in the model changes, the view reflects the change, and when data in the view changes, the model is updated as well.
This happens immediately and automatically, which makes sure that the model and the view is updated at all times.
 
##Controller

AngularJS controllers control the data of AngularJS applications.
AngularJS controllers is a JavaScript Object, created by a standard JavaScript object constructor.
 
 
 
 The ng-controller="myCtrl" attribute is an AngularJS directive. It defines a controller.
 
 In AngularJS, $scope is the application object (the owner of application variables and functions).
 
 The scope is the binding part between the HTML (view) and the JavaScript (controller).
 
 The scope is an object with the available properties and methods.
 
 The scope is available for both the view and the controller.
 When you make a controller in AngularJS, you pass the $scope 
 
 When adding properties to the $scope object in the controller, the view (HTML) gets access to these properties.
 
 In the view, you do not use the prefix $scope, you just refer to a propertyname, like {{carname}}.
 
 
 the Scope
 If we consider an AngularJS application to consist of:
 
 View, which is the HTML.
 Model, which is the data available for the current view.
 Controller, which is the JavaScript function that makes/changes/removes/controls the data.
 Then the scope is the Model.
 
 The scope is a JavaScript object with properties and methods, which are available for both the view and the controller.
 
 All applications have a $rootScope which is the scope created on the HTML element that contains the ng-app directive.
 
 The rootScope is available in the entire application.
 
 If a variable has the same name in both the current scope and in the rootScope, the application use the one in the current scope.
 
 $rootScope is available globally, no matter what controller you are in, whereas $scope is only available to the current controller and it's children.
 
 The main difference is the availability of the property assigned with the object. A property assigned with $scope cannot be used outside the controller in which it is defined whereas the a property assigned with $rootScope can be used anywhere.
 
 f a variable has the same name in both the current scope and in the rootScope, the application use the one in the current scope.
 
 ##Filters
 Filters can be added in AngularJS to format data.
 
 AngularJS provides filters to transform data:
 
 * *currency* **Format a number to a currency format.**
 * *date* **Format a date to a specified format.**
 * *filter* **Select a subset of items from an array.**
 * *json* **Format an object to a JSON string.**
 * *limitTo* **Limits an array/string, into a specified number of elements/characters.**
 * *lowercase* **Format a string to lower case.**
 * *number* **Format a number to a string.**
 * *orderBy* **Orders an array by an expression.**
 * uppercase* **Format a string to upper case.**
 
 Filters are added to directives, like ng-repeat, by using the pipe character |, followed by a filter:
 
 The filter filter selects a subset of an array.
 
 The filter filter can only be used on arrays, and it returns an array containing only the matching items.
 
 AngularJS can validate input data.
 
AngularJS offers client-side form validation.

AngularJS monitors the state of the form and input fields (input, textarea, select), and lets you notify the user about the current state.

AngularJS also holds information about whether they have been touched, or modified, or not.

You can use standard HTML5 attributes to validate input, or you can make your own validation functions.

Form State and Input State
AngularJS is constantly updating the state of both the form and the input fields.

## ngROUTES
The ngRoute module helps your application to become a Single Page Application.

Add styles for these classes to give your application a better and more intuitive user interface.


Remember, when naming a directive, you must use a camel case name, myDirective, but when invoking it, you must use - separated name, my-directive.

The ngRoute module helps your application to become a Single Page Application.


####What is Routing in AngularJS?
If you want to navigate to different pages in your application, but you also wants the application to be a SPA (Single Page Application), with no page reloading, you can use the ngRoute module.

More about it can be found here: 
http://www.w3schools.com/angular/angular_routing.asp

Example of routing :

```javascript

    app.config(function($routeProvider) {
        $routeProvider
        .when("/", {
            templateUrl : "main.htm"
        })
        .when("/red", {
            templateUrl : "red.htm"
        })
        .when("/green", {
            templateUrl : "green.htm"
        })
        .when("/blue", {
            templateUrl : "blue.htm"
        });
    
```
AngularJS AngularJS AngularJS AngularJS AngularJS AngularJS AngularJS AngularJS AngularJS
# AngularJS

## Definitions
AngularJS extends HTML with ng-directives.

    The **ng-app** directive defines an AngularJS application.

    The **ng-model** directive binds the value of HTML controls (input, select, textarea) to application data.

    The **ng-bind** directive binds application data to the HTML view.

    AngularJS **directives** are HTML attributes with an data-ng prefix.

    AngularJS expressions bind AngularJS data to HTML the same way as the ng-bind directive.

    AngularJS **modules** *define* AngularJS applications.

    AngularJS **controllers** *control* AngularJS applications.

    The **ng-app directive** defines the application, the **ng-controller directive** defines the controller.

    AngularJS expressions can be written inside double braces: {{ expression }} and can be written inside a directive: ng-bind="expression".

    AngularJS expressions are much like JavaScript expressions: They can contain literals, operators, and variables.

    AngularJS Expressions vs. JavaScript Expressions
* Like JavaScript expressions, AngularJS expressions can contain literals, operators, and variables.
* Unlike JavaScript expressions, AngularJS expressions can be written inside HTML.
* AngularJS expressions do not support conditionals, loops, and exceptions, while JavaScript expressions do.
* AngularJS expressions support filters, while JavaScript expressions do not.

    AngularJS has a set of built-in directives which you can use to add functionality to your application.

## APPLICATION
The AngularJS application is defined by  ng-app="myApp". The application runs inside the <div>.

## MODULE

The module is a container for the different parts of an application.
    The module is a container for the application controllers.
    _Controllers always belong to a module._

    ```javascript
var app = angular.module("myApp", []);  

```
The [] parameter in the module definition can be used to define dependent modules. Without the [] parameter, you are not creating a new module, but retrieving an existing one.

    Global functions should be avoided in JavaScript. They can easily be overwritten or destroyed by other scripts.

    AngularJS modules reduces this problem, by keeping all functions local to the module.

    AngularJS lets you extend HTML with new attributes called Directives.

    AngularJS has a set of built-in directives which offers functionality to your applications and you define your own directives.

    The ```{{ firstName }}``` expression, in the example above, is an AngularJS data binding expression.

    Data binding in AngularJS binds AngularJS expressions with AngularJS data.

    ```{{ firstName }}``` is bound with ```ng-model="firstName".```

    The **ng-repeat** directive actually clones HTML elements once for each item in a collection.

    The **ng-repeat** directive used on an array of objects:

    The **ng-app directive** defines the  ***root element*** of an AngularJS application.

    The **ng-app directive** will ***auto-bootstrap*** (automatically initialize) the application when a web page is loaded.

    The **ng-model** directive can also:

    * Provide type validation for application data (number, email, required).
* Provide status for application data (invalid, dirty, touched, error).
* Provide CSS classes for HTML elements.
* Bind HTML elements to HTML forms.


##DIRECTIVES

In addition to all the built-in AngularJS directives, you can create your own directives.

    New directives are created by using the .directive function.

When naming a directive, you must use a camel case name, w3TestDirective, but when invoking it, you must use - separated name, w3-test-directive:

You can invoke a directive by using:
    ```javascript
    app.directive("domFooter",function () {    
        var year = new Date().getFullYear();       
        return{       
            template : "<h3>Created and crafted by Dominik. &Omega;" + year + "</h3>"            
        };
    }
```

    * Element name ```<dom-footer></dom-footer>```
* Attribute ```<div dom-footer></div>```
* Class ```<div class="dom-footer"></div>```
* Comment ```<!-- directive: dom-footer -->```

You can restrict your directives to only be invoked by some of the methods:
    ```javascript
    app.directive("domFooter",function () {    
    
        var year = new Date().getFullYear();
        
        return{
            restrict: "A",
            template : "<h3>Created and crafted by Dominik. &Omega;" + year + "</h3>"
            
        };
    }
```

The legal restrict values are:

    * **E** for **Element name**
* **A** for **Attribute**
* **C** for **Class**
* **M** for **Comment**
(By default the value is EA)


## Two-Way Binding

The binding goes both ways. If the user changes the value inside the input field, the AngularJS property will also change its value:

    If the property in the ng-model attribute does not exist, AngularJS will create one for you.

                                                                                            **ng-empty** : _the view not contains any value_
**ng-not-empty** : _the view contains a non-empty value_
**ng-touched** : the control has been blurred **???**
**ng-untouched** : ? **???**
**ng-valid** : _the model is valid_
**ng-invalid** : _the model is invalid_
**ng-dirty** : _class tells you that the form has been modified by the user_
**ng-pending** :  any $asyncValidators are unfulfilled **???**
**ng-pristine** : _class tells you that the form has not been modified by the user_
**ng-valid-[key]** : for each valid key added by $setValidity

9from: https://docs.angularjs.org/api/ng/directive/ngModel


    Data binding in AngularJS is the synchronization between the model and the view.

    The HTML container where the AngularJS application is displayed, is called the view.

    You can use the ng-bind directive, which will bind the innerHTML of the element to the specified model property: ```<p ng-bind="description"></p>```or ```{{description}}``` or you can use the ng-model directive on HTML controls to bind the model to the view.

    When data in the model changes, the view reflects the change, and when data in the view changes, the model is updated as well.
    This happens immediately and automatically, which makes sure that the model and the view is updated at all times.

##Controller

AngularJS controllers control the data of AngularJS applications.
    AngularJS controllers is a JavaScript Object, created by a standard JavaScript object constructor.



    The ng-controller="myCtrl" attribute is an AngularJS directive. It defines a controller.

    In AngularJS, $scope is the application object (the owner of application variables and functions).

The scope is the binding part between the HTML (view) and the JavaScript (controller).

    The scope is an object with the available properties and methods.

    The scope is available for both the view and the controller.
    When you make a controller in AngularJS, you pass the $scope

When adding properties to the $scope object in the controller, the view (HTML) gets access to these properties.

    In the view, you do not use the prefix $scope, you just refer to a propertyname, like {{carname}}.


the Scope
If we consider an AngularJS application to consist of:

    View, which is the HTML.
    Model, which is the data available for the current view.
    Controller, which is the JavaScript function that makes/changes/removes/controls the data.
    Then the scope is the Model.

    The scope is a JavaScript object with properties and methods, which are available for both the view and the controller.

    All applications have a $rootScope which is the scope created on the HTML element that contains the ng-app directive.

    The rootScope is available in the entire application.

    If a variable has the same name in both the current scope and in the rootScope, the application use the one in the current scope.

    $rootScope is available globally, no matter what controller you are in, whereas $scope is only available to the current controller and it's children.

The main difference is the availability of the property assigned with the object. A property assigned with $scope cannot be used outside the controller in which it is defined whereas the a property assigned with $rootScope can be used anywhere.

    f a variable has the same name in both the current scope and in the rootScope, the application use the one in the current scope.

##Filters
Filters can be added in AngularJS to format data.

    AngularJS provides filters to transform data:

    * *currency* **Format a number to a currency format.**
* *date* **Format a date to a specified format.**
* *filter* **Select a subset of items from an array.**
* *json* **Format an object to a JSON string.**
* *limitTo* **Limits an array/string, into a specified number of elements/characters.**
* *lowercase* **Format a string to lower case.**
* *number* **Format a number to a string.**
* *orderBy* **Orders an array by an expression.**
* uppercase* **Format a string to upper case.**

Filters are added to directives, like ng-repeat, by using the pipe character |, followed by a filter:

    The filter filter selects a subset of an array.

    The filter filter can only be used on arrays, and it returns an array containing only the matching items.

    AngularJS can validate input data.

    AngularJS offers client-side form validation.

    AngularJS monitors the state of the form and input fields (input, textarea, select), and lets you notify the user about the current state.

    AngularJS also holds information about whether they have been touched, or modified, or not.

    You can use standard HTML5 attributes to validate input, or you can make your own validation functions.

    Form State and Input State
AngularJS is constantly updating the state of both the form and the input fields.

## ngROUTES
The ngRoute module helps your application to become a Single Page Application.

    Add styles for these classes to give your application a better and more intuitive user interface.


    Remember, when naming a directive, you must use a camel case name, myDirective, but when invoking it, you must use - separated name, my-directive.

    The ngRoute module helps your application to become a Single Page Application.


####What is Routing in AngularJS?
    If you want to navigate to different pages in your application, but you also wants the application to be a SPA (Single Page Application), with no page reloading, you can use the ngRoute module.

    More about it can be found here:
    http://www.w3schools.com/angular/angular_routing.asp

        Example of routing :

    ```javascript

    app.config(function($routeProvider) {
        $routeProvider
        .when("/", {
            templateUrl : "main.htm"
        })
        .when("/red", {
            templateUrl : "red.htm"
        })
        .when("/green", {
            templateUrl : "green.htm"
        })
        .when("/blue", {
            templateUrl : "blue.htm"
        });
    
```







DDD DDD DDD DDD DDD
##DDD** known as Domain-Driven Design

**Domain-Driven Design** is one of the most boring thing I read in my IT carrier since DB lectures at university.

**Domain-Driven Design** is all about design and creating highly expressive models.

    DDD also aims to create models that are understandable by everyone involved in the software development, not just software developers.

    Typically, a model of a domain can be depicted as a UML sketch, as code, and in the language of the domain.

    In DDD, it is less about the nouns and verbs and more about the concepts.

    Remember that the language is used to build a representation of the model of the domain. So is the code. When the code is refactored with new terminology then refactor your language to incorporate the new term.

    Strategic design is about design in the large, and helps focus on the many parts that make up the large model, and how these parts relate to each other.

#### Bounded Contexts

For each model, deliberately and explicitly define the context in which it exists. it is important thateveryone understands the boundary conditions of the context..

    Contexts can be created from (but not limited to) the following:
    * how teams are organized
* the structure and layout of the code base
* usage within a specific part of the domain

Aim for consistency and unity inside the context and don't be distracted by how the model is used outside the context.
Other contexts will have different models, concepts and/or use different dialect

#### Context mapping

Context mapping is a design process where the contact points and translations between bounded contexts are explicitly mapped out. Focus on mapping the existing landscape, and deal with the actual transformations later.

###### *TIP*
&nbsp;&nbsp;&nbsp;&nbsp; *Use continuous integration within a single bounded context to smoothen splinters that arise from different understanding. Frequent code merges, automated tests and applying the ubiquitous language will highlight fragmentation inside the bounded context quickly.*

Within the bounded contexts, effort is focused on building really expressive models; models that reveal the intention more than the implementation.

    Structure

**Entities** are classes where the instances are globally identifiable and keep the same identity for life.

                                                                                                      **Value objects** are lightweight, immutable objects that have no identity. Value objects are a good place to put complex calculations, offloading heavy computational logic from entities.Value Objects have simple life cycles and can greatly simplify your model.

**Cardinality of Associations** The greater the cardinality of associations between classes, the more complex the structure. Aim for lower cardinality by adding qualifiers.Bi-directional associations also add complexity. Critically ask questions of the model to determine if it is absolutely essential to be able to navigate in both directions between two objects.

**Services**

###### **`_(??? - START)_`**
Sometimes it is impossible to allocate behavior to any single class, be it an entity or value object. These are cases of pure functionality that act on multiple classes without one single class taking responsibility for the behavior. In such cases, a stateless class, called a service class, is introduced to encapsulate this behavior.
###### **`_(??? - END)_`**


#### Application Architecture

Each layer is aware of only those layers below it. As such, a layer at a lower level cannot make a call (i.e. send a message) to a layer above it.

**User Interface** *Responsible for constructing the user interface and managing the interaction with the domain model. Typical implementation pattern is model-view-controller.*

**Application**	*Thin layer that allows the view to collaborate with the domain.*

**Domain** *An extremely behavior-rich and expressive model of the domain. Note that repositories and factories are part of the domain. However, the object-relational mapper to which the repositories might delegate are part of the infrastructure, below this layer.*

**Infrastructure** *Deals with technology specific decisions and focuses more on implementations and less on intentions. Note that domain instances can be created in this layer, but, typically, it is the repository that interacts with this layer, to obtain references to these objects.*



**Sources**:
- https://dzone.com/refcardz/getting-started-domain-driven
-



    DESIGN PATTERNS


Null Object
Instead of putting if check for a null value, Null Object reflects a do nothing relationship. Such Null object can also be used to provide default behaviour in case data is not available.
    The intent of a Null Object is to encapsulate the absence of an object by providing a substitutable alternative that offers suitable default do nothing behavior.
    The key to the Null Object pattern is an abstract class that defines the interface for all objects of this type.


    JAVA

**Finally** is _not executed_ if the** System.exit** method is called _inside_ a try block.

**Single Responsibility Principle**

*"One class should have one and only one responsibility"*

write, change and maintain a class for only one purpose.

    It is good because it helps Organize the code,
    low coupling, code changes,



    Source:
https://dzone.com/articles/single-responsibility


    JAVA8 JAVA8  JAVA8  JAVA8 JAVA8


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


    Sources:
https://www.javacodegeeks.com/2014/05/java-8-features-tutorial.html
    https://docs.oracle.com/javase/tutorial/java/javaOO/lambdaexpressions.html



        #### **Functional Interface**

**Definition:**
A functional interface has exactly one abstract method. Since default methods have an implementation, they are not abstract. If an interface declares an abstract method overriding one of the public methods of java.lang.Object, that also does not count toward the interface's abstract method count since any implementation of the interface will have an implementation from java.lang.Object or elsewhere.
An instances of functional interfaces can be created with lambda expressions, method references, or constructor references.
**Docs:** https://docs.oracle.com/javase/8/docs/api/java/lang/FunctionalInterface.html

    Add @FunctionalInterface to Your Functional Interface


#### **Method References**


#### Optionals

Please don't use it as the field of a Java-Bean.




Sources:
    * http://blog.joda.org/2014/11/optional-in-java-se-8.html



    MONGO  MONGO

x###Collection
It is a group of MongoDB documents.
    Collections do not enforce a schema.

###Database
It is a physical container for collections.

    ###Document
A document is a set of key-value pairs.  Documents have dynamic schema. Dynamic schema means that documents in the same collection do not need to have the same set of fields or structure, and common fields in a collection's documents may hold different types of data.


## How RDBMS things are called in MongoDB

RDBMS	 	    MongoDB
Database	    Database
Table		    Collection
Tuple/Row	    Document
column		    Field
Table Join	    Embedded Documents
Primary Key	    Primary Key (Default key _id provided by mongodb itself)


## USEFUL COMMANDS

### db.COLLECTION.drop()
delete collection COLLECTION
Example:
    ```
> show collections
car
plane
> db.car.drop()
true
> db.car.drop()
false
> show collections
plane
```

### db.createCollection("COLLECTION")
create collection with name COLLECTION
for example : db.createCollection("plane")
*   MongoDB creates collection automatically, when you insert some document.
*   normally you will create this collection when you need specify some options for example for capped collection db.createCollection("plane",{"capped":true,"max":5,size:25000})

Example:
    ```
    > db.createCollection("plane",{"capped":true,"max":5,size:25000})
    { "ok" : 1 }
    > db.plane.insert({"name":"Boing 737"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.insert({"name":"Boing 747"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.insert({"name":"Boing 767"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.insert({"name":"Boing 777"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.insert({"name":"Boing 787"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.insert({"name":"Boing 7X7"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.find()
    { "_id" : ObjectId("57f79f9f9505f0047ef35a68"), "name" : "Boing 747" } <- cap was set to 5 so Boing 737 was deleted
    { "_id" : ObjectId("57f79fa29505f0047ef35a69"), "name" : "Boing 767" }
    { "_id" : ObjectId("57f79fa69505f0047ef35a6a"), "name" : "Boing 777" }
    { "_id" : ObjectId("57f79fb49505f0047ef35a6b"), "name" : "Boing 787" }
    { "_id" : ObjectId("57f79fba9505f0047ef35a6c"), "name" : "Boing 7X7" } 
    > db.plane.insert({"name":"Boing 7Y7"})
    WriteResult({ "nInserted" : 1 })
    > db.plane.find()
    { "_id" : ObjectId("57f79fa29505f0047ef35a69"), "name" : "Boing 767" } <= i added 7Y7 so Boing 747 was deleted
    { "_id" : ObjectId("57f79fa69505f0047ef35a6a"), "name" : "Boing 777" }
    { "_id" : ObjectId("57f79fb49505f0047ef35a6b"), "name" : "Boing 787" }
    { "_id" : ObjectId("57f79fba9505f0047ef35a6c"), "name" : "Boing 7X7" }
    { "_id" : ObjectId("57f79fc89505f0047ef35a6d"), "name" : "Boing 7Y7" }
```
### db.dropDatabase()
delete current database

### db.COLLECTION.find().pretty()
find all documents in collection NAME_OF_COLLECTION and display response as intended json

    ```
(data setup)
> db.plane.insert({"name":"SS Galaxy" , "speed": 250, "range": 1700})
WriteResult({ "nInserted" : 1 })
> db.plane.insert({"name":"SS Defiant" , "speed": 400, "range": 1220})
WriteResult({ "nInserted" : 1 })
> db.plane.insert({"name":"SS Voyager" , "speed": 205, "range": 2222})
WriteResult({ "nInserted" : 1 })
> db.plane.insert({"name":"SS Consitution" , "speed": 170, "range": 1150})
WriteResult({ "nInserted" : 1 })
> db.plane.insert({"name":"SS Ambassador" , "speed": 220, "range": 2222})
WriteResult({ "nInserted" : 1 })
> db.plane.insert({"name":"SS Akira" , "speed": 500, "range": 3200})
WriteResult({ "nInserted" : 1 })
(end of data setup)
```
#### Find (match exactly) db.plane.find({keyA:valueA, (...) ,keyZ:valueZ}).pretty()
    ```
> db.plane.find({"speed":500}).pretty()
{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
```

#### Find (greater than) > db.plane.find({key : {**$gt**:value}}).pretty()
    ```
> db.plane.find({"speed" : {**$gt**:205}}).pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
```
#### Find (greater than or equal) > db.plane.find({key : {**$gte**:value}}).pretty()
    ```
> db.plane.find({"speed" : {**$gte**:205}}).pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
```

#### Find (less than) > db.plane.find({key : {**$lt**:value}}).pretty()
    ```
> db.plane.find({"speed" : {$lt:250}}).pretty()
{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"),
        "name" : "SS Consitution",
        "speed" : 170,
        "range" : 1150
}
{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
```

#### Find (less than or equal) > db.plane.find({key : {**$lte**:value}}).pretty()
    ```
> db.plane.find({"speed" : {$lte:250}}).pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}{
        "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"),
        "name" : "SS Consitution",
        "speed" : 170,
        "range" : 1150
}{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
```

#### Find (not equals) db.plane.find({key : {$ne:value}}).pretty()
    ```
> db.plane.find({"speed" : {$ne:170},"speed":{$ne:400}}).pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}
{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"),
        "name" : "SS Consitution",
        "speed" : 170,
        "range" : 1150
}
{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
```

### Find (logical AND and OR)


#### AND
AND in find() is represent by using values that are separated by ','

    ```
> db.plane.find({"range":2222}).pretty()
{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
```

#### OR
Or in find() is represent using $or with array$or :[{keyA:ValueA},{keyB:valueB}]

    ```
> db.plane.find({$or:[{"name":"SS Defiant"},{"range":3200}]}).pretty()
{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
```

##### Using OR and AND combo :)

```
> db.plane.find({"speed":{$gt:200},$or:[{"name":"SS Defiant"}]}).pretty()
{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}
```


#### Projection db.COLLECTION.find({},{keyA:1,keyB:0})

Projection works like find but it return selected data rather than all data from document.
db.COLLECTION.find({},{keyA:1,keyB:0}) where 1 means display, 0 do not display

* by default _id will be always display, so if you don't want display _id simply add ```"_id":0``` for example:
* * ```db.plane.find({},{"_id":0,"name":1})```

    ```
(use normald find() )
> db.plane.find().pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}
{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}
{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"),
        "name" : "SS Consitution",
        "speed" : 170,
        "range" : 1150
}
{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
(use projection)

> db.plane.find({},{"name":1})
{ "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"), "name" : "SS Galaxy" }
{ "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"), "name" : "SS Defiant" }
{ "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"), "name" : "SS Voyager" }
{ "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"), "name" : "SS Consitution" }
{ "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"), "name" : "SS Ambassador" }
{ "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"), "name" : "SS Akira" }
{ "_id" : ObjectId("57ff8191ca6a9fc91c6d2b0b"), "name" : "SS Soverign XXL" }

(to display without _id )
> db.plane.find({},{"_id":0,"name":1}) 

{ "name" : "SS Galaxy" }
{ "name" : "SS Defiant" }
{ "name" : "SS Voyager" }
{ "name" : "SS Consitution" }
{ "name" : "SS Ambassador" }
{ "name" : "SS Akira" }
{ "name" : "SS Soverign XXL" }

```

### Find with limit() (>db.COLLECTION_NAME.find().limit(NUMBER))
    limit() method set how many records will be displayed


    ```
(this is typical find method with projection to display name of the ship only)

> db.plane.find({},{"name":1,"_id":0}).pretty()
{ "name" : "SS Galaxy" }
{ "name" : "SS Defiant" }
{ "name" : "SS Voyager" }
{ "name" : "SS Consitution" }
{ "name" : "SS Ambassador" }
{ "name" : "SS Akira" }
{ "name" : "SS Soverign XXL" }

using limit() method to display first 4 documents
> db.plane.find({},{"name":1,"_id":0}).pretty().limit(4)
{ "name" : "SS Galaxy" }
{ "name" : "SS Defiant" }
{ "name" : "SS Voyager" }
{ "name" : "SS Consitution" }
```


### Sorting with sort()
    db.COLLECTION_NAME.find().sort({KEY:1})
sort method is used to sort records using some criteria.

    Specify sorting order:
    * 1 is used for ascending order
* -1 is used for descending order.

    ```
this is list of ships with their speed
> db.plane.find({},{"name":1,"speed":1,"_id":0}).pretty()
{ "name" : "SS Galaxy", "speed" : 250 }
{ "name" : "SS Defiant", "speed" : 400 }
{ "name" : "SS Voyager", "speed" : 205 }
{ "name" : "SS Consitution", "speed" : 170 }
{ "name" : "SS Ambassador", "speed" : 220 }
{ "name" : "SS Akira", "speed" : 500 }
{ "name" : "SS Soverign XXL", "speed" : 466 }

SORT by speed in ascending order:

> db.plane.find({},{"name":1,"speed":1,"_id":0}).pretty().sort({"speed":1})
{ "name" : "SS Consitution", "speed" : 170 }
{ "name" : "SS Voyager", "speed" : 205 }
{ "name" : "SS Ambassador", "speed" : 220 }
{ "name" : "SS Galaxy", "speed" : 250 }
{ "name" : "SS Defiant", "speed" : 400 }
{ "name" : "SS Soverign XXL", "speed" : 466 }
{ "name" : "SS Akira", "speed" : 500 }

SORT by speed in descending order:

> db.plane.find({},{"name":1,"speed":1,"_id":0}).pretty().sort({"speed":-1})
{ "name" : "SS Akira", "speed" : 500 }
{ "name" : "SS Soverign XXL", "speed" : 466 }
{ "name" : "SS Defiant", "speed" : 400 }
{ "name" : "SS Galaxy", "speed" : 250 }
{ "name" : "SS Ambassador", "speed" : 220 }
{ "name" : "SS Voyager", "speed" : 205 }
{ "name" : "SS Consitution", "speed" : 170 }
```
### db.COLLECTION.insert(document) and
-- create new document (use save for insert/update)

    ```
> db.ufo.insert({
    "name":"Borg Cube",
    "description":"A borg generic purpose ship",
    "speed":9.8,cloakable:true
    })
    
WriteResult({ "nInserted" : 1 })

> db.ufo.save({
    "_id" : ObjectId("57fbc1759505f0047ef35a6e"),
    "name":"BORG Cube",
    "description":"A borg generic purpose ship",
    "speed":9.8,cloakable:true
    })
    
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.ufo.find()

{
    "_id" : ObjectId("57fbc1759505f0047ef35a6e"),
    "name" : "BORG Cube",
    "description" : "A borg generic purpose ship", 
    "speed" : 9.8, 
    "cloakable" : true
    }
```




### db.stats()
show statistic about database

### use DATABASE_NAME
switch to database DATABASE_NAME

### show dbs
    shows database in this mongo instance

    * In other to see Your created database on  list you need to insert atleast one document into it.

### show collections
    shows collections :)

### update and save document in collection

#### update db.COLLECTION.update(UPDATE_CRITERIA,NEW_VALUE)
    The update() method updates the values in the existing document.

        ```
(data setup)
> db.plane.insert({"name": "SS Sovereign","speed":475,"range":10000})
WriteResult({ "nInserted" : 1 })

(example)

> db.plane.update({ "speed":475},{$set:{"speed": 450}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.plane.find({"name":"SS Sovereign"}).pretty()
{
        "_id" : ObjectId("57ff8191ca6a9fc91c6d2b0b"),
        "name" : "SS Sovereign",
        "speed" : 450,
        "range" : 10000
}
```

#### save db.COLLECTION.save(document)
    The save() method replaces the existing document with the new document
        ```
(data setup)
> db.plane.insert({"name": "SS Sovereign","speed":475,"range":10000})
WriteResult({ "nInserted" : 1 })

(example)

> db.plane.save({ "_id" : ObjectId("57ff8191ca6a9fc91c6d2b0b"),"name" : "SS Soverign XXL", "speed": 466, "range" : 8770})	

(result)

> db.plane.find({"_id": ObjectId("57ff8191ca6a9fc91c6d2b0b")}).pretty()
{
        "_id" : ObjectId("57ff8191ca6a9fc91c6d2b0b"),
        "name" : "SS Soverign XXL",
        "speed" : 466,
        "range" : 8770
}

```

### delete documents and collections
        ```
> db.animals.insert({"name":"Dog","fly?": false,"underwater?":false})
WriteResult({ "nInserted" : 1 })
> db.animals.insert({"name":"Cat","fly?": false,"underwater?":false})
WriteResult({ "nInserted" : 1 })
> db.animals.insert({"name":"Dragon","fly?": true,"underwater?":false})
WriteResult({ "nInserted" : 1 })
> db.animals.insert({"name":"Hawk","fly?": true,"underwater?":false})
WriteResult({ "nInserted" : 1 })
> db.animals.insert({"name":"Shark","fly?": false,"underwater?":true})
WriteResult({ "nInserted" : 1 })
```

#### remove document by criteria

        ```
> db.animals.find().pretty()
{
        "_id" : ObjectId("5800e0deca6a9fc91c6d2b0c"),
        "name" : "Dog",
        "fly?" : false,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e0e5ca6a9fc91c6d2b0d"),
        "name" : "Cat",
        "fly?" : false,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e0f2ca6a9fc91c6d2b0e"),
        "name" : "Dragon",
        "fly?" : true,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e0f9ca6a9fc91c6d2b0f"),
        "name" : "Hawk",
        "fly?" : true,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e10bca6a9fc91c6d2b10"),
        "name" : "Shark",
        "fly?" : false,
        "underwater?" : true
}

> db.animals.remove({"fly?":true})
WriteResult({ "nRemoved" : 2 })

> db.animals.find().pretty()
{
        "_id" : ObjectId("5800e0deca6a9fc91c6d2b0c"),
        "name" : "Dog",
        "fly?" : false,
        "underwater?" : false
}{
        "_id" : ObjectId("5800e0e5ca6a9fc91c6d2b0d"),
        "name" : "Cat",
        "fly?" : false,
        "underwater?" : false
}{
        "_id" : ObjectId("5800e10bca6a9fc91c6d2b10"),
        "name" : "Shark",
        "fly?" : false,
        "underwater?" : true
}
```

#### remove first document
        ```
> db.animals.remove({"fly?":true},1)
WriteResult({ "nRemoved" : 1 })

> db.animals.find().pretty()
{
        "_id" : ObjectId("5800e364ca6a9fc91c6d2b11"),
        "name" : "Dog",
        "fly?" : false,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e369ca6a9fc91c6d2b12"),
        "name" : "Cat",
        "fly?" : false,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e376ca6a9fc91c6d2b14"),
        "name" : "Hawk",
        "fly?" : true,
        "underwater?" : false
}
{
        "_id" : ObjectId("5800e37dca6a9fc91c6d2b15"),
        "name" : "Shark",
        "fly?" : false,
        "underwater?" : true
}
```
#### remove collection

        ```
> db.animals.remove({})
WriteResult({ "nRemoved" : 5 })

> db.animals.find().pretty()
```

## Indexing

    **db.COLLECTION_NAME.createIndex({KEY:1})** (In Mongo 2 was known as ensureIndex and in Mongo 1 was known as .... createIndex . no idea why ;)

    Indexes are special data structures, that store a small portion of the data set in an easy-to-traverse form,so helps with the efficient resolution of queries.
        Without indexes, MongoDB must scan every document of a collection to select those documents that match the query statement which is highly inefficient and require MongoDB to process a large volume of data.

        Specify sorting order:
        * 1 is used for ascending order
    * -1 is used for descending order.

        What are Indexes in MongoDB?
        Indexes support the efficient execution of queries in MongoDB. Without indexes, MongoDB must perform a collection scan, i.e. scan every document in a collection, to select those documents that match the query statement. If an appropriate index exists for a query, MongoDB can use the index to limit the number of documents it must inspect.
        by default for a new collection?
    By default, MongoDB created the _id collection for every collection.

    ```
> db.plane.find().pretty()
{
        "_id" : ObjectId("57fe359aca6a9fc91c6d2b05"),
        "name" : "SS Galaxy",
        "speed" : 250,
        "range" : 1700
}
{
        "_id" : ObjectId("57fe35bcca6a9fc91c6d2b06"),
        "name" : "SS Defiant",
        "speed" : 400,
        "range" : 1220
}
{
        "_id" : ObjectId("57fe35dbca6a9fc91c6d2b07"),
        "name" : "SS Voyager",
        "speed" : 205,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3698ca6a9fc91c6d2b08"),
        "name" : "SS Consitution",
        "speed" : 170,
        "range" : 1150
}
{
        "_id" : ObjectId("57fe36c4ca6a9fc91c6d2b09"),
        "name" : "SS Ambassador",
        "speed" : 220,
        "range" : 2222
}
{
        "_id" : ObjectId("57fe3706ca6a9fc91c6d2b0a"),
        "name" : "SS Akira",
        "speed" : 500,
        "range" : 3200
}
{
        "_id" : ObjectId("57ff8191ca6a9fc91c6d2b0b"),
        "name" : "SS Soverign XXL",
        "speed" : 466,
        "range" : 8770
}

> db.plane.createIndex({"name":1,"speed":-1})
{
        "createdCollectionAutomatically" : false, <- (*1)
        "numIndexesBefore" : 1,
        "numIndexesAfter" : 2,
        "ok" : 1
}

(*1) The createdCollectionAutomatically indicates if the operation created a collection. If a collection does not exist, MongoDB creates the collection as part of the indexing operation.
```

    ? DON'T WHY this db.animals.remove() does not work



    pretty() display result in formatted way.

        ```
db.ships.find({KEY:{WHERE:33}})
	-- where WHERE
		$gt - greater than
		$gte - greater than and equals
		$lt - less than
		$lte -  - less than and equals

for example:
	1. Inserting example data:
		db.ships.insert({"number": 25})
		db.ships.insert({"number": 29})
		db.ships.insert({"number": 33})
		db.ships.insert({"number": 37})
		db.ships.insert({"number": 41})		

		db.ships.find() 
			will return all records (keep in mind that _id is random)
			{ "_id" : ObjectId("57f26056938bb376542ca156"), "number" : 25 }
			{ "_id" : ObjectId("57f2605a938bb376542ca157"), "number" : 29 }
			{ "_id" : ObjectId("57f2605e938bb376542ca158"), "number" : 33 }
			{ "_id" : ObjectId("57f26065938bb376542ca159"), "number" : 37 }
			{ "_id" : ObjectId("57f26068938bb376542ca15a"), "number" : 41 }

		db.ships.find({"number":33})
			{ "_id" : ObjectId("57f2605e938bb376542ca158"), "number" : 33 }

		db.ships.find({"number":{$lte:33}})
			{ "_id" : ObjectId("57f26056938bb376542ca156"), "number" : 25 }
			{ "_id" : ObjectId("57f2605a938bb376542ca157"), "number" : 29 }
			{ "_id" : ObjectId("57f2605e938bb376542ca158"), "number" : 33 }

		db.ships.find({"number":{$gte:33}})
			{ "_id" : ObjectId("57f2605e938bb376542ca158"), "number" : 33 }
			{ "_id" : ObjectId("57f26065938bb376542ca159"), "number" : 37 }
			{ "_id" : ObjectId("57f26068938bb376542ca15a"), "number" : 41 }

		db.ships.find({"number":{$gt:33}})
			{ "_id" : ObjectId("57f26065938bb376542ca159"), "number" : 37 }
			{ "_id" : ObjectId("57f26068938bb376542ca15a"), "number" : 41 }

		db.ships.find({"number":{$gte:33}})
			{ "_id" : ObjectId("57f2605e938bb376542ca158"), "number" : 33 }
			{ "_id" : ObjectId("57f26065938bb376542ca159"), "number" : 37 }
			{ "_id" : ObjectId("57f26068938bb376542ca15a"), "number" : 41 }
		
		db.ships.find({"number":{$ne:33}})
			{ "_id" : ObjectId("57f26056938bb376542ca156"), "number" : 25 }
			{ "_id" : ObjectId("57f2605a938bb376542ca157"), "number" : 29 }
			{ "_id" : ObjectId("57f26065938bb376542ca159"), "number" : 37 }
			{ "_id" : ObjectId("57f26068938bb376542ca15a"), "number" : 41 }

	AND in MongoDB ( pass multiple keys by separating them by ','  )
		db.mycol.find({key1:value1, key2:value2}).pretty()
```

###  List all the indexes on a particular collection
    db.COLLECTION_NAME.getIndexes()


## explain()
    As name suggest it explain how command/method can be used with various information

## Worth to remember:
        * In mongodb default database is test. If you didn't create any database then collections will be stored in test database.

* What is the difference between save and insert in Mongo DB?
* save insert or update a document. Insert does only an insertion. If you don't specify _id in the document while you db.COLLECTION.save(document) then save() method will work same as insert() method

    *  covered query  (TODO) is the one in which fields used in the query are part of an index used in the query, and the fields returned in the results are in the same index Since all the fields are covered in the index itself, MongoDB can match the query condition as well as return the result fields using the same index without looking inside the documents.

    * Aggregations operations process data records and return computed results. They group values from multiple documents , perform various operations and return result.MongoDB has 3 ways to perform aggregation: the aggregation pipeline, the map-reduce function, and single purpose aggregation methods and commands.

    * GridFS is a file system for files that exceed the BSON-document size limit of 16MB. (GridFS divides a file into parts, or chunks, and stores each of those chunks as a separate document.(
    * Concurrency MongoDB uses reader-writer locks that allow concurrent readers shared access to a resource, such as a database or collection, but give exclusive access to a single write operation.

    * What is Replication in MongoDB? Explain.
        Replication is the process of synchronizing data across multiple servers. Replication provides redundancy and increases data availability. With multiple copies of data on different database servers, replication protects a database from the loss of a single server. Replication also allows you to recover from hardware failure and service interruptions.

    * What are Primary and Secondary Replica sets?
        Primary and master nodes are the nodes that can accept writes. MongoDB's replication is 'single-master:' only one node can accept write operations at a time.

    Secondary and slave nodes are read-only nodes that replicate from the primary.

        How does Journaling work in MongoDB?
        When running with journaling, MongoDB stores and applies write operations in memory and in the on-disk journal before the changes are present in the data files on disk. Writes to the journal are atomic, ensuring the consistency of the on-disk journal files. With journaling enabled, MongoDB creates a journal subdirectory within the directory defined by dbPath, which is /data/db by default.


    NOTES NOTES NOTES

    SLF4J is a façade for various logging frameworks




    https://www.linkedin.com/pulse/whats-next-chinese-companies-after-brexit-gordon-orr?trk=eml-b2_content_ecosystem_digest-recommended_articles-123-null&midToken=AQH251li7xkXQQ&fromEmail=fromEmail&ut=2NSESzB3Q4unw1


        AngularJs

    Do not use user input to generate template dynamically
    Do not run user input though eval scope

    https://www.slideshare.net/mobile/x00mario/an-abusive-relationship-with-angularjs
