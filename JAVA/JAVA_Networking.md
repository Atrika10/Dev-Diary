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

## Socket Programming 
* Socket is the communication mechanism between two computers using TCP.
![alt text](media/image.png)

- each client have own socket
- server have it't own server soket
- server socket will create socket, as many clients as there are 
- now whatever data client want to send to the server & vice versa, it'll be done through this socket connections.
- client's data reached to the server socket through socket(which is created by server socket)
- Then server socket pass the data to the server

Your description of socket programming captures the fundamental concepts well. However, let's refine the wording for clarity and accuracy:

---

#### Steps in details

1. **Each Client Has Its Own Socket:**
   - In a networked application, each client establishes its own socket, which is an endpoint for communication.

2. **The Server Has Its Own Server Socket:**
   - The server creates a `ServerSocket`, which listens for incoming connection requests from clients. It acts as a welcoming door for clients.

3. **Server Socket Creates a New Socket for Each Client:**
   - When a client connects to the server, the `ServerSocket` creates a new `Socket` for that specific client. This `Socket` is used to handle communication between the server and the client.

4. **Data Transfer Through Socket Connections:**
   - Once the connection is established, the client and server can exchange data. The data transfer occurs through the socket connections established between the client and the server.

5. **Client's Data Reaches the Server Through the Socket:**
   - The data sent by the client is transmitted over the network and received by the server's corresponding socket.

6. **Server Socket Passes Data to the Server:**
   - The server processes the incoming data from the client through the socket connection. The server can then respond to the client, continuing the data exchange as needed.

---

## Steps to Establish a TCP Connection Using Sockets

1. **Server-Side Setup:**
   - **Create a `ServerSocket` Object:**
     - The server creates an instance of the `ServerSocket` class, specifying a port number. This port number is where the server listens for incoming connection requests from clients.
     - Example: `ServerSocket serverSocket = new ServerSocket(8080);`

2. **Listening for Connection Requests:**
   - **Accepting Client Connections:**
     - The server calls the `accept()` method on the `ServerSocket` object. This method blocks (waits) until a client makes a connection request.
     - When a connection request is received, the `accept()` method creates a new `Socket` object for the server to communicate with the client.
     - Example: `Socket clientSocket = serverSocket.accept();`

3. **Client-Side Setup:**
   - **Create a `Socket` Object:**
     - The client creates a `Socket` object, specifying the server's hostname or IP address and the port number to connect to.
     - This establishes a connection between the client and the server.
     - Example: `Socket socket = new Socket("localhost", 8080);`

4. **Establishing the Connection:**
   - **Connection Established:**
     - When the client creates the `Socket` object, a connection request is sent to the server. If the server accepts the request (via `accept()`), the connection is established.
     - Both client and server now have `Socket` objects representing the connection, through which they can communicate.

5. **Data Exchange:**
   - **Input and Output Streams:**
     -   The server and client communicate using input and output streams, with the client sending data to the server and the server responding.
     This is done through the `Socket` object on both sides.
     - Example: `InputStream in = socket.getInputStream(); OutputStream out = socket.getOutputStream();`

* NOTES : First run server side code & then client side code




