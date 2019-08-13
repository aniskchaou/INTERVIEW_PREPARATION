
## Abstract class

 

    abstract class Bike{  
      abstract void run();  
    } 
     
    class Honda4 extends Bike{  
    void run(){System.out.println("running safely");}  
    
    public static void main(String args[]){  
     Bike obj = new Honda4();  
     obj.run();  
    }  
    }  

**output**

## running safely

## primitive type

## approximation of pi

## ascii art

## interface vs implementation

## exception


## differeence == and
```
0 == false   // true
0 === false  // false, because they are of a different type
1 == "1"     // true, automatic type conversion for value only
1 === "1"    // false, because they are of a different type
null == undefined // true
null === undefined // false
'0' == false // true
'0' === false // false
```
## Final method

**A final method cannot be overridden by any subclasses**. As mentioned previously, the final modifier prevents a method from being modified in a subclass.

    public class Test {
       public final void changeName() {
          // body of method
       }
    }
Multiple inheritance

    // First Parent class 
    class Parent1 
    { 
        void fun() 
        { 
            System.out.println("Parent1"); 
        } 
    } 
      
    // Second Parent Class 
    class Parent2 
    { 
        void fun() 
        { 
            System.out.println("Parent2"); 
        } 
    } 
      
    // Error : Test is inheriting from multiple 
    // classes 
    class Test extends Parent1, Parent2 
    { 
       public static void main(String args[]) 
       { 
           Test t = new Test(); 
           t.fun(); 
       } 
    }

 
**Output :**
Compiler Error

## Object class

Object class in Java
The Object class is the parent class of all the classes in java by default. 


**toString() :** toString() provides String representation of an Object and used to convert an object to String. 

**hashCode() :** For every object, JVM generates a unique number which is hashcode. It returns distinct integers for distinct objects.
Use of hashCode() method : Returns a hash value that is used to search object in a collection. 

    public class Student 
    { 
        static int last_roll = 100;  
        int roll_no; 
      
        // Constructor 
        Student() 
        { 
            roll_no = last_roll; 
            last_roll++; 
        } 
      
        // Overriding hashCode() 
        @Override
        public int hashCode() 
        { 
            return roll_no; 
        } 
      
        // Driver code 
        public static void main(String args[]) 
        { 
            Student s = new Student(); 
      
            // Below two statements are equivalent 
            System.out.println(s); 
            System.out.println(s.toString()); 
        } 
    } 

**Output :**

    Student@64
    Student@64

**equals(Object obj)** : Compares the given object to “this” object (the object on which the method is called).

**getClass() :** Returns the class object of “this” object and used to get actual runtime class of the object.

**finalize() method** : This method is called just before an object is garbage collected. It is called by the Garbage Collector on an object when garbage collector determines that there are no more references to the object. 

    public class Test 
    { 
        public static void main(String[] args) 
        { 
            Test t = new Test(); 
            System.out.println(t.hashCode()); 
      
            t = null; 
      
            // calling garbage collector  
            System.gc(); 
      
            System.out.println("end"); 
        } 
      
        @Override
        protected void finalize() 
        { 
            System.out.println("finalize method called"); 
        } 
    } 

**Output:**
366712642

**clone() :** It returns a new object that is exactly the same as this object. For clone() method refer Clone()
The remaining three methods **wait(), notify() notifyAll()** are related to Concurrency. 

## Singleton

    class Singleton 
    { 
        // static variable single_instance of type Singleton 
        private static Singleton single_instance = null; 
      
        // variable of type String 
        public String s; 
      
        // private constructor restricted to this class itself 
        private Singleton() 
        { 
            s = "Hello I am a string part of Singleton class"; 
        } 
      
        // static method to create instance of Singleton class 
        public static Singleton getInstance() 
        { 
            if (single_instance == null) 
                single_instance = new Singleton(); 
      
            return single_instance; 
        } 
    } 

## String object
 

     String s1="java";//creating string by java string literal
     char ch[]={'s','t','r','i','n','g','s'};
     String s2=new String(ch);//converting char array to string
     String s3=new String("example");//creating java string by new keyword

## Thread

 **L'interface Runnable**



    public class MonTraitement implements Runnable {
    public void run() {
    int i = 0;
    for (i = 0; i > 10; i++) {
    System.out.println("" + i);
    }
    }
    }

**Classe thread**

    public class MonThread extends Thread {
     
    @Override
    public void run() {
    System.out.println("Mon traitement");
    }
    }


    public class TestThread {
    
    public static void main(String[] args) {
    MonThread t = new MonThread();
    t.start();
    }
    }

## Visibility of attributes

 
**`Default`**: When no access modifier is specified for a class , method or data member – It is said to be having the default access modifier by default.
The data members, class or methods which are not declared using any access modifiers i.e. having default access modifier are accessible only within the same package.
//Java program to illustrate default modifier 

    package p1; 
      
    //Class Geeks is having Default access modifier 
    class Geek 
    { 
        void display() 
           { 
               System.out.println("Hello World!"); 
           } 
    }

 



    //Java program to illustrate error while  
    //using class from different package with 
    //default modifier 
    package p2; 
    import p1.*; 
      
    //This class is having default access modifier 
    class GeekNew 
    { 
        public static void main(String args[]) 
           {   
              //accessing class Geek from package p1 
              Geeks obj = new Geek(); 
      
              obj.display(); 
           } 
    } 

Output:

    Compile time error
    
**`Private:`** The private access modifier is specified using the keyword private.
•   The methods or data members declared as private **are accessible only within the class in which they are declared.**

**`protected`:** The protected access modifier is specified using the keyword protected.
•   The methods or data members declared as protected are accessible within same package or sub classes in different package.

**`public:`** The public access modifier is specified using the keyword public.
•   The public access modifier has the widest scope among all other access modifiers.
•   Classes, methods or data members which are declared as public are accessible from every where in the program. There is no restriction on the scope of a public data members.

## Friendly class

    package com.asjava;
    
    public class TestOne {
          protected  static String protectedStr = "protected";
          static String friendlyStr = "friendly";
    }
    package com.asjava.ts;
    
    import com.asjava.TestOne;
    
    public class TestOneSon extends TestOne {
         public static void main(String[] args){
            //correct to use, class TestOneSon is subclass of TestOne
            System.out.print(TestOne.protectedStr);
            //incorrect to use, friendly field is only visible to access in same package
            System.out.print(TestOne.friendlyStr);
        }
    }

## Bitwise operator >>


## Equals & hashcode

•   **`equals(Object obj):`** a method provided by java.lang.Object that indicates whether some other object passed as an argument is "equal to" the current instance.***The default implementation provided by the JDK is based on memory location — two objects are equal if and only if they are stored in the same memory address.***
•   **`hashcode():`** a method provided by java.lang.Object that returns an integer representation of the object memory address. **By default, this method returns a random integer that is unique for each instance.** 

***This integer might change between several executions of the application and won't stay the same.***

## Garbage collector

Advantage of Garbage Collection
o   It makes java memory efficient because garbage collector removes the unreferenced objects from heap memory.
o   It is automatically done by the garbage collector(a part of JVM) so we don't need to make extra efforts.


**1) By nulling a reference:**

    .   Employee e=new Employee();  
        e=null;  

**2) By assigning a reference to another:**

    1.  Employee e1=new Employee();  
    2.  Employee e2=new Employee();  
    3.  e1=e2;//now the first object referred by e1 is available for garbage 

collection  
**3) By anonymous object:**

    new Employee();

  



**finalize() method**
The finalize() method is invoked each time before the object is garbage collected. This method can be used to perform cleanup processing. 

**gc() method**
The gc() method is used to invoke the garbage collector to perform cleanup processing. The gc() is found in System and Runtime classes.

Simple Example of garbage collection in java

    1.  public class TestGarbage1{  
    2.   public void finalize(){System.out.println("object is garbage collected");}  
    3.   public static void main(String args[]){  
    4.    TestGarbage1 s1=new TestGarbage1();  
    5.    TestGarbage1 s2=new TestGarbage1();  
    6.    s1=null;  
    7.    s2=null;  
    8.    System.gc();  
    9.   }  
    10. }  

## Interfaces

    interface FirstInterface {
      public void myMethod(); // interface method
    }
    
    interface SecondInterface {
      public void myOtherMethod(); // interface method
    }
    
    // DemoClass "implements" FirstInterface and SecondInterface
    class DemoClass implements FirstInterface, SecondInterface {
      public void myMethod() {
        System.out.println("Some text..");
      }
      public void myOtherMethod() {
        System.out.println("Some other text...");
      }
    }
    
    class MyMainClass {
      public static void main(String[] args) {
        DemoClass myObj = new DemoClass();
        myObj.myMethod();
        myObj.myOtherMethod();
      }
    }

## Constant

public static final String WELCOME_MESSAGE = "Hello, welcome to the server";

## Bitwise operator &

`&`  is bitwise.  `&&`  is logical.

`&`  evaluates both sides of the operation.  
`&&`  evaluates the left side of the operation, if it's  `true`, it continues and evaluates the right side.
## Bitwise operator |

## Linary operator (i++)
i++ and ++i are very similar but not exactly the same. Both increment the number, but ++i increments the number before the current expression is evaluted, whereas i++ increments the number after the expression is evaluated.

    int i = 3;
    int a = i++; // a = 3, i = 4
    int b = ++a; // b = 4, a = 4

## Operation integers

    public class ArithmeticDemo {
        public static void main(String[] args) {
    
            //a few numbers
            int i = 37;
            int j = 42;
            double x = 27.475;
            double y = 7.22;
            System.out.println("Variable values...");
            System.out.println("    i = " + i);
            System.out.println("    j = " + j);
            System.out.println("    x = " + x);
            System.out.println("    y = " + y);
    
            //adding numbers
            System.out.println("Adding...");
            System.out.println("    i + j = " + (i + j));
            System.out.println("    x + y = " + (x + y));
    
            //subtracting numbers
            System.out.println("Subtracting...");
            System.out.println("    i - j = " + (i - j));
            System.out.println("    x - y = " + (x - y));
    
            //multiplying numbers
            System.out.println("Multiplying...");
            System.out.println("    i * j = " + (i * j));
            System.out.println("    x * y = " + (x * y));
    
            //dividing numbers
            System.out.println("Dividing...");
            System.out.println("    i / j = " + (i / j));
            System.out.println("    x / y = " + (x / y));
    
            //computing the remainder resulting from dividing numbers
            System.out.println("Computing the remainder...");
            System.out.println("    i % j = " + (i % j));
            System.out.println("    x % y = " + (x % y));
    
            //mixing types
            System.out.println("Mixing types...");
            System.out.println("    j + y = " + (j + y));
            System.out.println("    i * x = " + (i * x));
        }
    }

output 

        i = 37
        j = 42
        x = 27.475
        y = 7.22
    Adding...
        i + j = 79
        x + y = 34.695
    Subtracting...
        i - j = -5
        x - y = 20.255
    Multiplying...
        i * j = 1554
        x * y = 198.37
    Dividing...
        i / j = 0
        x / y = 3.8054
    Computing the remainder...
        i % j = 37
        x % y = 5.815
    Mixing types...
        j + y = 49.22
        i * x = 1016.58

## Use of exeptions

**Java try and catch**

    public class MyClass {
      public static void main(String[ ] args) {
        try {
          int[] myNumbers = {1, 2, 3};
          System.out.println(myNumbers[10]);
        } catch (Exception e) {
          System.out.println("Something went wrong.");
        }
      }
    }

The output will be:

    Something went wrong.
**Finally**
The finally statement lets you execute code, after try...catch, regardless of the 

    public class MyClass {
      public static void main(String[] args) {
        try {
          int[] myNumbers = {1, 2, 3};
          System.out.println(myNumbers[10]);
        } catch (Exception e) {
          System.out.println("Something went wrong.");
        } finally {
          System.out.println("The 'try catch' is finished.");
        }
      }
    }

The output will be:

    Something went wrong.
    The 'try catch' is finished.

**The throw keyword**

    public class MyClass {
      static void checkAge(int age) { 
        if (age < 18) {
          throw new ArithmeticException("Access denied - You must be at least 18 years old."); 
        }
        else {
          System.out.println("Access granted - You are old enough!"); 
        }
      } 
    
      public static void main(String[] args) { 
        checkAge(15); // Set age to 15 (which is below 18...)
      } 
    }

The output will be:

    Exception in thread "main" java.lang.ArithmeticException: Access denied - You must be at least 18 years old.
            at MyClass.checkAge(MyClass.java:4)
            at MyClass.main(MyClass.java:12)


## Enum


•   Enum declaration can be done outside a Class or inside a Class but not inside a Method.

    enum Color 
    { 
        RED, GREEN, BLUE; 
    } 
      
    public class Test 
    { 
        // Driver method 
        public static void main(String[] args) 
        { 
            Color c1 = Color.RED; 
            System.out.println(c1); 
        } 
    }

Output :

    RED


    public class Test 
    { 
        enum Color 
        { 
            RED, GREEN, BLUE; 
        } 
      
        // Driver method 
        public static void main(String[] args) 
        { 
            Color c1 = Color.RED; 
            System.out.println(c1); 
        } 
    }

Output :

    RED


Interface vs implementation

## Multiple inheritance of interfaces

     Live Demo
    interface AnimalEat {
       void eat();
    }
    interface AnimalTravel {
       void travel();
    }
    class Animal implements AnimalEat, AnimalTravel {
       public void eat() {
          System.out.println("Animal is eating");
       }
       public void travel() {
          System.out.println("Animal is travelling");
       }
    }
    public class Demo {
       public static void main(String args[]) {
          Animal a = new Animal();
          a.eat();
          a.travel();
       }
    }

Output

    Animal is eating
    Animal is travelling

## Size of arraylist

The java.util.ArrayList.size() method returns the number of elements in this list i.e the size of the list.

**public int size()**

## String buffers


StringBuffer is a peer class of String that provides much of the functionality of strings. 
String represents fixed-length, immutable character sequences while StringBuffer represents growable and writable character sequences.


    import java.io.*; 
    class GFG { 
        public static void main(String[] args) 
        { 
            StringBuffer s = new StringBuffer("GeeksforGeeks"); 
            int p = s.length(); 
            int q = s.capacity(); 
            System.out.println("Length of string GeeksforGeeks=" + p); 
            System.out.println("Capacity of string GeeksforGeeks=" + q); 
        } 
    } 

Output:

    Length of string GeeksforGeeks=13
    Capacity of string GeeksforGeeks=29

•   append( ): It is used to add text at the end of the existence text. Here are a few of its forms:

    import java.io.*; 
    class GFG { 
        public static void main(String[] args) 
        { 
            StringBuffer s = new StringBuffer("Geeksfor"); 
            s.append("Geeks"); 
            System.out.println(s); // returns GeeksforGeeks 
            s.append(1); 
            System.out.println(s); // returns GeeksforGeeks1 
        } 
    } 

Output:

    GeeksforGeeks
    GeeksforGeeks1

## Dependency inversion principle (DIP)

## The liskov subtitustion principle (LSP)

## Inheritance


    1.  class Animal{  
    2.  void eat(){System.out.println("eating...");}  
    3.  }  
    4.  class Dog extends Animal{  
    5.  void bark(){System.out.println("barking...");}  
    6.  }  
    7.  class TestInheritance{  
    8.  public static void main(String args[]){  
    9.  Dog d=new Dog();  
    10. d.bark();  
    11. d.eat();  
    12. }}  

Output:

    barking...
    eating...

**Multilevel Inheritance Example**


    1.  class Animal{  
    2.  void eat(){System.out.println("eating...");}  
    3.  }  
    4.  class Dog extends Animal{  
    5.  void bark(){System.out.println("barking...");}  
    6.  }  
    7.  class BabyDog extends Dog{  
    8.  void weep(){System.out.println("weeping...");}  
    9.  }  
    10. class TestInheritance2{  
    11. public static void main(String args[]){  
    12. BabyDog d=new BabyDog();  
    13. d.weep();  
    14. d.bark();  
    15. d.eat();  
    16. }}  

Output:

    weeping...
    barking...
    eating...

## Counter synchronization

## Simple Boolean expression
       public int void (int a , int b)
       {
       return a==1 || b==1 || a+b==1;
       }
## Simple fix

## Strings equality
// Java program to Compare two strings 
// lexicographically 

    public class GFG { 
      
        // This method compares two strings 
        // lexicographically without using 
        // library functions 
        public static int stringCompare(String str1, String str2) 
        { 
      
            int l1 = str1.length(); 
            int l2 = str2.length(); 
            int lmin = Math.min(l1, l2); 
      
            for (int i = 0; i < lmin; i++) { 
                int str1_ch = (int)str1.charAt(i); 
                int str2_ch = (int)str2.charAt(i); 
      
                if (str1_ch != str2_ch) { 
                    return str1_ch - str2_ch; 
                } 
            } 
      
            // Edge case for strings like 
            // String 1="Geeks" and String 2="Geeksforgeeks" 
            if (l1 != l2) { 
                return l1 - l2; 
            } 
      
            // If none of the above conditions is true, 
            // it implies both the strings are equal 
            else { 
                return 0; 
            } 
        } 
      
        // Driver function to test the above program 
        public static void main(String args[]) 
        { 
            String string1 = new String("Geeksforgeeks"); 
            String string2 = new String("Practice"); 
            String string3 = new String("Geeks"); 
            String string4 = new String("Geeks"); 
      
            // Comparing for String 1 < String 2 
            System.out.println("Comparing " + string1 + " and " + string2 
                               + " : " + stringCompare(string1, string2)); 
      
            // Comparing for String 3 = String 4 
            System.out.println("Comparing " + string3 + " and " + string4 
                               + " : " + stringCompare(string3, string4)); 
      
            // Comparing for String 1 > String 4 
            System.out.println("Comparing " + string1 + " and " + string4 
                               + " : " + stringCompare(string1, string4)); 
        } 
    } 


## Hashtable

This class implements a hash table, which maps keys to values. Any non-null object can be used as a key or as a value.

    class hashTabledemo { 
        public static void main(String[] arg) 
        { 
            // creating a hash table 
            Hashtable<Integer, String> h = 
                          new Hashtable<Integer, String>(); 
      
            Hashtable<Integer, String> h1 = 
                          new Hashtable<Integer, String>(); 
      
            h.put(3, "Geeks"); 
            h.put(2, "forGeeks"); 
            h.put(1, "isBest"); 
      
            // create a clone or shallow copy of hash table h 
            h1 = (Hashtable<Integer, String>)h.clone(); 
      
            // checking clone h1 
            System.out.println("values in clone: " + h1); 
      
            // clear hash table h 
            h.clear(); 
      
            // checking hash table h 
            System.out.println("after clearing: " + h); 
        } 
    } 

Output:

    values in clone: {3=Geeks, 2=forGeeks, 1=isBest}
    after clearing: {}

## Largest win from chaos
```
  //initialisation
        int tab[] = {2, 6, 8, 8, 9, 10};
        int min = 0, max = 0;

        //algorithme
        for (int i = 0; i < tab.length; i++) {
            if (tab[i] < min) {
                min = tab[i];
            } else if (tab[i] > max) {
                max = tab[i];
            }
        }
```
## Use of string buffer/join

Use StringBuffer to Concatenate Strings
To improve performance, instead of using string concatenation, use `StringBuffer.append().`
String objects are immutable—they never change after creation. For example, consider the following code:

    String str = "testing";
    str = str + "abc";

The compiler translates this code as:

    String str = "testing";
    StringBuffer tmp = new StringBuffer(str);
    tmp.append("abc");
    str = tmp.toString();

## Range sum
```
 public class RangeSum
    {
    
       public static void main(String[] args)
       {
          int[] numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9};
          
          System.out.print("The sum of elements 2 through " +
                           "5 is "+ rangeSum(numbers, 3, 5));
       }
       
  public static int rangeSum(int[] array, int start, int end)
   {
      if (start > end)
         return 0;
      else
         return array[start] +
                    rangeSum(array, start + 1, end);
   }
}
```
## Secure closure of an i/o stream

You can wrap things in try and catch in order to ensure your stream gets closed.

     try {
         int code = reader.read();
         while (code != -1) {
            System.out.print((char) code);
            code = reader.read();
         }
     } finally {
        try {
            reader.close();
        } catch(IOException e) {
            // Log here.
        }
     }

The try/catch block under finally allows you to close the reader and do something about the exception, should it occur.

## Duplacates removal

## Summing based on factors

    static int divSum(int n) {
    
    ```
            int result = 0; 
            for (int i = 2; i <= Math.sqrt(n); i++) 
            { 
                
                if (n % i == 0) 
                { 
                 
                    if (i == (n / i)) 
                        result += i; 
                    else
                        result += (i + n / i); 
                } 
            } 
          
            return (result + n + 1); 
              
        } 
    ```

## Intervals

## Summer sales

## Asci art

## Twins

## Approximation pi

## Reshape string
```
public static String reshape(int n, String str) {

        //replace each space with empty string
        str = str.replace(" ", "");

        //insert a '\n' character each n characters
        String res = "";

        for (int i = 0; i < str.length(); i++) {

            if (i % n == 0 && i != 0) {
                res = res + '\n' + str.charAt(i);
            } else {
                res += str.charAt(i);
            }

        }

        return res;

    }
```
## Combinations options in a tournament

## Move toward zero
```
static void pushZerosToEnd(int arr[], int n) {
    int count = 0;

    for (int i = 0; i < n; i++) {
        if (arr[i] != 0) {
            arr[count++] = arr[i];
        }
    }

    while (count < n) {
        arr[count++] = 0;
    }
}
```

## Joining point

## Loop detection

## From the fruit we know the tree

## Filefinder

## Giving change
```
public static final int[] CENTIMES = {500, 200, 100, 50, 20, 10, 5, 2, 1};

    public static int[] monnaie(int centimes) {
        int[] rendu = new int[CENTIMES.length];

        for (int i = 0; i < CENTIMES.length; i++) {
            rendu[i] = centimes / CENTIMES[i];
            centimes %= CENTIMES[i];
        }

        return rendu;
    }
```
## Ternary operator


    booleanExpression ? expression1 : expression2
exemple

    int num = 8;
    String msg = "";
    if(num > 10) {
        msg = "Number is greater than 10";
    }
    else {
        msg = "Number is less than or equal to 10";
    }

ternary oprator: 

        final String msg = num > 10
      ? "Number is greater than 10"
      : "Number is less than or equal to 10";

## find the temperature

    static double closestToZero(double[] ts) {
            if (ts.length == 0) return 0;
    
            double closest = ts[0];
            for (double i : ts) {
                double abs = Math.abs(i);
                double absClosest = Math.abs(closest);
                if (abs < absClosest) {
                    closest = i;
                } else if (abs == absClosest && closest < 0) {
                    closest = i;
                }
            }
            return closest;
        }






















