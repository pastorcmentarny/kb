## **HONEST WARNING**

**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._

# Java 17

1. 356:    Enhanced Pseudo-Random Number Generators
2. 403:    Strongly Encapsulate JDK Internals

```
You cannot do this:
System.out.println(sun.security.util.SecurityConstants.ALL_PERMISSION);
You will see error: Package 'sun.security.util' is declared in module 'java.base', which does not export it to the unnamed module
```

3. 409:    Sealed Classes
5. Java 17 is issued under the new NFTC (Oracle No-Fee Terms and Conditions) license. The new Oracle licensing model
   allowed to use the Oracle JDK version for free for production and commercial use
   (well, at least until the next licencing change :D).
6. LTS releases changed to a two-year cadence; enterprises and developers have more frequent opportunities to move an
   application onto an LTS release.

Another things that doesn't require example:
306:    Restore Always-Strict Floating-Point Semantics 398:    Deprecate the Applet API for Removal 407:    Remove RMI
Activation 410:    Remove the Experimental AOT and JIT Compiler 411:    Deprecate the Security Manager for Removal
 
