
## 107) What is the abstraction?

**Abstraction is a process of hiding the implementation details and showing only functionality to the user.** 

In Java, there are two ways to achieve the abstraction.

Abstract Class
Interface


## 109) What is the abstract class?


 It cannot be instantiated. It can have abstract methods, non-abstract methods, constructors, and static methods. It can also have the final methods which will force the subclass not to change the body of the method. 
 

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


Output

    running safely


## 110) Can there be an abstract method without an abstract class?

No, if there is an abstract method in a class, that class must be abstract.

## 111) Is the following program written correctly? If yes then what will be the output of the program?

    abstract class Calculate  
    {  
        abstract int multiply(int a, int b);  
    }  
       
    public class Main  
    {  
        public static void main(String[] args)  
        {  
            int result = new Calculate()  
            {      
                @Override  
                int multiply(int a, int b)  
                {  
                    return a*b;  
                }  
            }.multiply(12,32);  
            System.out.println("result = "+result);  
        }  
    }  

Yes, the program is written correctly. The Main class provides the definition of abstract method multiply declared in abstract class Calculation. The output of the program will be:

Output

    384

## 112) Can you use abstract and final both with a method?

No, because we need to override the abstract method to provide its implementation, whereas we can't override the final method.

## 113) Is it possible to instantiate the abstract class?

**No, the abstract class can never be instantiated even if it contains a constructor and all of its methods are implemented.**

## 114) What is the interface?

The interface is a blueprint for a class that has static constants and abstract methods. 


## 115) Can you declare an interface method static?

No, because methods of an interface are abstract by default, and **we can not use static and abstract together.**

## 116) Can the Interface be final?

No, because an interface **needs to be implemented by the other class** and if it is final, it can't be implemented by any class.

## 117) What is a marker interface?

**A Marker interface can be defined as the interface which has no data member and member functions.** For example, Serializable, Cloneable are marker interfaces.

    public interface Serializable{    
    }    

## 118) What are the differences between abstract class and interface?


An abstract class can have a method body (non-abstract methods).  The interface has only abstract methods.
An abstract class can have instance variables.  An interface cannot have instance variables.
An abstract class can have the constructor. The interface cannot have the constructor.
An abstract class can have static methods.  The interface cannot have static methods.
You can extend one abstract class.  You can implement multiple interfaces.
The abstract class can provide the implementation of the interface. The Interface can't provide the implementation of the abstract class.
The abstract keyword is used to declare an abstract class.  The interface keyword is used to declare an interface.
An abstract class can extend another Java class and implement multiple Java interfaces. An interface can extend another Java interface only.
An abstract class can be extended using keyword extends An interface class can be implemented using keyword implements

## 119) Can we define private and protected modifiers for the members in interfaces?

No, **they are implicitly public.**

## 120) When can an object reference be cast to an interface reference?

An object reference can be cast to an interface reference **when the object implements the referenced interface.**
