## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 


#Definitions

##BASICS:
All flows are made up of three essential elements: States, Transitions and Flow Data.

### Flow
A flow encapsulates a reusable sequence of steps that can execute in different contexts.

### State
It is a a step in flow that consists of a series of steps.
States are first-class elements of a web flow. As a flow executes, it transitions from one state to another state, performing some action, making some decision, or displaying some output at each step of the way.
* <action-state>	Performs one or more actions. The outcome of an action may determine the transition to be taken to the next state in the flow.
* <decision-state>	Evaluates one or more expressions to decide the next step in the flow.
* < ?-state>	    Denotes the final state of a flow. Upon entry to the end state, the flow is terminated.
* <subflow-state>	Starts another flow as a subflow.
* <view-state>	    A state that involves the user in the flow by presenting them with some output and possibly prompting them for input
  * <attribute>	Along with a nested <value> element, <attribute> declares a meta attribute to describe or annotate the state.
  * <binder>	Used to configure custom form binding.
  * <exception-handler>	References a <bean> (through the bean attribute) that implements FlowExecutionExceptionHandler that should handle exceptions thrown in this state.
  * <on-entry>	Specifies actions (evaluations, setting of variables, and/or fragment render requests) to be performed upon entry to this state.
  * <on-exit>	Specifies actions (evaluations, setting of variables, and/or fragment render requests) to be performed as exiting this state.
  * <on-render>	Specifies actions (evaluations, setting of variables, and/or fragment render requests) to be performed as rendering this state's view.
  * <secured>	Used with Spring Security to restrict access to this state given the current user's security attributes.
  * <transition>	Defines a path from this state to another state based on an event or exception. May optionally execute one or more actions in the course of the transition.
  * <var>	Declares a view instance variable.
#### Type of states

### Transitions

## Variables
* Declared variables are allocated when the flow starts.
* Any @Autowired transient references the variable holds are also rewired when the flow resumes.

### Scopes
* **Variable Scope** Web Flow can store variables in one of several scopes:

* * Flow Scope
* * * It gets allocated when a flow starts and destroyed when the flow ends. _any objects stored in this scope need to be Serializable (default implementation)_
* * View Scope
* * * It gets allocated when a view-state enters and destroyed when the state exits. View scope is only referenceable from within a view-state. _any objects stored in this scope need to be Serializable (default implementation)_
* * Request Scope
* * * It gets allocated when a flow is called and destroyed when the flow returns.
* * Flash Scope
* * * It gets allocated when a flow starts, cleared after every view render, and destroyed when the flow ends._any objects stored in this scope need to be Serializable (default implementation)_
* * Conversation Scope
* * * It gets allocated when a top-level flow starts and destroyed when the top-level flow ends. Conversation scope is shared by a top-level flow and all of its subflows._any objects stored in this scope need to be Serializable (default implementation)_

# Tags:

## action-state
"Performs one or more actions. The outcome of an action may determine the transition to be taken to the next state in the flow."

## attribute
<attribute>	Along with a nested <value> element, <attribute> declares a meta attribute to describe or annotate the flow.

## bean-import
<bean-import>	Imports user-defined beans that are resolvable using flow expressions.

## decison-state
<decision-state>	Evaluates one or more expressions to decide the next step in the flow.

## On end
<on-end>	Actions to execute when the flow ends.

## On start
<on-start>	Actions to execute when the flow starts.

## Output
<output>	Declares an output to be returned to the caller of this flow.


## view-state element tag
Defines a step of the flow that renders a view.
* By convention, a view-state maps its id to a view template in the directory where the flow is located. For example, the state above might render /WEB-INF/hotels/booking/enterBookingDetails.xhtml if the flow itself was located in the /WEB-INF/hotels/booking directory.

## Transition tag
It is element to handle events that occur within a state.
```xml
<view-state id="enterBookingDetails">
    <transition on="submit" to="reviewBooking" />
</view-state>
```

## End-state element
Defines a flow outcome. When a flow transitions to a end-state it terminates and the outcome is returned.

## Exception Handler
<exception-handler>	Designates a bean that will handle exceptions for this flow.

## Evaluate element
It used to evaluate an expression at a point within your flow.
If the expression returns a value, that value can be saved in the flow's data model called flowScope:
```xml
<evaluate expression="houseSearch.findHouses(postcode)" result="flowScope.houses" />
```

## Input & Output
Use the name attribute to give name for input
Use the type attribute to declare the input attribute's type.
Use value to assign value
Use required attribute to specify is input is madatory or not
```xml
<input name="houseNumber" type="int"  value="flowScope.myParameterObject.hotelId" required="true" />

<end-state id="houseFounded">
    <output name="houseNumber" value="houseResult.houseNumber" />
</end-state>
```

## var element



# Actions
Most flows need to express more than just view navigation logic.
* On flow start
* On state entry
* On view render
* On transition execution
* On state exit
* On flow end



If the expression returns a value, that value can be saved in the flow's data model called **flowScope**

If the expression returns a value that may need to be converted, specify the desired type using the result-type attribute:


## Variables
Use the var element to declare a flow variable:
```<var name="searchCriteria" class="com.mycompany.myapp.hotels.search.SearchCriteria"/>```
Make sure your variable's class implements java.io.Serializable, as the instance state is saved between flow requests.


## Subflow
* Subflow is a flow that is called from another flow.
* The flow will wait until the subflow returns, then respond to the subflow outcome.


# Tips Tricks and Advices
