## **What is mean by `Exception`?**

Ans: An Exception is a problem that can occur  `during the normal flow of an execution.`  Exceptions are a subclass of  `java.lang.Exception`.

```
try{

//Risky  codes  are  surrounded  by  this block

}catch(Exception e){

//Exceptions  are  caught in catch block

}

```

## **What are the types of Exceptions?**

**Checked Exception:**  These exceptions  `are checked by the compiler at the time of compilation`. E.g. ClassNotFound Exception

**Unchecked Exception:**  These exceptions  `are not checked during the compile time by the compiler`.

It includes:

-   **Arithmetic**  Exception
-   **ArrayIndexOutOfBounds**  Exception

## **What are the different `ways` to handle exceptions?**

**Using try/catch:**

A risky code is surrounded by try block. If an exception occurs, then it is caught by the catch block which is followed by the try block.

```
class  Manipulation{

public  static  void  main(String[] args){
add();
}

Public void  add(){
    try{
    addition();
    }catch(Exception e){
    e.printStacktrace();
    }
}

}

```

**By declaring throws keyword:**

At the end of the method, we can declare the exception using throws keyword.

```
class  Manipulation{

public  static  void  main(String[] args){
add();
}

public  void  add() throws  Exception{
addition();
}
}

```

## **What are Exception handling keywords in Java?**

**try:**

When a risky code is surrounded by a try block. An exception occurring in the try block is caught by a catch block.

**catch:**

This is followed by try block. Exceptions are caught here.

**finally:**

This is followed either by try block (or) catch block. This block gets executed regardless of an exception.  `So generally clean up codes are provided here.`

## **Explain about Exception Propagation.**

```
public  class  Manipulation{
public  static  void  main(String[] args){
add();
}
public  void  add(){
addition();
}

```

**`If an exception occurred in the addition() method is not caught, then it moves to the method add(). Then it is moved to the main() method and then it will stop the flow of execution.`**  It is called Exception Propagation.

## **What is a `Thread`?**

Ans: In Java, the flow of a execution is called Thread. Every java program has at least one thread called main thread, the Main thread is created by JVM.

## **How do you make a `thread` in Java?**

**Extend Thread class:**

**Extending a Thread class and override the run method**. The thread is available in java.lang.thread.

```
Public class  Addition extends  Thread {

public  void  run () {
}

}

```

**The disadvantage of using a thread class is that we cannot extend any other classes because we have already extend the thread class**.

**Implement Runnable interface:**

```
Public class  Addition implements  Runnable {

public  void  run () {

}
}

```

## **Explain about join () method.**

Join () method is used to join one thread with the end of the currently running thread.

```
public  static  void  main (String[] args){

Thread t = new  Thread ();
t.start ();
t.join ();

}
}

```

## **Difference between `notify()` method and `notifyAll()` method in Java.**

**`notify()`**  This method is used to send a signal to wake up a single thread in the waiting pool.  **`notifyAll()`**  This method sends the signal to wake up all the threads in a waiting spool.

## **When to use Runnable interface Vs Thread class in Java?**

Ans: If we need our class to extend some other classes other than the thread then we can go with the runnable interface because in java we can extend only one class.

If we are not going to extend any class then we can extend the thread class.

## **Difference between start() and run() method of thread class.**

Start() method creates new thread and the code inside the run () method is executed in the new thread.

## **What is `Multi-threading`?**

Multiple threads are executed simultaneously.

```
public  class  MultipleThreads implements  Runnable
{

public  static  void  main (String[] args){

Runnable r = new  runnable ();
Thread t=new  thread ();
t.start ();//User thread  starts  here
Addition add=new  addition ();
}

public  void  run(){
go();
}
}

```

## **Explain thread life cycle in Java.**

-   New
-   Runnable
-   Running
-   Non-runnable (Blocked)
-   Terminated

## **What is Synchronization?**

Ans: Synchronization makes only  **`one thread to access a block of code at a time.`**

```
public  class  ExampleThread  implements  Runnable{ 

public  static  void  main (String[] args){
 Thread t = new Thread ();
  t.start ();
   } 
  
  public  void  run(){ 
  synchronized(object){ {
  
   }
   }

```

## **What is meant by `Serialization`?**

Ans: Converting a file into a byte stream is known as Serialization. The objects in the file is converted to the bytes for security purposes.  **For this, we need to implement java.io.Serializable interface.**  It has no method to define.

## **Which methods are used during `Serialization` and `Deserialization` process?**

Ans: ObjectOutputStream and ObjectInputStream classes are higher level java.io. package.

`ObjectOutputStream.writeObject`  —->Serialize the object and write the serialized object to a file.

`ObjectInputStream.readObject`  —> Reads the file and deserializes the object.

**To be serialized, an object must implement the serializable interface.**

## **Difference between `Serialization` and `Deserialization` in Java.**

Serialization is the process which  **is used to convert the objects into byte stream**

Deserialization  **is the opposite process of serialization where we can get the objects back from the byte stream**.

## **What is `SerialVersionUID`?**

  Ans: Whenever an object is Serialized, the object is stamped with a version ID number for the object class. This ID is called the SerialVersionUID.

## **What's the purpose of Static methods and static variables?**

  When there is a requirement to  **share a method or a variable between multiple objects of a class**

## **How can we pass argument to a function by reference instead of pass by value?**

In java, we can pass argument to a function only by value and not by reference.

## **Is there any way to skip Finally block of exception even if some exception occurs in the exception block?**

System.exit(0);

## **Can a class have multiple constructors?**

Ans: Yes, a class can have multiple constructors with different parameters.


## **What's difference between Stack and Queue?**

**stack**  is based on Last in First out (LIFO)  **queue**  is based on FIFO (First In First Out) principle.

## **In java, how we can `disallow serialization` of variables?**

we can use the keyword  `transient`  while declaring them.

```
public class transientExample  { 
private transient trans_var; 
 }

```
## **What will be the output of Round(3.7) and Ceil(3.7)?**

Round(3.7) returns 4 and Ceil(3.7) returns 4.

## **Is the following class declaration correct?**

```
public abstract final class testClass {
// Class methods and variables
}

```

**`The above class declaration is incorrect as an abstract class can't be declared as Final.`**


## **How can an exception be thrown manually by a programmer?**

In order to throw an exception in a block of code manually, throw keyword is used. Then this exception is caught and handled in the catch block.

```
public void topMethod() { 
    try {
     excMethod();
      }catch (ManualException e) {
    }
}

public void excMethod { 
String name = null; 
if (name == null) { 
throw (new ManualException("Exception thrown manually "); 
}

```
## Java LocalDate Example

```
LocalDate date = LocalDate.now();
LocalDate yesterday = date.minusDays(1);
LocalDate tomorrow = yesterday.plusDays(2);
System.out.println("Today date: "+date);
System.out.println("Yesterday date: "+yesterday);
System.out.println("Tommorow date: "+tomorrow);

```

## Java LocalTime Example: now()

    ```
    
        LocalTime time = LocalTime.now();
        System.out.println(time);
        ```
        ## **GenericMethods**
        public static < E> void printArray(E[] inputArray) {
        
        // Display array elements
        
        for (E element : inputArray) {
        
        System.out.printf("%s ", element);
        
        }
        
        System.out.println();
        
        }
        
        Integer[] intArray = {1, 2, 3, 4, 5};
        
        Double[] doubleArray = {1.1, 2.2, 3.3, 4.4};
        
        Character[] charArray = {'H', 'E', 'L', 'L', 'O'};

## GenericCLassTutorial

    public class GenericCLassTutorial<T> {
    
    //As with generic methods, the type parameter section of a generic class can
    
    //have one or more type parameters separated by commas.
    
    private T t;
    
    public void add(T t) {
    
    this.t = t;
    
    }
    
    public T get() {
    
    return t;
    
    }
    
    public static void main(String[] args) {
    
    GenericCLassTutorial<Integer> integerBox = new GenericCLassTutorial<Integer>();
    
    GenericCLassTutorial<String> stringBox = new GenericCLassTutorial<String>();
    
    integerBox.add(new Integer(10));
    
    stringBox.add(new String("Hello World"));
    }


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
