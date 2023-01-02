## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 


TODO:
* https://www.javacodegeeks.com/2016/06/5-common-hibernate-exceptions-fix.html
* 

HIBERNATE
What is the difference between save, persist and saveOrUpdate methods in Hibernate?

TODO:
http://javarevisited.blogspot.co.uk/2013/05/10-hibernate-interview-questions-answers-java-j2ee-senior.html
http://www.java67.com/2016/02/top-20-hibernate-interview-questions.html

Why is it better to use hibernate than JDBC for database interaction in various Java applications?
Hibernate provides an OO view of the database by mapping the various classes to the database tables.
This helps in thinking in terms of the OO language then in RDBMS terms and hence increases productivity.


Define what is JDBC and what is Hibernate, as well as their differences.
JDBC stands for Java Database Connectivity allows developers to connect, query and update a database using the Structured Query Language. JDBC API standard provides Java developers to interact with different RDBMS and access table data through Java application without learning RDBMS details and using Database Specific JDBC Drivers.
Hibernate is an Object-Relational Mapping (ORM) solution for JAVA. It is a powerful, high performance object/relational persistence and query service. It allows us to develop persistent classes following object-oriented idiom – including association, inheritance and polymorphism.
 
 
 
 
 
 
 
 
JDBC
Hibernate
With JDBC, developer has to write code to map an object model's data representation to a relational data model and its corresponding database schema.  
Hibernate is flexible and powerful ORM solution to map Java classes to database tables. Hibernate itself takes care of this mapping using XML files so developer does not need to write code for this.
With JDBC, it is developer’s responsibility to handle JDBC result set and convert it to Java objects through code to use this persistent data in application. So with JDBC, mapping between Java objects and database tables is done manually.  
Hibernate reduces lines of code by maintaining object-table mapping itself and returns result to application in form of Java objects. It relieves programmer from manual handling of persistent data, hence reducing the development time and maintenance cost.  
With JDBC, caching is maintained by hand-coding.  
Hibernate, with Transparent Persistence, cache is set to application work space. Relational tuples are moved to this cache as a result of query. It improves performance if client application reads same data many times for same write. Automatic Transparent Persistence allows the developer to concentrate more on business logic rather than this application code.  
 
