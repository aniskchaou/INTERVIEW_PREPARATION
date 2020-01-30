## **What are the `Oops concepts`?**

-   Inheritance
-   Encapsulation
-   Polymorphism
-   Abstraction
-   Interface

## **What is `Inheritance`?**

-   Existing class is known as Super class
-   the derived class is known as a sub class.

```
public  class  Manupulation{

}

public  class  Addition extends  Manipulation{

}

```

**Inheritance is applicable for public and protected members only. Private members can’t be inherited.**

## **What is `Encapsulation`?**

`Purpose of Encapsulation`:

-   Protects the code from others.
-   Code maintainability.

public class Addition(){ private int a = 5; //Here the variable is marked as private }

**For encapsulation, we need to make all the instance variables as private and create setter and getter for those variables.**

## **What is `Polymorphism`?**

```
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

```

results :

```
super class 
sub class

```

Polymorphism is applicable for overriding and not for overloading.

## **What is meant by `Method Overriding`?**

-   Method  `name`  should be same
-   `Argument`  should be same
-   `Return`  type also should be same

## **What is meant by `Overloading`?**

-   `Same`  method  `name`
-   `Different argument`  type
-   May have  `different return`  types
example 

  ````  public class Manipulation{ 
    //Super class 
    public void add(String name){ } }
    
    public class Addition extends Manipulation{
    
    public void add(){} 
    public void add(int a){}
    
    public static void main(String args[]){ 
    Addition addition = new Addition(); 
    addition.add(); 
    } }
````
## **What is meant by `Local variable` and `Instance variable`?**

-   Local variables are defined in the method
-   An instance variable is defined inside the class




## **What is meant by `Interface`?**

  

```
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

```

## **What is meant by `Abstract class`?**

```
public  abstract  class  Manupulation{

public  abstract  void  add();//Abstract method  declaration

Public void  subtract(){

}
}

```

-   An abstract class  `may have a Non- abstract method`  also.
    
-   The concrete Subclass which extends the Abstract class should provide the implementation for abstract methods.


## **Can we use different return types for methods when overridden?**

```
Class B extends A {

A method(int x) {

//original method }

B method(int x) {

//overridden method

}}

```

## **What's the base class of all exception classes?**

Ans: In Java, Java.lang.Throwable

## **What's the order of call of constructors in inheritiance?**

Ans: In case of inheritance, first the constructor of the super class is invoked and then the constructor of the derived class is invoked.

## **Can a class be a super class and a sub-class at the same time?**

**`If there is a hierarchy of inheritance used`**, a class can be a super class for another class and a sub-class for another one at the same time.

```
public class world {..........}
public class continenet extends world {............}
public class country extends continent {......................}

```

## **How objects of a class are created if no constructor is defined in the class?**

Ans: Even if no explicit constructor is defined in a java class,  **`objects get created successfully as a default constructor is implicitly used`**  for object creation. This constructor has no parameters.

## **What's the base class in Java from which all classes are derived?**


 java.lang.object


## **What is the final keyword in Java?**


**Final variable**



Once a variable is declared as final,  **then the value of the variable could not be changed. It is like a constant.**

final int = 12;


**Final method:**



**A final keyword in a method that couldn’t be overridden**. If a method is marked as a final, then it can’t be overridden by the subclass.


**Final class:**


**If a class is declared as final, then the class couldn’t be subclassed**. No class can extend the final class.

## **What is ternary operator? Give an example.**


    public class conditionTest  { 
    public static void main(String args[]) { 
    String status;
    int rank = 3; 
     
     status = (rank == 1) ? "Done" : "Pending"; 
     
     System.out.println(status); 
     }}



## **How can you generate random numbers in Java?**

-   Using Math.random() you can generate  **`random numbers in the range greater than or equal to 0.1 and less than 1.0`**
-   Using Random class in package java.util

## Can we override static methods of a class?

Ans: We cannot override static methods.  **`Static methods belong to a class and not to individual objects and are resolved at the time of compilation (not at runtime).`**

```
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

```

Ans: Output will be:

```
Displaying from subclass

Displaying from superclass

```

## Object class in Java

The Object class is the parent class of all the classes in java by default. In other words, it is the topmost class of java.

**public final Class getClass()**   returns the Class class object of this object. 
**public int hashCode()**   returns the hashcode number for this object.
**public boolean equals(Object obj)**   compares the given object to this object.
**protected Object clone()**    creates and returns the exact copy (clone) of this object.
**public String toString()**    returns the string representation of this object.
**public final void notify()**  wakes up single thread, waiting on this object's monitor.
**public final void notifyAll()**   wakes up all the threads, waiting on this object's monitor.
**public final void wait(long timeout)**    causes the current thread to wait for the specified milliseconds, until another thread notifies (invokes notify() or notifyAll() method).
**public final void wait(long timeout,int nanos)**  causes the current thread to wait for the specified milliseconds and nanoseconds, until another thread notifies (invokes notify() or notifyAll() method).
**public final void wait()**    causes the current thread to wait, until another thread notifies (invokes notify() or notifyAll() method).
**protected void finalize()**   is invoked by the garbage collector before object is being garbage collected.

## Java Math class

     int x=-1;
            System.out.println(Math.abs(x)); //1
            System.out.println(Math.ceil(2.3)); //3.0
            System.out.println(Math.round(2.3)); //2
            System.out.println(Math.floor(2.3)); //2.0
            System.out.println(Math.max(1, 0));//1
            System.out.println(Math.min(1, 0));//0
            System.out.println(Math.pow(2, 2));//4.0
            System.out.println(Math.random());//0.7873627181811799
            System.out.println(Math.PI);//3.141592653589793

## Wrapper classes in Java

The wrapper class in Java provides the mechanism to convert primitive into object and object into primitive.

Since J2SE 5.0, autoboxing and unboxing feature convert primitives into objects and objects into primitives automatically.

**Autoboxing**

    //Converting int into Integer  
    int a=20;  
    Integer i=Integer.valueOf(a);//converting int into Integer explicitly  
    Integer j=a;//autoboxing, now compiler will write Integer.valueOf(a) internally  
    System.out.println(a+" "+i+" "+j);  

**Unboxing**

    //Converting Integer to int    
    Integer a=new Integer(3);    
    int i=a.intValue();//converting Integer to int explicitly  
    int j=a;//unboxing, now compiler will write a.intValue() internally    
    System.out.println(a+" "+i+" "+j);    




## Java Command Line Arguments

    class CommandLineExample{  
    public static void main(String args[]){  
    System.out.println("Your first argument is: "+args[0]);  
    }  
    } 

 
compile by > javac CommandLineExample.java  
run by > java CommandLineExample sonoo  


## Access Modifiers in Java

# Default

   The data members, class or methods which are not declared using any access modifiers i.e. having default access modifier are accessible  **only within the same package**.

In this example, we will create two packages and the classes in the packages will be having the default access modifiers and we will try to access a class from one package from a class of second package.

## Private

-   The methods or data members declared as private are accessible only  **within the class**  in which they are declared.
-   Any other  **class of same package will not be able to access**  these members.
-   Top level Classes or interface can not be declared as private because
    1.  private means “only visible within the enclosing class”.
    2.  protected means “only visible within the enclosing class and any subclasses”
    
    Hence these modifiers in terms of application to classes, they apply only to nested classes and not on top level classes
    

## protected

-   The methods or data members declared as protected are  **accessible within same package or sub classes in different package.**

## public:

-   The public access modifier has the  **widest scope**  among all other access modifiers.
-   Classes, methods or data members which are declared as public are  **accessible from every where**  in the program. There is no restriction on the scope of a public data members.



|           │ Class │ Package │ Subclass │ Subclass │ World  |
|           │       │         │(same pkg)│(diff pkg)│        |
|───────────┼───────┼─────────┼──────────┼──────────┼────────|
|public     │   +   │    +    │    +     │     +    │   +    | 
|───────────┼───────┼─────────┼──────────┼──────────┼────────|
|protected  │   +   │    +    │    +     │     +    │        | 
|───────────┼───────┼─────────┼──────────┼──────────┼────────|
|no modifier│   +   │    +    │    +     │          │        | 
|───────────┼───────┼─────────┼──────────┼──────────┼────────|
|private    │   +   │         │          │          │        |
|___________|_______|_________|__________|__________|________|
 + : accessible         blank : not accessible



