 **What  are  the  `features` in JAVA?**
 -   Object-oriented
 -   Platform  independent:
 -   Multi-threaded

 **What  are  the Java `IDE’s`?**
 - Eclipse
 -    NetBeans

 **What  is  meant  by  `Local variable` and `Instance variable`?**

 - Local variables  are  defined in the  method 
 -  An instance variable is  defined  inside  the  class

**What  are  the  `Oops  concepts`?**

-   Inheritance    
-   Encapsulation
-   Polymorphism 
-   Abstraction
-   Interface

 **What  is  `Inheritance`?**

 - Existing  class  is  known  as Super class   
 - the  derived  class  is known  as a sub  class.
 - 

    public  class  Manupulation{
    
    }
    
    public  class  Addition extends  Manipulation{
    
    }

**Inheritance  is  applicable  for  public and protected  members  only. Private members  can’t  be  inherited.**

 **What  is  `Encapsulation`?**

 `Purpose of  Encapsulation`:
-   Protects  the code from  others.
-   Code maintainability.

 public  class  Addition(){
    private  int  a = 5; //Here the variable is  marked  as private
   }

**For  encapsulation, we  need  to  make all the  instance variables as private and create  setter and getter  for  those variables.** 

**What  is  `Polymorphism`?**


    public class Manipulation{ //Super class 
    
        public void add(){ 
        System.out.println("super class ");
        } 
    }
    public class Addition extends Manipulation{ // Sub class 
    
        public void add(){ 
         System.out.println("sub class");
        }
    }


    Manipulation manipulation = new Manipulation();
    Manipulation addition = new Addition();
    manipulation.add();
    addition.add(); 

results :

    super class 
    sub class

Polymorphism  is  applicable  for overriding and not for overloading.

 **What  is  meant  by `Method Overriding`?**

-   Method `name`  should  be same
-   `Argument` should  be same
-   `Return` type also should  be same
    
**What  is  meant  by  `Overloading`?**

-   `Same` method  `name`
-   `Different argument` type
-   May have `different return`  types



 public class Manipulation{ //Super class
        public void add(String name){ }
    }

public class Addition extends Manipulation{

public void add(){}
public void add(int a){}

public static void main(String args[]){
     Addition addition = new Addition();
      addition.add();
    } 
} 
    
 **What  is  meant  by `Interface`?**
methods : public  abstract  void
variables : public  static final

    Public abstract  interface  IManupulation{ 
    Public abstract  void  add();
    public  abstract  void  subtract();
    }




    public  class  Manupulation implements  IManupulation{ 
    
    Public void  add(){
    }
    Public void  subtract(){
    }
    
    }

**What  is  meant  by `Abstract class`?**

    public  abstract  class  Manupulation{
    
    public  abstract  void  add();//Abstract method  declaration
    
    Public void  subtract(){
    
    }
    }

-   An abstract  class  `may  have a Non- abstract  method` also.
   
-   The concrete  Subclass  which  extends  the Abstract class  should  provide  the  implementation  for  abstract  methods.

**Difference  between Array and Array List.**

**Size** should  be  given at the time of  array  declaration.  
  
String[] name = new String[2]
name[1] = “book” **//with index**

**Size** may not be  required. It  changes  the  `size  dynamically`.  
  
ArrayList  name = new  ArrayList
name.add(“book”) **//no index**

**Difference  between `String`, `String Builder`, and `String Buffer`.**

**String:** 
String variables are  stored in “constant  string pool”. Once  the  string  reference  changes  **`the  old  value  that  exists in the “constant  string pool”, it  cannot  be  erased.`**
  
**String Buffer**
Here string  values  are  stored in a stack. If  the  values  are  changed  then  the  new  value  replaces  the  older  value.

**String Builder**
This is same as String Buffer except  for  the String Builder  which  is not threaded  safety  that  is not synchronized. So obviously  performance  is fast.

Difference  between  HashMap and HashTable.
Difference  between  HashSet and TreeSet.

**What  is  mean  by  `Exception`?**

Ans: An Exception  is a problem  that  can  occur  `during  the normal flow  of an execution.`
Exceptions  are a subclass  of  `java.lang.Exception`.

    try{
    
    //Risky  codes  are  surrounded  by  this block
    
    }catch(Exception e){
    
    //Exceptions  are  caught in catch block
    
    }

**What  are  the  types  of  Exceptions?**


**Checked  Exception:**
These exceptions  `are  checked  by  the  compiler at the time of  compilation`. 
E.g. ClassNotFound  Exception

**Unchecked  Exception:**
These exceptions  `are not checked  during  the  compile time by  the  compiler`. 

It  includes:
-   **Arithmetic**  Exception
-   **ArrayIndexOutOfBounds**  Exception

**What  are  the different `ways`  to handle exceptions?**

 **Using  try/catch:**

A risky code is  surrounded  by  try  block. If an exception  occurs, then  it  is  caught  by  the catch block  which  is  followed  by  the  try  block.

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

**By declaring  throws  keyword:**

At the  end  of  the  method, we  can  declare  the  exception  using  throws  keyword.

    class  Manipulation{
    
    public  static  void  main(String[] args){
    add();
    }
    
    public  void  add() throws  Exception{
    addition();
    }
    }

 **What  are  Exception  handling  keywords in Java?**

**try:**

When a risky code is  surrounded  by a try  block. An exception  occurring in the  try  block  is  caught  by a catch block.

**catch:**

This is  followed  by  try  block. Exceptions  are  caught  here.

**finally:**

This is  followed  either  by  try  block (or) catch block. This block  gets  executed  regardless  of an exception. `So generally clean up  codes  are  provided  here.`

 **Explain  about  Exception Propagation.**


    public  class  Manipulation{
    public  static  void  main(String[] args){
    add();
    }
    public  void  add(){
    addition();
    }

**`If an exception  occurred in the addition() method  is not caught, then  it  moves  to  the  method add(). Then  it  is  moved  to  the main() method and then  it will stop  the  flow  of  execution.`** It  is  called  Exception Propagation.

**What  is  the  final  keyword in Java?**

    Final variable

Once a variable is  declared  as final, **then  the  value  of  the variable could not be  changed. It  is like a constant.**

final int = 12;

    Final method:

**A final keyword in a method  that  couldn’t  be  overridden**. If a method  is  marked  as a final, then  it  can’t  be  overridden  by  the  subclass.

    Final class:

**If a class  is  declared  as final, then  the  class  couldn’t  be  subclassed**. No  class  can  extend  the  final  class.

 **What  is a `Thread`?**

Ans: In Java, the  flow  of a execution  is  called Thread. Every java  program  has at least one  thread  called  main  thread, the Main thread  is  created  by JVM.

 **How do you  make a `thread` in Java?**

**Extend Thread class:**

**Extending a Thread class and override  the  run  method**. The thread  is  available in java.lang.thread.


    Public class  Addition extends  Thread {
    
    public  void  run () {
    }
    
    }

**The disadvantage  of  using a thread  class  is  that  we  cannot  extend  any  other  classes  because  we  have  already  extend  the  thread  class**. 

**Implement Runnable interface:**

    Public class  Addition implements  Runnable {
    
    public  void  run () {
    
    }
    }

 **Explain  about  join () method.**

 Join () method  is  used  to  join  one  thread  with  the  end  of  the  currently  running  thread.

    public  static  void  main (String[] args){
    
    Thread t = new  Thread ();
    t.start ();
    t.join ();
    
    }
    }

**Difference  between  `notify()` method and `notifyAll()` method in Java.**

**`notify()`**
This method  is  used  to send a signal  to  wake  up a single  thread in the  waiting pool.
**`notifyAll()`**
This method  sends  the  signal  to  wake  up all the  threads in a waiting spool.

**When  to  use  Runnable interface Vs Thread class in Java?**

Ans: If  we  need  our  class  to  extend  some  other  classes  other  than  the  thread  then  we  can  go  with  the  runnable interface because in java  we  can  extend  only  one  class.

If  we  are not going  to  extend  any  class  then  we  can  extend  the  thread  class.

**Difference  between  start() and run() method  of  thread  class.**

 Start() method  creates  new  thread and the code inside  the  run () method  is  executed in the  new  thread.

**What  is `Multi-threading`?**

Multiple threads  are  executed  simultaneously.

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

 **Explain  thread  life  cycle in Java.**

-   New
-   Runnable
-   Running 
-   Non-runnable (Blocked)
-   Terminated

**What  is  Synchronization?**

Ans: Synchronization  makes  only  **`one  thread  to  access a block  of code at a time.`**

    public  class  ExampleThread  implements  Runnable{ 
    
    public  static  void  main (String[] args){
     Thread t = new Thread ();
      t.start ();
       } 
      
      public  void  run(){ 
      synchronized(object){ {
      
       }
       }



 **What  is  meant  by  `Serialization`?**

Ans: Converting a file  into a byte stream is  known  as  Serialization. The objects in the  file  is  converted  to  the  bytes  for  security  purposes. **For  this, we  need  to  implement  java.io.Serializable interface.** It  has  no  method  to  define.

 **Which  methods  are  used  during  `Serialization` and `Deserialization`  process?**

Ans: ObjectOutputStream and ObjectInputStream  classes  are  higher  level java.io. package. 

`ObjectOutputStream.writeObject` —->Serialize  the  object and write  the  serialized  object  to a file.

`ObjectInputStream.readObject` —> Reads the  file and deserializes  the  object.

**To  be  serialized, an object must implement  the  serializable interface.**

 **Difference  between  `Serialization` and `Deserialization` in Java.**

Serialization  is  the  process  which  **is  used  to  convert  the  objects  into  byte stream**

Deserialization  **is  the  opposite  process  of  serialization  where  we  can  get  the  objects back from  the  byte stream**.

 **What  is  `SerialVersionUID`?**
Ans: Whenever an object  is  Serialized, the  object  is  stamped  with a version ID number  for  the  object  class. This ID is  called  the  SerialVersionUID. 

 **What's the purpose of Static methods and static variables?**
When there is a requirement to **share a method or a variable between multiple objects of a class**


**What is ternary operator? Give an example.**

    public class conditionTest  { 
    public static void main(String args[]) { 
    String status;
    int rank = 3; 
     
     status = (rank == 1) ? "Done" : "Pending"; 
     
     System.out.println(status); 
     }}

**How can you generate random numbers in Java?**

-   Using Math.random() you can generate **`random numbers in the range greater than or equal to 0.1 and less than 1.0`**
-   Using Random class in package  java.util


**What's the base class in Java from which all classes are derived?**

     java.lang.object

**How can we pass argument to a function by reference instead of pass by value?**

 In java, we can pass argument to a function only by value and not by reference.

 **Is there any way to skip Finally block of exception even if some exception occurs in the exception block?**

System.exit(0);

**Can a class have multiple constructors?**

Ans: Yes, a class can have multiple constructors with different parameters.

Q29. Can we override static methods of a class?

Ans: We cannot override static methods. **`Static methods belong to a class and not to individual objects and are resolved at the time of compilation (not at runtime).`**

    public class superclass { 
    public void displayResult() { 
    system.out.println("Printing from superclass"); 
    }}
    
    public class subclass extends superclass { 
    public void displayResult() { 
    system.out.println("Displaying from subClass"); 
    super.displayResult(); 
    } 
    
    public static void main(String args[]) { 
    subclass obj = new subclass(); 
    obj.displayResult(); 
    }}

Ans: Output will be:

    Displaying from subclass
    
    Displaying from superclass

 **Is String a data type in java?**

String is not a primitive data type in java. **`When a string is created in java, it's actually an object of Java.Lang.`** 


 **Why Strings in Java are called as Immutable?**

In java, string objects are called immutable as once value has been assigned to a string, **`it can't be changed and if changed, a new object is created`**.

In below example, reference str refers to a string object having value "Value one".

    String str="Value One";

When a new value is assigned to it, a new String object **gets created and the reference is moved to the new object.**

    str="New Value";

**How garbage collection is done in Java?**

Ans: In java, when `an object is not referenced any more, garbage collection takes place and the object is destroyed automatically.`
For automatic garbage collection java calls either System.gc() method or Runtime.gc() method.

 **Can a class be a super class and a sub-class at the same time?** 

**`If there is a hierarchy of inheritance used`**, a class can be a super class for another class and a sub-class for another one at the same time.

    public class world {..........}
    public class continenet extends world {............}
    public class country extends continent {......................}


 **How objects of a class are created if no constructor is defined in the class?**

Ans: Even if no explicit constructor is defined in a java class, **`objects get created successfully as a default constructor is implicitly used`** for object creation. This constructor has no parameters.

 **What's difference between Stack and Queue?**

**stack** is based on Last in First out (LIFO) 
**queue** is based on FIFO (First In First Out) principle.

**In java, how we can `disallow serialization` of variables?**

we can use the keyword `transient` while declaring them. 

    public class transientExample  { 
    private transient trans_var; 
     }

**What will be the output of following piece of code?**

    public class operatorExample  {
    
    public static void main(String args[]) {
    
    int x = 4;
    
    system.out.println(x++);
    }}

 **In this case postfix ++ operator is used which `first returns the value and then increments`. Hence  it's output will be 4.**

 **What are the two `environment variables` that must be set in order to run any Java programs**

1.  PATH variable
2.  CLASSPATH variable

 **What will be the output of Round(3.7) and Ceil(3.7)?**

 Round(3.7) returns 4 and Ceil(3.7) returns 4.

 **Is the following class declaration correct?**

    public abstract final class testClass {
    // Class methods and variables
    }

 **`The above class declaration is incorrect as an abstract class can't be declared as Final.`**

 **What's the difference between comparison done by equals method and == operator?**

***In Java, equals() method is used to compare the contents of two string objects and returns true if the two have same value while == operator compares the references of two string objects.***



    public class equalsTest {
    
    public static void main(String args[]) {
    
    String str1 = new String("Hello World");
    
    String str2 = new String("Hello World");
    
    if (str1.equals(str2)) {
    
    // this condition is true
    
    System.out.println("str1 and str2 are equal in terms of values"); }
    
    if (str1 == str2) {
    
    //This condition is true
    
    System.out.println("Both strings are referencing same object");
    
    } else {
    
    // This condition is NOT true
    
    System.out.println("Both strings are referencing different objects");
    
    } }}

 **I want my class to be developed in such a way that no other class (even derived class) can create its objects. How can I do so?**

 **`If we declare the constructor of a class as private,`** it will not be accessible by any other class  and hence, no other class will be able to instantiate it and formation of its object will be limited to itself only.

 **How can an exception be thrown manually by a programmer?**

 In order to throw an exception in a block of code manually, throw keyword is used. Then this exception is caught and handled in the catch block.

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

 **How objects are stored in Java?**

 In java, each object when created **`gets a memory space from a heap`**. 

 **I have multiple constructors defined in a class. Is it possible to call a constructor from another constructor's body?**

, it's possibl**`e to call one constructor from the body of another one using this().`**


 **Can we use different return types for methods when overridden?**



    Class B extends A {
    
    A method(int x) {
    
    //original method }
    
    B method(int x) {
    
    //overridden method
    
    }}

**What's the base class of all exception classes?**

Ans: In Java, Java.lang.Throwable

 **What's the order of call of constructors in inheritiance?**

Ans: In case of inheritance, first the constructor of the super class is invoked and then the constructor of the derived class is invoked.

## Collections

**Iterator --> Collections**

**Collections --> List, Queue, Dequeue, Set, SortedSet**
**List --> ArrayList, Vector, LinkedList**

## ArrayList

    ArrayList<String> list=new ArrayList<String>();
    list.add("Ravi");  
    list.add("Vijay");  
    list.add("Ravi");  
    list.add("Ajay");  
     
    Iterator itr=list.iterator();  
    while(itr.hasNext()){  
    System.out.println(itr.next());  
    }  

## Vector

Vector uses a dynamic array to store the data elements. It is similar to ArrayList. However, **It is synchronized and contains many methods that are not the part of Collection framework.**

## LinkedList

 **It can store the duplicate elements. It maintains the insertion order and is not synchronized.** In LinkedList, the manipulation is fast because no shifting is required.

    LinkedList ll = new LinkedList();
          
          // add elements to the linked list
          ll.add("F");
          ll.add("B");
          ll.add("D");
          ll.add("E");
          ll.add("C");
          ll.addLast("Z");
          ll.addFirst("A");
          ll.add(1, "A2");

## Stack

The stack is the subclass of Vector. It implements the last-in-first-out data structure, i.e., 
 

    Stack<String> stack = new Stack<String>();  
    stack.push("Ayush");  
    stack.push("Garvit");  
    stack.push("Amit");  
    stack.push("Ashish");  
    stack.push("Garima");  
    stack.pop();  
    Iterator<String> itr=stack.iterator();  
    while(itr.hasNext()){  
    System.out.println(itr.next());  
    }  

 


**Queue --> PriorityQueue**


## PriorityQueue

The PriorityQueue class implements the Queue interface. **It holds the elements or objects which are to be processed by their priorities.** PriorityQueue doesn't allow null values to be stored in the queue.


    PriorityQueue<String> queue=new PriorityQueue<String>();  
    queue.add("Amit Sharma");  
    queue.add("Vijay Raj");  
    queue.add("JaiShankar");  
    queue.add("Raj");  
    System.out.println("head:"+queue.element());  
    System.out.println("head:"+queue.peek());  
    System.out.println("iterating the queue elements:");  
    Iterator itr=queue.iterator();  
    while(itr.hasNext()){  
    System.out.println(itr.next());  
    }  
    queue.remove();  
    queue.poll();  
    System.out.println("after removing two elements:");  
    Iterator<String> itr2=queue.iterator();  
    
    while(itr2.hasNext()){  
    System.out.println(itr2.next());  
    }  



**Set --> LinkedHashSet, HashSet**
Set Interface in Java is present in java.util package. It extends the Collection interface. ***It represents the unordered set of elements which doesn't allow us to store the duplicate items.*** We can store at most one null value in Set. Set is implemented by HashSet, LinkedHashSet, and TreeSet.

## HashSet

HashSet class implements Set Interface. It represents the collection that uses a hash table for storage. Hashing is used to store the elements in the HashSet. It contains unique items.

    HashSet<String> set=new HashSet<String>();  
    set.add("Ravi");  
    set.add("Vijay");  
    set.add("Ravi");  
    set.add("Ajay");  
    //Traversing elements  
    Iterator<String> itr=set.iterator();  
    while(itr.hasNext()){  
    System.out.println(itr.next());  
    }  

**SortedSet --> TreeSet**

## TreeSet

Java TreeSet class implements the Set interface that uses a tree for storage. **Like HashSet, TreeSet also contains unique elements.** However, the access and retrieval time of TreeSet is quite fast. The elements in TreeSet stored in ascending order.

**Map --> HashMap, LinkedHashMap, TreeMap**
A map contains values on the basis of key, i.e. key and value pair. Each key and value pair is known as an entry. A Map contains unique keys.



**HashMap** HashMap is the implementation of Map, **but it doesn't maintain any order.**
**LinkedHashMap**   LinkedHashMap is the implementation of Map. It inherits HashMap class. **It maintains insertion order.**
**TreeMap** TreeMap is the implementation of Map and SortedMap. **It maintains ascending order.**

    Map<Integer,String> map=new HashMap<Integer,String>();  
      map.put(100,"Amit");  
      map.put(101,"Vijay");  
      map.put(102,"Rahul");  
      //Elements can traverse in any order  
      for(Map.Entry m:map.entrySet()){  
       System.out.println(m.getKey()+" "+m.getValue());  
      }  
## Java LocalDate Example


    LocalDate date = LocalDate.now();
    LocalDate yesterday = date.minusDays(1);
    LocalDate tomorrow = yesterday.plusDays(2);
    System.out.println("Today date: "+date);
    System.out.println("Yesterday date: "+yesterday);
    System.out.println("Tommorow date: "+tomorrow);

## Java LocalTime Example: now()

    LocalTime time = LocalTime.now();
    System.out.println(time);