* It is a LTS release.
* Oracle did lots of changes 
    * Java is still free
    * Use openjdk version instead of oracle's one
* new Files Utility Methods
* new exciting methods The String class 
 * strip()
 * stripLeading()
 * stripTrailing()
 * isBlank()
 * lines()
 * repeat(n)
* Remove
  * lots of packages like cobra
  * methods from Tread Class destroy()and  stop(Throwable obj)
* Epsilon Garbage Collector. Lazy as Dom Garbage Collector as he do not reclaim memory.
   * Good for performance testing
*   Z Garbage Collector is a scallable low-latency GC
    * Aim is ZGC pause time **do not** increase with the heap or live-set size but **do** increase with the root-set size (for example treads )
* The strip() method is new in Java 11. It removes whitespace from both ends of a string, where whitespace is defined using Unicode semantics. This differs from the older String.trim() method, which uses an anachronistic definition of whitespace based on ASCII control characters.    
   
