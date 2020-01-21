## **ByteStream and CharacterStream**
Java byte streams are used to perform input and output of 8-bit bytes.
Though there are many classes related to byte streams but the most frequently used classes are,
whereas Java Character streams are used to perform input and output for 16-bit unicode.
Though there are many classes related to character streams but the most frequently used classes are,
FileReader and FileWriter.

## Directories

    String dirname = "/tmp/user/java/bin";
    
    File d = new File(dirname);
    
    // Create directory now.
    
    d.mkdirs();

## FileInputStream

 constructor takes a file name as a string to create an input stream object to read the file −

    InputStream f = new FileInputStream("C:/java/hello");
    File file = new File("C:/java/hello");
    
    InputStream fis = new FileInputStream(file);

## FileOutputStream

FileOutputStream is used to create a file and write data into it. The stream would create a file,

if it doesn't already exist, before opening it for output.

Following constructor takes a file name as a string to create an input stream object to write the file −

OutputStream f1 = new FileOutputStream("C:/java/hello") ;

    File f = new File("C:/java/hello");
    
    OutputStream f2 = new FileOutputStream(f);

## socket

The java.net package of the J2SE APIs contains a collection of classes and interfaces that provide


**Sockets provide the communication mechanism between two computers using TCP.**
A client program creates a socket on its end of the communication and attempts to connect that socket to a server.
When the connection is made, the server creates a socket object on its end of the communication.
The client and the server can now communicate by writing to and reading from the socket.

**client**

    Socket client =  new  Socket(serverName, port);

**Server**

    serverSocket =  new  ServerSocket(port);
