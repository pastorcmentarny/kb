## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._


The cloud intends to make it easy to provision infrastructure when you need it, and just as easy to release it when you don't. 


What is service discovery?

In a microservices-based application, there are often many microservices communicating with each other to achieve some common outcome.

So, we inherently require some method by which a client can call any specific service at a given point of time.

For that to take place, we must have the URL (API endpoint) of that service configured somewhere (in some property file such as application.properties, appl.yml, or something like that).

But it' a very bad practice to keep URLs hard coded. We should not hard code the URL of any service in our application for multiple reasons:

Cloud-based application URLs are dynamic so they need to be updated every now and then.

Hard coded URLs need code change/code updates.

The basic requirement of an application to be run on multiple environments (e.g. local, QA, production, etc. (RFS/UAT/PAT)).

Load balancing. This implies that for similar kinds of service there are multiple URLs, so deciding which URL to hard code becomes a bottle neck.

kubernetes - the tests are acceptance tests that validate the behavior of the application.


The 12 Factor App
Codebase - One Codebase Tracked in Version Control, Many Deploys
Config - Store Config in the Environment

Backing services - Treat Backing Services as Attached Resources.All of these need to be configurable, and it should be easy to switch from one backing service to another.

Build, Release, Run - Strictly Separate Build and Run Stages

Processes - Execute the App as One or More Stateless Processes

Ideally an application should be stateless. 
Logs - Treat Logs as Event Streams
Visibility is one of the most important requirements of a microservices architecture.
All one needs to do in order to debug a problem, is to go to the central dashboard and search for it.

Challenges of Developing Cloud Applications

Security

Security is a major concern, as you do not own the infrastructure, and it can be dynamically acquired and released.

Application Compatibility

Most applications are not compatible with the cloud. Applications have to be enhanced to make them cloud-native.

Scale-out aggressively.Scale in in-steps slowly