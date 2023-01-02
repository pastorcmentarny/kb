
## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 

* **Ansible** is a radically simple IT automation engine that automates cloud provisioning, configuration management, application deployment, intra-service orchestration, and many other IT needs.Designed for multi-tier deployments . Ansible works by connecting to your nodes and pushing out small programs, called "Ansible modules" to them.  there are no servers, daemons, or databases required.  
*  **Marathon** orchestrates the containers on top of **Mesos** as a framework. Also it does log every time it does anything with a container even though it can get a bit obscure in some cases (all those logs are in ELK). When **Mesos** starts a **Docker** container on one of the slaves, it will add labels to that container. _**Marathon** has nothing to do with the load balancing._
* Make sure you allocate virtual resources map to physical resources. For example. Remember OS and management use resources too. Know what and where your actual resources are.
## Feature toggle
*   Never reuse feature toggle, so it will not enable a feature that shouldn't be. Name toggle well. Feature toggle should have a short lifespan. Don't use feature toggle and permission .it is blurry permission boundary. Use authorisation service. Monitor toggles. Check rollout percentage, if is 100 (everybody) or 0 (nobody)  over a specific time.  Set alert if is 100 or 0.
## **The blue-green deployment strategy** 
* It can be implemented to reduce or remove downtime. It achieves this by running two identical production environments, Blue and Green. Let's assume Green is the existing live instance and Blue is the new version of the application. At any time, only one of the environments is live, with the live environment serving all production traffic
* It helps to reduce the downtime and even reduces it to zero depending on the application design and deployment approach.     
* It gives a rapid way of rollback of the application in case of production issue.     
* It helps to build confidence to business users as testing of new version can be done in Production in isolation before rollout.
* Challenges. When Applications which have DB changes while moving from Green to Blue version is one of the complex scenarios where the Blue version will have some DB changes as well. The reason is if you apply the DB changes while Green is running it may break the existing application and outage will be caused. One of the solution can be make application read-only  your application as read-only while you are switching from Green to Blue instances.
* Create easy upgrade and downgrade scripts/configurations for your dev and prod environments. You need to be able to switch easily between the two states of the system. This includes GC configuration, not just the JVM version.


## Chaos Engineering
Chaos Engineering is great for exposing unknown weaknesses in your production system, but if you are certain that a Chaos Engineering experiment will lead to a significant problem with the system, there’s no sense in running that experiment. Fix that weakness first. Then come back to Chaos Engineering and it will either uncover other weaknesses that you didn’t know about, or it will give you more confidence that your system is in fact resilient.- From Chaos Engineering Book