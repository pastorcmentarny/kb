## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._

# Spring Boot 2.3
  .Graceful shutdown is used to continue pending requests for a certain time period after stopping the application.

The following snippet shows how to enable the graceful shutdown and configure the timeout value to 30 seconds:

server.shutdown=graceful

spring.lifecycle.timeout-per-shutdown-phase=30s


##Spring Boot 2.1

0.  Java 11 Support
0.  JUnit 5 improvements. No need for @ExtendWith(SpringExtension.class)
0.  Logging improvements. group logging categories using logging.group.{groupName}={first},{second} (logging.group.web and logging.group.sql are already defined).
0.  Lazy JPA startup: specify spring.data.jpa.repositories.bootstrap-mode=lazy to turn it on.
0.  It uses In 1.18, Lombok will no longer generate a private, no-args constructor by default. It can be enabled by setting lombok.noArgsConstructor.extraPrivate=true in a lombok.config configuration file.
0.  Profile matching has been improved to support an expression format. For instance production & (us-east | eu-central) indicates a match if the production profile is active and either the us-east or eu-central profiles are active.
0.  Logging Groups
    * define the group
    * logging.group.tomcat=org.apache.catalina, org.apache.coyote, org.apache.tomcat
0.  Auto-configuration is now provided for Kafa Streams when a org.apache.kafka:kafka-streams dependency is declared.
0.  Micrometer
    * Common Micrometer Tags
```properties
management.metrics.tags.region=us-east-1
management.metrics.tags.stack=prod
```      
* Error page shows stacktraces when Devtools is in use.
  Kafka auto-configuation now supports errorHandler transactionManager and afterRollbackProcessor beans.
* ongoDB auto-configuration will now back-off when a com.mongodb.client.MongoClient bean is defined (as well as the more usual com.mongodb.MongoClient).


Resource:
* https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-2.1-Release-Notes
* https://github.com/spring-projects/spring-framework/wiki/Upgrading-to-Spring-Framework-5.x#upgrading-to-version-51
