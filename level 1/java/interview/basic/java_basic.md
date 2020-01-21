## 6) How many types of memory areas are allocated by JVM?

**Heap:** It is the runtime data area in which ***the memory is allocated to the objects***

**Stack:** Java Stack stores frames. ***It holds local variables and partial results, and plays a part in method invocation and return.*** 

## 7) What is JIT compiler?

Just-In-Time(JIT) compiler: It is used to improve the performance. ***JIT compiles parts of the bytecode that have similar functionality at the same time***, and hence reduces the amount of time needed for compilation. 

## 12) Is Empty .java file name a valid source file name?

Yes, Java allows to save our java file by .java only, we need to compile it by javac .java and run by java classname Let's take a simple example:

    //save by .java only  
    class A{  
    public static void main(String args[]){  
    System.out.println("Hello java");  
    }  
    }  
    //compile by javac .java  
    //run by     java A  


## 14) If I don't provide any arguments on the command line, then what will the value stored in the String array passed into the main() method, empty or NULL?

It is empty, but not null.

    public static void main(String[] args) {
           if(args.length==0)
           {
               System.out.println(args.toString());
           }
                     
        }

## 15) What if I write static public void instead of public static void?

The program compiles and runs correctly because ***the order of specifiers doesn't matter in Java.***

## 16) What is the default value of the local variables?

The local variables are not initialized to any default value, ***neither primitives nor object references.***


## 18) What is the purpose of static methods and variables?

static is used in the case, where ***we need to define variables or methods which are common to all the objects of the class.***

*For example, In the class simulating the collection of the students in a college, the name of the college is the common attribute to all the students. Therefore, the college name will be defined as static.*

## 19) What are the advantages of Packages in Java?

Packages ***avoid the name clashes.***
We can also have the hidden classes **that are not visible outside and used by the package.**
It is easier to locate the related classes.

## 20) What is the output of the following Java program?

    class Test   
    {  
        public static void main (String args[])   
        {  
            System.out.println(10 + 20 + "Javatpoint");   
            System.out.println("Javatpoint" + 10 + 20);  
        }  
    }  

The output of the above code will be

    30Javatpoint
    Javatpoint1020


## 21) What is the output of the following Java program?

    class Test   
    {  
        public static void main (String args[])   
        {  
            System.out.println(10 * 20 + "Javatpoint");   
            System.out.println("Javatpoint" + 10 * 20);  
        }  
    }  

The output of the above code will be

    200Javatpoint
    Javatpoint200
## 22) What is the output of the following Java program?

    class Test   
    {  
        public static void main (String args[])   
        {  
            for(int i=0; 0; i++)   
            {  
                System.out.println("Hello Javatpoint");  
            }  
        }  
    }  

**The above code will give the compile-time error because the for loop demands a boolean value in the second part and we are providing an integer value, i.e., 0**.

## What is typecasting?

**Widening (automatically)** - conversion of a smaller data type to a larger data type size.

`byte -> short -> char -> int -> long -> float -> double`

**Narrowing (manually)** - converting a larger type to a smaller size type

`double -> float -> long -> int -> char -> short -> byte`

## What are the default values and sizes of primitive data types?


**int** 0

**char**  ‘u0000’

**byte** 0

**short** 0

**long** 0L

**float** 0.0f

**double** 0.0d

**boolean**  false


## What are non-primitive data types?

 String, arrays, and structures.
## Is there any default value for local variables?

**Ans:**  No, local variables are not initialized by any default values.

## What is the role of the unary operator in Java?


    `class UnaryExample{`
    
    `public static void main(String args[]){`
    
    `int x=15;`
    
    `System.out.println(x++);``//15 (16)`
    
    `System.out.println(++x);``//17`
    
    `System.out.println(x--);``//12 (16)`
    
    `System.out.println(--x);``//15`
    
    `}}`

## What is a ternary operator?

**Ans:** Ternary operator in Java is used to replace if-else statement. The representation or the syntax for the ternary operator is given as:

`variable= (expression) ? expression` `true` `: expression` `false`

## 228) Write a Java program that prints all the values given at command-line.

Program

    class A{  
    public static void main(String args[]){  
      
    for(int i=0;i<args.length;i++)  
    System.out.println(args[i]);  
      
    }  
    }

  
compile by > javac A.java  
run by > java A sonoo jaiswal 1 3 abc  
Output

    sonoo
    jaiswal
    1
    3
    abc   

   


## 237) What is Locale?

A Locale object represents a specific geographical, political, or cultural region. This object can be used to get the locale-specific information such as country name, language, variant, etc.

    import java.util.*;  
    public class LocaleExample {  
    public static void main(String[] args) {  
   
    Locale locale=Locale.getDefault();  
    //Locale locale=new Locale("fr","fr");//for the specific locale  
      
    System.out.println(locale.getDisplayCountry());  
    System.out.println(locale.getDisplayLanguage());  
    System.out.println(locale.getDisplayName());  
    System.out.println(locale.getISO3Country());  
    System.out.println(locale.getISO3Language());  
    System.out.println(locale.getLanguage());  
    System.out.println(locale.getCountry());  
          
    }  
    }  

Output:

    United States
    English
    English (United States)
    USA
    eng
    en
    US
## What is an infinite Loop? How infinite loop is declared?

Ans: An infinite loop runs without any condition and runs infinitely. 

    for (;;)
    {
        // Statements to execute
    
        // Add any loop breaking logic
    }

## What are Wrapper classes?
    
Java wrapper classes are the Object representation of eight primitive types in java. **All the wrapper classes in java are immutable and final.** Java 5 autoboxing and unboxing allows easy conversion between primitive types and their corresponding wrapper classes.


    
## What is Enum in Java?

    
  Enum was introduced in Java 1.5 as a new type whose fields consists of fixed set of constants. For example, in Java we can create Direction as enum with fixed fields as EAST, WEST, NORTH, SOUTH.
  
 **Enum constants are implicitly static and final.** 
## What is Java Annotations?

Java Annotations provide information about the code and they have no direct effect on the code they annotate. Annotations are introduced in Java 5. 

## How to run a JAR file through command prompt?

We can run a jar file using java command but it requires Main-Class entry in jar manifest file. Main-Class is the entry point of the jar and used by java command to execute the class.
## What is instanceof keyword?

We can use instanceof keyword to check if an object belongs to a class or not. We should avoid it’s usage as much as possible. Sample usage is:

```

public static void main(String args[]){
  Object str = new String("abc");
    
  if(str instanceof String){
    System.out.println("String value:"+str);
  }
    
  if(str instanceof Integer){
    System.out.println("Integer value:"+str);
  }
}

```
## 106) What is Java instanceOf operator?

The instanceof in Java is also known as type comparison operator because it **compares the instance with type**. It returns either true or false. 

    class Simple1{  
     public static void main(String args[]){  
     Simple1 s=new Simple1();  
     System.out.println(s instanceof Simple1);//true  
     }  
    }  


Output

    true
## Is there a way to increase the size of an array after its declaration?

Ans: Arrays are static and once we have specified its size, we can't change it. 


## Can we cast any other type to Boolean Type with type casting?

Ans: No, we can neither cast any other primitive type to Boolean data type nor can cast Boolean data type to any other primitive data type.

## How does Autoboxing of Integer work in Java?

hint: By using the `valueOf()` method in Java.

## Difference between** `**Comparator**` **and** `**Comparable**` **in Java?

  
hint: `Comparator` defines custom ordering while `Comparable` defines the natural order of objects, e.g. the alphabetic order for `String`. 


## What is Marker interface?
    
A marker interface is an empty interface without any method **but used to force some functionality in implementing classes by Java.** Some of the well known marker interfaces are Serializable and Cloneable.
    

## 180) What is gc()?

The gc() method is used to invoke the garbage collector for cleanup processing. This method is found in System and Runtime classes. 

    public class TestGarbage1{  
     public void finalize(){System.out.println("object is garbage collected");}  
     public static void main(String args[]){  
      TestGarbage1 s1=new TestGarbage1();  
      TestGarbage1 s2=new TestGarbage1();  
      s1=null;  
      s2=null;  
      System.gc();  
     }  
    }  




## 182) How can an object be unreferenced?


**1) By nulling a reference:**

Employee e=new Employee();  
e=null;  

**2) By assigning a reference to another:**

Employee e1=new Employee();  
Employee e2=new Employee();  
e1=e2;//now the first object referred by e1 is available for garbage collection  

**3) By anonymous object:**
new Employee();  

## 183) What is the purpose of the finalize() method?

**The finalize() method is invoked just before the object is garbage collected.** It is used to perform cleanup processing. 

    public class FinalizeTest {  
        int j=12;  
        void add()  
        {  
            j=j+12;  
            System.out.println("J="+j);  
        }  
        public void finalize()  
        {  
            System.out.println("Object is garbage collected");  
        }  
        public static void main(String[] args) {  
            new FinalizeTest().add();  
            System.gc();  
            new FinalizeTest().add();  
        }  
    }  
      

## 184) Can an unreferenced object be referenced again?

Yes,



## 187) What is the purpose of the Runtime class?

Java Runtime class is used to interact with a java runtime environment. Java Runtime class provides methods to execute a process, invoke GC, get total and free memory, etc. There is only one instance of java.lang.Runtime class is available for one java application. **The Runtime.getRuntime() method returns the singleton instance of Runtime class.**

## 188) How will you invoke any external process in Java?

By Runtime.getRuntime().exec(?) method. Consider the following example.

    public class Runtime1{  
     public static void main(String args[])throws Exception{  
      Runtime.getRuntime().exec("notepad");//will open a new notepad  
     }  
    }  



## In a class implementing an interface, can we change the value of any variable defined in the interface?

Ans: No, we can't change the value of any variable of an interface in the implementing class as **all variables defined in the interface are by default public, static and Final and final variables are like constants which can't be changed later.**

## Is it correct to say that due to garbage collection feature in Java, a java program never goes out of memory?

Ans: Even though automatic garbage collection is provided by Java, it doesn't ensure that a Java program will not go out of memory as there is a possibility that creation of Java objects is being done at a faster pace compared to garbage collection resulting in filling of all the available memory resources.

So, garbage collection helps in reducing the chances of a program going out of memory but it doesn't ensure that.

## I want to re-reach and use an object once it has been garbage collected. How it's possible?

Ans: Once an object has been destroyed by garbage collector, it no longer exists on the heap and it can't be accessed again. There is no way to reference it again.





## 124) What is the package?

A package is a group of similar **type of classes, interfaces, and sub-packages.** It provides access protection and removes naming collision. 


    package mypack;  
    public class Simple{  
     public static void main(String args[]){  
        System.out.println("Welcome to package");  
       }  
    } 



## 128) Do I need to import java.lang package any time? Why?

No. It is by default loaded internally by the JVM.

## 129) Can I import same package/class twice? Will the JVM load the package twice at runtime?

One can import the same package or the same class multiple times. Neither compiler nor JVM complains about it. However, the JVM will internally load the class only once no matter how many times you import the same class.





Since str is of type String at runtime, first if statement evaluates to the true and second one to false.
