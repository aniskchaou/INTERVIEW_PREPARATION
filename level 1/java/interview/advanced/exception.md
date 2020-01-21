
## 133) Explain the hierarchy of Java Exception classes?

The java.lang.Throwable class is the root class of Java Exception hierarchy which is inherited by two subclasses: 

## 135) What is the base class for Error and Exception?

The Throwable class is the base class for Error and Exception.

## 136) Is it necessary that each try block must be followed by a catch block?

It is not necessary that each try block must be followed by a catch block. 

    public class Main{  
         public static void main(String []args){  
            try{  
                int a = 1;   
                System.out.println(a/0);  
            }  
            finally  
            {  
                System.out.println("rest of the code...");  
            }  
         }  
    }  
          

Output:

Exception in thread main java.lang.ArithmeticException:/ by zero
rest of the code...

## 137) What is the output of the following Java program?

    public class ExceptionHandlingExample {  
    public static void main(String args[])  
    {  
        try  
        {  
            int a = 1/0;  
            System.out.println("a = "+a);  
        }  
        catch(Exception e){System.out.println(e);}  
        catch(ArithmeticException ex){System.out.println(ex);}    
    }  
    }  

Output

ExceptionHandlingExample.java:10: error: exception ArithmeticException has already been caught
  catch(ArithmeticException ex){System.out.println(ex);}  
  ^
1 error
Explanation

ArithmaticException is the subclass of Exception. Therefore, it can not be used after Exception. **Since Exception is the base class for all the exceptions, therefore, it must be used at last to handle the exception. No class can be used after this.**

## 138) What is finally block?

The "finally" block is used to execute the important code of the program. It is executed whether an exception is handled or not. **In other words, we can say that finally block is the block which is always executed.**  The finally block is mainly used to place the cleanup code such as closing a file or closing a connection. 

## 139) Can finally block be used without a catch?

Yes, According to the definition of finally block, it must be followed by a try or catch block, therefore, we can use try block instead of catch. More details.

## 140) Is there any case when finally will not be executed?

Finally block will not be executed if program exits(either by calling System.exit() or by causing a fatal error that causes the process to abort).More details.


## 142) What is the output of the following Java program?

 

     public class Main{  
         public static void main(String []args){  
            try  
            {  
                throw 90;   
            }  
            catch(int e){  
                System.out.println("Caught the exception "+e);  
            }  
                  
        }  
    }  

Output

Main.java:6: error: incompatible types: int cannot be converted to Throwable
            throw 90; 
            ^
Main.java:8: error: unexpected type
        catch(int e){
              ^
  required: class
  found:    int
2 errors
Explanation

In Java, the throwable objects can only be thrown. If we try to throw an integer object, The compiler will show an error since we can not throw basic data type from a block of code.

## 143) What is the output of the following Java program?

    class Calculation extends Exception  
    {  
        public Calculation()   
        {  
            System.out.println("Calculation class is instantiated");  
        }  
        public void add(int a, int b)  
        {  
            System.out.println("The sum is "+(a+b));  
        }  
    }  
    public class Main{  
         public static void main(String []args){  
            try  
            {  
                throw new Calculation();   
            }  
            catch(Calculation c){  
                c.add(10,20);  
            }  
        }  
    }   

Output

Calculation class is instantiated
The sum is 30
Explanation

The object of Calculation is thrown from the try block which is caught in the catch block. The add() of Calculation class is called with the integer values 10 and 20 by using the object of this class. Therefore there sum 30 is printed. The object of the Main class can only be thrown in the case when the type of the object is throwable. To do so, we need to extend the throwable class.

## 144) Can an exception be rethrown?

Yes

## 199) What is serialization?

Serialization in Java is a mechanism of writing the state of an object into a byte stream. 
