
As per the Spring Boot doc, the @SpringBootApplication annotation is equivalent to using @Configuration, @EnableAutoConfiguration, and @ComponentScan with their default attributes

3) How to disable a specific auto-configuration class?
@EnableAutoConfiguration(exclude={DataSourceAutoConfiguration.class})


4) What is Spring Actuator? What are its advantages?

Spring Boot provides lots of auto-configuration features that help developers quickly develop production components. But if you think about debugging and how to debug, if something goes wrong, we always need to analyze the logs and dig through the data flow of our application to check to see what's going on. So, the Spring Actuator provides easy access to those kinds of features.

6) What is the Spring Initializer?

The Spring Initializer is a web application that generates a Spring Boot project with everything you need to start it quickly. 

7) What is a shutdown in the actuator?

Shutdown is an endpoint that allows the application to be gracefully shutdown. This feature is not enabled by default.