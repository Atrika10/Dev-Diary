### 1. What is String 
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

### What is String Pool? Explain it.

The String Pool, also known as the String Intern Pool, is a special memory region in the Java heap where the Java Virtual Machine (JVM) stores string literals. 

**Why is it Used?**
- **Memory Efficiency:** The primary purpose of the String Pool is to save memory. Since strings are widely used in Java applications, having multiple identical strings can lead to high memory consumption.
- **Performance Improvement:** By storing only one copy of each literal string, Java reduces memory usage and improves performance.

**How Does it Work?**
1. **String Literals:**
   - When you create a string literal, Java checks the String Pool to see if an identical string already exists.
   - If it does, Java will reference the existing string from the pool.
   - If it does not, Java will add the new string to the pool.

2. **String Objects Created with `new`:**
   - When you create a string using the `new` keyword, Java creates a new string object in the heap, even if an identical string already exists in the pool.
   - To add such strings to the pool, you can use the `intern()` method, which explicitly adds the string to the pool or returns the reference if it already exists.

**Example:**

```java
public class StringPoolExample {
    public static void main(String[] args) {
        String str1 = "Hello"; // This will refer to the string in the pool
        String str2 = "Hello"; // This will refer to the same string in the pool
        
        // Both str1 and str2 point to the same object
        System.out.println(str1 == str2); // true
        
        String str3 = new String("Hello"); // This creates a new string object in the heap
        System.out.println(str1 == str3); // false
        
        // Using intern() method to add str3 to the pool
        String str4 = str3.intern();
        System.out.println(str1 == str4); // true
    }
}
```

- **String Pool** is a memory area for string literals.
- It enhances **memory efficiency** and **performance** by storing only one copy of each string.
- String literals are automatically added to the pool, whereas strings created with `new` are not unless explicitly interned using the `intern()` method. 

Explaining the String Pool in this way shows a clear understanding of how Java manages strings and optimizes memory usage, which is a common and important concept in Java programming.

### Some String methods

`length()` method.

Example:
```java
String str = "Hello";
int length = str.length(); // 5 
```

 `concat()` method.

Example:
```java
Copy code
String str1 = "Hello";
String str2 = "World";
String result = str1 + " " + str2; // "Hello World"
// Or
result = str1.concat(" ").concat(str2); // "Hello World"
```
`uppercase()` or `lowercase()`?

Example:
```java
String str = "Hello";
String upper = str.toUpperCase(); // "HELLO"
String lower = str.toLowerCase(); // "hello"
```
`contains()` method
Example:
```java
String str = "Hello, World!";
boolean contains = str.contains("World"); // true
```
 `replace()` method
Example:
```java
String str = "Hello, World!";
String replacedStr = str.replace("World", "Java"); // "Hello, Java!"
```
`split()` method.
Example:
```java
String str = "Hello, World!";
String[] parts = str.split(", "); // ["Hello", "World!"]
```

`toCharArray()` method.
Example:
```java
String str = "Hello";
char[] charArray = str.toCharArray(); // ['H', 'e', 'l', 'l', 'o']
```
#### How do you compare two strings lexicographically?

 `compareTo()` method
Example:
```java
String str1 = "apple";
String str2 = "banana";
int result = str1.compareTo(str2); // negative value because "apple" is lexicographically less than "banana"
```
#### How do you remove leading and trailing spaces from a string?

Using the `trim()` method.
Example:
```java
String str = "   Hello, World!   ";
String trimmedStr = str.trim(); // "Hello, World!"
```

#### What are some common String methods?
Explanation: Some commonly used string methods include `substring()`, `charAt()`, `indexOf()`, `lastIndexOf()`, and `isEmpty()`.

Example:
```java
String str = "Hello, World!";
String subStr = str.substring(7); // "World!"
char charAt = str.charAt(1); // 'e'
int index = str.indexOf('o'); // 4
int lastIndex = str.lastIndexOf('o'); // 8
boolean isEmpty = str.isEmpty(); // false
```