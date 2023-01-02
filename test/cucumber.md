## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 


## Cucumber

Cucumber is a testing tool that supports Behavior Driven Development (BDD) framework. 
(find better explanation for this crap)  It is a Business Readable, Domain Specific Language that lets you describe software’s behaviour without detailing how that behaviour is implemented.

Cucumber allows automation functional validation that is easily read and understood. Cucumber was initially implemented in Ruby and then extended to Java framework. Both the tools support native JUnit.


##Gherkin (TODO improve it)

Gherkin is a plain English text language, which helps the tool - Cucumber to interpret and execute the test scripts.
Gherkin provides the common set of keywords in English text, which can be used by people amongst the different community and yet get the same output in the form of test scripts.


###Feature

A Feature can be defined as a standalone unit or functionality of a project. (For example: Create and remove the user from the social networking site.)


###Feature files
The file, in which Cucumber tests are written, is known as feature files.

A simple feature file consists of the following keywords/parts −

* Feature − Name of the feature under test.
* Description (optional) − Describe about feature under test.
* Scenario − What is the test scenario.
* Given − Prerequisite before the test steps get executed.
* When − Specific condition which should match in order to execute the next step.
* Then − What should happen if the condition mentioned in WHEN is satisfied.


### Steps Definitions
Steps definition file stores the mapping between each step of the scenario defined in the feature file with a code of function to be executed.


### Scenario

Scenario is one of the core Gherkin structures. Every scenario starts with the keyword “Scenario:” (or localized one) and is followed by an optional scenario title. Each feature can have one or more scenarios and every scenario consists of one or more steps.


### Scenario outline 
It  replaces variable/keywords with the value from the table. Each row in the table is considered to be a scenario.


### Annotations

Annotation is a predefined text, which holds a specific meaning.

* **Given** − describes the pre-requisite for the test to be executed.   (Given)
* **When** - defines the trigger point for any test scenario execution. (_WHEN I enter "<username>"_)
* **Then** − holds the expected result for the test to be executed. (_THEN login should be successful._)  
* **And** - provides the logical AND condition between any two statements. AND can be used in conjunction with GIVEN, WHEN and THEN statement. (_WHEN I enter my "<username>" AND I enter my "<password>"_)
* **But** - signifies logical OR condition between any two statements. OR can be used in conjunction with GIVEN, WHEN and THEN statement. (_THEN login should be successful. BUT home page should not be missing._)
* **Scenario** Details about the scenario under the test needs to be captured after the keyword “Scenario:”
* **Background** Background generally has the instruction on what to setup before each scenario runs. However, it gets executed after “Before” hook (to be covered later). So this is ideal to be used for code when we want to set up the web-browser or we want to establish the database connectivity.


##Other boring definitions:


##TODO
Find definition of Gherkin is the language that Cucumber

(TODO improve this!) **Treetop** is a language for describing languages. 