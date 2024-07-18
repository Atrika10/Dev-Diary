# Core JAVA

    - main
    - static
    - public
    - variables in java
    - concept of round off - C vs Java 
    - user Input in java  
    - Primitive & Non Primitive data types
    - Operators
    - unary
    - ternary
    - shift
    - Relational & logical
    - Bitwise & Assignment
    - JAVA operator Precedence & Associativity
    - String Method
    - Math Functions in java
    - How to generate an otp via java
    - Garbage collection 
    - If-else Condition 
    - Swich
    - Array
    - Loops
    - break() & continue()
    - Methods in java
    - Exceptional Handling in java
    - URL Class in java
    - Socket Programming in java
    - 6 problem
    - Java AWT & Swing
    - JAVA Applet
    - Java Event Handling
    
## What is JDK?

**Definition:**
JDK stands for **Java Development Kit**. It is a software development environment used for developing Java applications and applets. It includes the necessary tools and libraries to create and run Java programs.

**Key Components of JDK:**

1. **JRE (Java Runtime Environment):**
   - The JRE is a part of the JDK that provides the libraries, Java Virtual Machine (JVM), and other components to run Java applications.
   - The JRE is what you need to run Java applications, but it does not contain the development tools like the compiler.

2. **Java Compiler (`javac`):**
   - The compiler converts Java source code (.java files) into bytecode (.class files) that can be executed by the JVM.
   - It checks for syntax errors and generates the bytecode that the JVM can interpret and run.

3. **Java Debugger (`jdb`):**
   - This tool helps in debugging Java programs. You can use it to find and fix errors in your code.
   - It allows you to set breakpoints, inspect variables, and control the execution flow of your program.

4. **Java Documentation (`javadoc`):**
   - This tool generates HTML documentation from Java source code comments.
   - It helps in creating documentation for your Java classes, methods, and fields, making it easier to understand and use the code.

5. **Java Archive Tool (`jar`):**
   - This tool is used to package multiple files into a single JAR (Java ARchive) file.
   - JAR files are used to distribute Java applications or libraries.

6. **Other Tools and Libraries:**
   - The JDK includes various other tools and libraries that help in Java development, such as `java` (the launcher for running Java applications), `javap` (a disassembler), and more.

**Example:**

1. **Installing JDK:**
   - To start developing Java applications, you need to install the JDK. It is available for different operating systems like Windows, macOS, and Linux.
   - You can download the JDK from the official Oracle website or use open-source versions like OpenJDK.

2. **Writing and Compiling a Java Program:**

   - **Writing a Program:**
     Write a simple Java program in a text editor and save it as `HelloWorld.java`.

     ```java
     public class HelloWorld {
         public static void main(String[] args) {
             System.out.println("Hello, World!");
         }
     }
     ```

   - **Compiling the Program:**
     Open a command prompt or terminal, navigate to the directory where you saved `HelloWorld.java`, and compile it using the `javac` command.

     ```sh
     javac HelloWorld.java
     ```

     This command creates a `HelloWorld.class` file, which contains the bytecode.

   - **Running the Program:**
     Run the compiled bytecode using the `java` command.

     ```sh
     java HelloWorld
     ```

     This command executes the `main` method of the `HelloWorld` class and prints "Hello, World!" to the console.

**Summary:**
The JDK is essential for Java development as it provides all the necessary tools and libraries to write, compile, debug, and run Java applications. It includes the JRE, compiler, debugger, documentation generator, and various other tools that make Java development easier and more efficient.

## The Purpose of a Class in Java

**Definition:**
A class in Java is a blueprint for creating objects. It defines a set of properties (fields) and behaviors (methods) that the objects created from the class can have. Classes help organize code into reusable components.

**Key Points:**
- A class is like a blueprint for an object.
- It defines what properties (attributes) and behaviors (methods) an object will have.
- Objects are instances of classes.

**Example:**

Let's say you want to create a program to represent and manage information about cars.

1. **Define the Class:**
   You create a `Car` class that has properties like `make`, `model`, and `year`, and behaviors like `startEngine` and `stopEngine`.

```java
// This is the Car class
public class Car {
    // Properties (fields)
    String make;
    String model;
    int year;

    // Constructor to initialize the properties
    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    // Behaviors (methods)
    public void startEngine() {
        System.out.println("The engine is starting.");
    }

    public void stopEngine() {
        System.out.println("The engine is stopping.");
    }
}
```

2. **Create Objects from the Class:**
   You can create objects (instances) of the `Car` class and use them.

```java
public class Main {
    public static void main(String[] args) {
        // Creating an object of the Car class
        Car myCar = new Car("Toyota", "Camry", 2020);

        // Accessing properties
        System.out.println("Make: " + myCar.make);
        System.out.println("Model: " + myCar.model);
        System.out.println("Year: " + myCar.year);

        // Calling methods
        myCar.startEngine();
        myCar.stopEngine();
    }
}
```

**Explanation:**
- **Class Definition:** The `Car` class has three properties (`make`, `model`, `year`) and two methods (`startEngine`, `stopEngine`).
- **Constructor:** The constructor `Car(String make, String model, int year)` is used to initialize the properties when creating an object.
- **Creating Objects:** In the `Main` class, we create an object `myCar` of the `Car` class with specific values for `make`, `model`, and `year`.
- **Using Objects:** We access the properties and call the methods of the `myCar` object.

**Purpose:**
- **Reusability:** Once the `Car` class is defined, you can create as many `Car` objects as needed with different values.
- **Organization:** Classes help organize code by grouping related properties and behaviors together.
- **Modularity:** Classes make the code modular, allowing you to manage and maintain it more easily.

In summary, a class is a fundamental concept in Java that helps in creating reusable and organized code structures. It defines the properties and behaviors that objects will have, making it easier to manage and use these objects in your programs.

## Why Classes are Required in Java

**1. Organization and Structure:**
- **Blueprint for Objects:** Classes provide a blueprint for creating objects. By defining a class, you specify the attributes (fields) and behaviors (methods) that the objects will have.
- **Grouping Related Code:** Classes group related data and functions together, making the code easier to understand and manage.

**Example:**
Without classes, you would have to manage each piece of data and functionality separately, which can become chaotic and hard to maintain.

```java
// Without classes
String make = "Toyota";
String model = "Camry";
int year = 2020;

void startEngine() {
    System.out.println("The engine is starting.");
}

void stopEngine() {
    System.out.println("The engine is stopping.");
}
```

With classes, everything related to a car is grouped together:

```java
public class Car {
    String make;
    String model;
    int year;

    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    public void startEngine() {
        System.out.println("The engine is starting.");
    }

    public void stopEngine() {
        System.out.println("The engine is stopping.");
    }
}
```

**2. Reusability:**
- **Reusable Code:** Once a class is defined, you can create multiple objects from it, reducing redundancy and promoting code reuse.

**Example:**

```java
Car car1 = new Car("Toyota", "Camry", 2020);
Car car2 = new Car("Honda", "Accord", 2021);
```

**3. Encapsulation:**
- **Data Protection:** Classes allow you to encapsulate data, meaning you can restrict access to the inner workings of an object and only expose what is necessary. This helps protect the data from unintended modifications.

**Example:**

```java
public class Car {
    private String make;
    private String model;
    private int year;

    public Car(String make, String model, int year) {
        this.make = make;
        this.model = model;
        this.year = year;
    }

    public String getMake() {
        return make;
    }

    public void setMake(String make) {
        this.make = make;
    }

    public void startEngine() {
        System.out.println("The engine is starting.");
    }

    public void stopEngine() {
        System.out.println("The engine is stopping.");
    }
}
```

**4. Inheritance:**
- **Code Extension:** Classes enable inheritance, where a new class can inherit properties and methods from an existing class. This promotes code reuse and the creation of more complex hierarchies.

**Example:**

```java
public class ElectricCar extends Car {
    private int batteryLife;

    public ElectricCar(String make, String model, int year, int batteryLife) {
        super(make, model, year);
        this.batteryLife = batteryLife;
    }

    public void chargeBattery() {
        System.out.println("The battery is charging.");
    }
}
```

**5. Polymorphism:**
- **Flexible Code:** Polymorphism allows objects to be treated as instances of their parent class rather than their actual class. This provides flexibility in code design.

**Example:**

```java
Car myCar = new ElectricCar("Tesla", "Model S", 2022, 300);
myCar.startEngine(); // Calls the startEngine method of Car
```

**Summary:**
Classes are required in Java because they provide structure, organization, and modularity to the code. They enable reusability, encapsulation, inheritance, and polymorphism, making it easier to create, manage, and extend complex software applications. By using classes, developers can write cleaner, more maintainable, and more efficient code.


