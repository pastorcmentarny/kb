# Java 15 
The idea is straightforward: common state and behaviour can be abstracted to a super-class and shared (through inheritance) by sub-classes. ealed classes (explained in detail in JEP 360) provide a fine-grained mechanism that allows a developer to restrict which other classes or interfaces may extend them.  


Records
One of the clarifications in JDK 15 is, “The implicitly declared fields corresponding to the record components of a record class are final and moreover are not modifiable via reflection (doing so will throw IllegalAccessException).”  Java finally has (if you’ll excuse the pun) truly final fields.

Native methods have now been explicitly prohibited from records since they could introduce behaviour that would be dependent on external state.
The new JEP also introduces the concept of local records.  These are similar in idea to local classes enabling a record to be defined in a method and have its scope of use limited to that method. All local records are implicitly static.   This is different from local classes that are never static. 