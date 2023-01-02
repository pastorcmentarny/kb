 0. one database per microservice must be designed; it must be private to that service only.
 0. the configuration should be stored in a Git repository.
 0. Components of microservices in the cloud:
    - Configuration Management
    - Dynamic Scale Up And Down
    - Service Registration
    - Service Discovery
    - Load Balancing
    - Visibility and Monitoring
    - API Gateway
    - Fault Tolerance
0. Never reuse feature toggle, so it will not enable a feature that shouldn't be. name toggle well. Feature toggle should have short lifespan. Don't use feature toggle and permission .it is blurry permission boundary . use autorisation service. monitor toggles . rollout percentage so if is 100 (everybody) or 0 (nobody)  over specifi time.  set alert if is 100 or 0

#### components 
*   micrometer - Micrometer provides a Java-based facade over the client libraries that the different monitoring tools provide.