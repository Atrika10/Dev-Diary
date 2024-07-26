### What is JAVA NETWORKING ?
It is used to write programs that executes accross multiple devices connected by a network.
 - EX : If you are writing code for chat application where you ahve to transfer date over a network for that we should know about Java Networking.

* **`Package`**: Java networking is supported by the `java.net` package, which provides the necessary classes and interfaces.

* This package is used to sent Data from client side to server side using 2 protocol
    - TCP   (Transmission Control Protocol - Realiable & no data loss)
    - UDP   (User Datagram Protocol - Speed where we can't delay)

**URL (Uniform Resource Locator):**

- A URL specifies the address of a resource on the internet.

- Format: https://domainName:portNo/fileName

    - domainName: The website's address.
    - portNo: The server's port number (default is -1 if  - unspecified).
    - fileName: The specific file or page to access.
    - Example URL: https://www.atrikashow.com:60/index.html

The URL class in Java provides a simple, concise API to access and manipulate information from the internet using URLs.


- Example :
    ```java
    import java.net.URL;
    public class java{
       try {
            URL obj = new URL("https://www.atrikashow.com/index.html");
        System.out.println(obj.getProtocol());
        System.out.println(obj.getHost());
        System.out.println(obj.getPort());
        System.out.println(obj.getFile());
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
    ```

### Inet Address Class :

1. It representation an IP address & provide method to get the IP of any Host Name.
2. Inet Address class is used to encapsulate both the numerical IP address & both the domain name for that address. (2 things we will get)

- The `InetAddress` class in Java is part of the java.net package. It represents an Internet Protocol (IP) address, both IPv4 and IPv6, and provides methods for resolving hostnames to IP addresses and vice versa.

```java
import java.net.InetAddress;
public class Basics{
    
    public static void main(String[] args){

         try {
            // Get InetAddress for a hostname
            InetAddress address = InetAddress.getByName("www.example.com");
            
            // Print the hostname and IP address
            System.out.println("Host Name: " + address.getHostName());
            System.out.println("Host Address: " + address.getHostAddress());
            
            // Get local machine's InetAddress
            InetAddress localAddress = InetAddress.getLocalHost();
            System.out.println("Local Host Name: " + localAddress.getHostName());
            System.out.println("Local Host Address: " + localAddress.getHostAddress());
        } catch (Exception e) {
            System.out.println("Unable to resolve host: " + e.getMessage());
        } 
        
    }
}
```