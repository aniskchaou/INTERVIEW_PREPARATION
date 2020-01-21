
## **ByteStream**
Java byte streams are used to perform input and output of 8-bit bytes.

 

## CharacterStream
 Java Character streams are used to perform input and output for 16-bit unicode.
Though there are many classes related to character streams 
 - FileReader
 - FileWriter

.

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


    OutputStream f1 = new FileOutputStream("C:/java/hello") ;
    
        File f = new File("C:/java/hello");
        
        OutputStream f2 = new FileOutputStream(f);

## Socket

The java.net package of the J2SE APIs contains a collection of classes and interfaces that provide


**Sockets provide the communication mechanism between two computers using TCP.**


**client**

    Socket client =  new  Socket(serverName, port);

**Server**

    serverSocket =  new  ServerSocket(port);
