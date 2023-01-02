## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._

1. I repeatedly find that audit logs are the backbone of all good security policy and effective incident response. There’s a wonderful trend in CI/CD/DevOps culture where centralized logging and alerting is becoming a standard practice.
2. Be aware of user privacy in what you log, and how relevant long term storage would be in a breach.
3. Add security level to your logging https://www.owasp.org/index.php/How_to_add_a_security_log_level_in_log4j
4. Each log should have:
    -   Timestamp (when)
    -   System, Application, or Component (where)
    -   User (who)
    -   Action (what)
    -   Status (result)
    -   Priority (severity, importance, rank, level, etc)
5. Events To Log
    -   Authentication/Authorization Decisions (including logoff)
    -   System Access, Data Access
    -   System/Application Changes (especially privilege changes)
    -   Data Changes
    -   Invalid Input (possible badness/threats)
    -   Resources (RAM, Disk, CPU, Bandwidth, any other hard or soft limits)
6. Health/Availability / Automated task
    -   Startups/Shutdowns
    -   Faults/Errors
7. Log any variables in logging statements, because without these information, there’s limited information about the application that is captured by the log, and finding out what actually happened might feel like searching for a needle in a log file.
8. What log in each level:
    - FATAL should be reserved for errors that cause the application to crash or fail to start (ex: JVM out of memory).
    - ERROR should contain technical issues that need to be resolved for proper functioning of the system (ex: couldn’t connect to database).
    - WARN is best used for temporary problems or unexpected behavior that does not significantly hamper the functioning of the application (ex: failed user login).
    - INFO should contain messages that describe what is happening in the application (ex: user registered, order placed).
    - DEBUG is intended for messages that could be useful in debugging an issue (ex: method execution started).
    - TRACE is similar to DEBUG but contains more detailed events (ex: data model updated).
    - Logging Sensitive Information. The best way to avoid this is simply to make sure you never log this kind of sensitive information. What’s more, logging some categories of data, such as financial information, is also heavily regulated and can have serious legal implications.
    - Automated log analysis to check security
9.  Log all your inbound traffic. We keep logs on all inbound connections. This enabled all of our investigations. You can’t investigate what you don’t log.
10. Use 2FA. That remaining system that still uses legacy authentication can be your biggest vulnerability.