




## 90) What is the final variable?

In Java, the final variable is used to restrict the user from updating it. 

    class Bike9{  
    
     final int speedlimit=90;//final variable  
    
     void run(){  
      speedlimit=400;  
     }  
     public static void main(String args[]){  
     Bike9 obj=new  Bike9();  
     obj.run();  
     }  
    }//end of class  


Output:

    Compile Time Error


## 91) What is the final method?

If we change any method to a final method, we can't override it. 

    class Bike{  
      final void run(){System.out.println("running");}  
    }  
         
    class Honda extends Bike{  
       void run(){System.out.println("running safely with 100kmph");}  
         
       public static void main(String args[]){  
       Honda honda= new Honda();  
       honda.run();  
       }  
    }  


Output:

    Compile Time Error

## 92) What is the final class?

If we make any class final, we can't inherit it into any of the subclasses.

    final class Bike{}  
      
    class Honda1 extends Bike{  
      void run(){System.out.println("running safely with 100kmph");}  
        
      public static void main(String args[]){  
      Honda1 honda= new Honda1();  
      honda.run();  
      }  
    }  


Output:

    Compile Time Error


## 93) What is the final blank variable?

A final variable, **not initialized at the time of declaration,** is known as the final blank variable. We can't initialize the final blank variable directly.

    class Student{  
    int id;  
    String name;  
   
    final String PAN_CARD_NUMBER;  
    ...  
    } 

 


## 94) Can we initialize the final blank variable?

Yes, if it is not static, we can initialize it in the constructor. If it is static blank final variable, it can be initialized only in the static block. 

## 95) Can you declare the main method as final?

Yes, We can declare the main method as
 public static final void main(String[] args){}.

## 96) What is the output of the following Java program?

    class Main {  
     public static void main(String args[]){  
       final int i;  
       i = 20;  
       System.out.println(i);  
     }  
    }  

Output

    20

Explanation

Since i is the blank final variable. It can be initialized only once. We have initialized it to 20. Therefore, 20 will be printed.

## 97) What is the output of the following Java program?

    class Base   
    {  
        protected final void getInfo()  
        {  
            System.out.println("method of Base class");  
        }  
    }  
       
    public class Derived extends Base  
    {  
        protected final void getInfo()  
        {  
            System.out.println("method of Derived class");  
        }  
        public static void main(String[] args)  
        {  
            Base obj = new Base();  
            obj.getInfo();  
        }  
    }  

Output

    Derived.java:11: error: getInfo() in Derived cannot override getInfo() in Base
    protected final void getInfo()
                         ^
  overridden method is final
1 error
Explanation

The getDetails() method is final; therefore it can not be overridden in the subclass.

## 98) Can we declare a constructor as final?

The constructor can never be declared as final because it is **never inherited**. 

## 99) Can we declare an interface as final?

No, we cannot declare an interface as final ***because the interface must be implemented by some class to provide its definition.*** 

## 100) What is the difference between the final method and abstract method?

The main difference between the final method and abstract method is that the abstract method ***cannot be final as we need to override them*** in the subclass to give its definition.
