**Question 1** - What is inside a packet?

**Solution 1**: "All packets have a header, which stores the address or destination of a packet, and a payload which stores the data or message of the packet."

**Question 2** - What is the purpose of an internet layer in the TCP/IP protocol? What do you, as a client, need to specify in this protocol?

**Solution 2**: The purpose of this layer is to interconnect networks. As the client, you need to specify for the server what you would like to reach so that the server can provide it. 

**Question 3** - What is the purpose of the transport layer in the TCP/IP protocol? What do you, as a client, need to specify in this protocol?

**Solution 3**: The transport layer provides an abstraction for two processes sending and receiving data on the internet. Also it provides ports to allow differentiation for communication. As a client, you need to specify 

**Question 4** - What is the difference between SMTP and HTTP?

**Solution 4**: SMTP is used to transmit email messages and HTTP is used to download web content

**Question 5** - What is the difference between an IP address and a domain name?

**Solution 5**: Domain names, through DNS, allows you to enter a more familiar string and convert it to an IP address. So they share the same idea, but IP is a number while the domain name is a string. 

**Question 6** - How does the operating system use ports?

**Solution 6**: "The ports allows the operating system differentiate traffic for each application."

**Question 7** - Write code that creates a socket connection to ip address `123.45.678.900` at port `4040`. Then, print a color to that socket’s output.

**Solution 7**: 

```java
public class ColorSocket {
    public static void main (String args[]) {
        Socket sock = null;
        try {
            sock = new Socket ("123.45.678.900", 4040);
        } catch (Exception e) {
            System.err.println ("Cannot Connect");
            System.exit(1);
        }

        try {
            PrintWriter pw = new PrintWriter(sock.getOutputStream());
            pw.println("Blue");
            pw.close(); 
            sock.close();
        }catch(Exception e){
            System.err.print("IOException");
            System.exit(1);
        }
    }
}
```

**Question 8** - What is the difference between a socket’s input stream and its output stream?

**Solution 8**: The output stream is what is shown to the client. The input stream is what the client can input, for example a response. 

**Question 9** - What is the difference between a `Socket` and a `SocketServer`?

**Solution 9**: The Socket works with the client side and the ServerSocket works with the server side. The ServerSocket accepts Sockets that are attempting to connect to it. 

**Question 10** - How are threads useful with servers? How does a server manage to always be listening for sockets trying to connect?

**Solution 10**: Threads are useful for servers because a complex server will expect multiple connections while running a complex program. The server manages to listed for sockets trying to connect because the server is running as a main thread. This means that while the server is helping with one user through one thread, if another user wants to connect, the main thread can create a thread for this new user so the system runs seamlessly. 