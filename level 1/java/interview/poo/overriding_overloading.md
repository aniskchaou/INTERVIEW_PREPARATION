

## 72) What is method overloading?

Method overloading is the polymorphism technique which allows us to **create multiple methods with the same name but different signature.** We can achieve method overloading in two ways.

**Changing the number of arguments**
**Changing the return type**
Method overloading increases **the readability of the program.** 
Method overloading is performed to figure out the program quickly.



## 73) Why is method overloading not possible by changing the return type in java?

In Java, ***method overloading is not possible by changing the return type of the program due to avoid the ambiguity.***

    class Adder{  
    static int add(int a,int b){return a+b;}  
    static double add(int a,int b){return a+b;}  
    }  
    class TestOverloading3{  
    public static void main(String[] args){  
    System.out.println(Adder.add(11,11));//ambiguity  
    }}  


Output:

    Compile Time Error: method add(int, int) is already defined in class Adder
    More Details.

## 74) Can we overload the methods by making them static?

**No, We cannot overload the methods** by just applying the static keyword to them(number of parameters and types are the same).

    public class Animal  
    {  
        void consume(int a)  
        {  
            System.out.println(a+" consumed!!");  
        }  
        static void consume(int a)  
        {  
            System.out.println("consumed static "+a);  
        }  
        public static void main (String args[])  
        {  
            Animal a = new Animal();  
            a.consume(10);  
            Animal.consume(20);  
        }  
    }    

Output

    Animal.java:7: error: method consume(int) is already defined in class Animal
        static void consume(int a)
                    ^
    Animal.java:15: error: non-static method consume(int) cannot be referenced from a static context
            Animal.consume(20);
                  ^
    2 errors

## 75) Can we overload the main() method?

Yes, we can have any number of main methods in a Java program **by using method overloading.**



## 77) What is the output of the following Java program?

    class OverloadingCalculation3{    
    
      void sum(int a,long b){System.out.println("a method invoked");}    
      
      void sum(long a,int b){System.out.println("b method invoked");}    
        
      public static void main(String args[]){  
        
      OverloadingCalculation3 obj=new OverloadingCalculation3();    
      obj.sum(20,20);//now ambiguity    
      }    
    } 

   
Output

    OverloadingCalculation3.java:7: error: reference to sum is ambiguous
    obj.sum(20,20);//now ambiguity  
         ^ 
          both method sum(int,long) in OverloadingCalculation3 
          and method sum(long,int) in OverloadingCalculation3 match
    1 error

Explanation

There are two methods defined with the same name, i.e., sum. The first method accepts the integer and long type whereas the second method accepts long and the integer type. 

## 78) What is method overriding:

Rules for Method overriding

The method must have **the same name as in the parent class.**
The method must have **the same signature as in the parent class.**
**Two classes must have an IS-A relationship between them.**


## 79) Can we override the static method?

No, you can't override the static method **because they are the part of the class, not the object.**

## 80) Why can we not override static method?

It is because the static method is the part of the class

## 81) Can we override the overloaded method?

Yes.


## 83) Can we override the private methods?

***No, we cannot override the private methods because the scope of private methods is limited*** to the class and we cannot access them outside of the class.

## 84) Can we change the scope of the overridden method in the subclass?

Yes, we can change the scope of the overridden method in the subclass. ***However, we must notice that we cannot decrease the accessibility of the method.*** 

The private can be changed to protected, public, or default.
The protected can be changed to public or default.
The default can be changed to public.
The public will always remain public.

## 85) Can we modify the throws clause of the superclass method while overriding it in the subclass?

Yes, we can modify the throws clause of ***the superclass method while overriding it in the subclass.*** However, there are some rules which are to be followed while overriding in case of exception handling.

## 86) What is the output of the following Java program?

    class Base  
    {  
        void method(int a)  
        {  
            System.out.println("Base class method called with integer a = "+a);  
        }  
           
        void method(double d)  
        {  
            System.out.println("Base class method called with double d ="+d);  
        }  
    }  
       
    class Derived extends Base  
    {  
        @Override  
        void method(double d)  
        {  
            System.out.println("Derived class method called with double d ="+d);  
        }  
    }  
       
    public class Main  
    {      
        public static void main(String[] args)  
        {  
            new Derived().method(10);  
        }  
    }  

Output

    Base class method called with integer a = 10

Explanation

The method() is overloaded in class Base whereas it is derived in class Derived with the double type as the parameter. In the method call, the integer is passed.

## 87) Can you have virtual functions in Java?

Yes, all functions in Java are virtual by default.

## 89) What is the output of the following Java program?

    class Base   
    {  
        public void baseMethod()  
        {  
            System.out.println("BaseMethod called ...");  
        }  
    }  
    class Derived extends Base   
    {  
        public void baseMethod()  
        {  
            System.out.println("Derived method called ...");  
        }  
    }  
    public class Test   
    {  
        public static void main (String args[])  
        {  
            Base b = new Derived();  
            b.baseMethod();  
        }  
    }  

Output

    Derived method called ...
