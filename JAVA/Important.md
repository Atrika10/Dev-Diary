### Garbage Collection
Garbage collection in Java is like a smart cleanup crew for memory. It automatically finds and clears away objects in memory that your program no longer uses, so you don't have to do it yourself.

* Points : 
- Garbage collector is always running in background.
- Main Objective of garbage collector is to free heap memory by destroying unreachable objects.

- An object is said to be unreachable if it doesn't contain any reference to it. Objects which are part of `island of isolation` are also unreachable.
- An object is said to be eligible for Garbage Collection if it is unreachable.

**Island of Isolation:** 
Object 1 references object 2 & Object 2 reference Object 1. Neither obj 1 nor obj 2 is referenced by any other object.That's an island of isolation.

Basically, an island of isolation is a group of objects that reference each other but they are not referenced by any active object in the application.
Even a single unrefernced objcect is an island of isolation too.