### 1. what is String 
String is a class in Java and is defined in the java.lang package. It’s not a primitive data type like int and long. The String class represents character strings. String is used in almost all Java applications. String in immutable and final in Java and the JVM uses a string pool to store all the String objects. You can instantiate a String object using double quotes and you can overload the + operator for concatenation.

### 2.  Is String immutable or final in Java? If so, then what are the benefits of Strings being Immutable?

Strings in Java are immutable, meaning once a string is created, it cannot be changed. Any modification creates a new string.

Example :
```java
String str = "Hello";
str = str.concat(", World!"); // Creates a new string "Hello, World!"
```
* Benefits of String being Immutable : 
    - String pool is possible because String is immutable in Java.
    - It increases security because any hacker can’t change its value and it’s used for storing sensitive information such as a database username or password.

### String methods
