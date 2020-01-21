


## 102) What is Runtime Polymorphism?



    class Bike{  
      void run(){System.out.println("running");}  
    }  
    class Splendor extends Bike{ 
     
      void run(){System.out.println("running safely with 60km");}  
      
      public static void main(String args[]){  
        
        Bike b = new Splendor();//upcasting  
        b.run();  
      }  
    }  


Output:


    running safely with 60km.

In this process, an overridden method is called through the reference variable of a superclass. The determination of the method to be called is based on the object being referred to by the reference variable.



## 103) Can you achieve Runtime Polymorphism by data members?


    class Bike{  
     int speedlimit=90;  
    }  

    class Honda3 extends Bike{  
     int speedlimit=150;  

     public static void main(String args[]){  
      Bike obj=new Honda3();  
      System.out.println(obj.speedlimit);//90  
       }  


Output:

90


## 104) What is the difference between static binding and dynamic binding?


**Static Binding**

    class Dog{  
     private void eat(){System.out.println("dog is eating...");}  
      
     public static void main(String args[]){  
      Dog d1=new Dog();  
      d1.eat();  
     }  
    } 

 
**Dynamic Binding**

    class Animal{  
     void eat(){System.out.println("animal is eating...");}  
    }  
      
    class Dog extends Animal{  
     void eat(){System.out.println("dog is eating...");}  
      
     public static void main(String args[]){  
      Animal a=new Dog();  
      a.eat();  
     }  
    }  



## 105) What is the output of the following Java program?

    class BaseTest   
    {  
      void print()  
      {  
        System.out.println("BaseTest:print() called");  
      }  
    }  
    public class Test extends BaseTest   
    {  
      void print()   
      {  
        System.out.println("Test:print() called");  
      }  
      public static void main (String args[])  
      {  
        BaseTest b = new Test();  
        b.print();  
      }  
    }  

Output

 

     Test:print() called




