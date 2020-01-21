## 23) What is object-oriented paradigm?

It is a programming paradigm based on objects having data and methods defined in the class to which it belongs. 

## 26) What will be the initial value of an object reference which is defined as an instance variable?

All object references ***are initialized to null*** in Java.


## 27) What is the constructor?

The constructor can be defined as the special type of method that is used to initialize the state of an object. It is invoked when the class is instantiated.


## 28) How many types of constructors are used in Java?

**Default Constructor:** default constructor is the one which does not accept any value. 
**Parameterized Constructor:** The parameterized constructor is the one which can initialize the instance variables with the given values.

## 29) What is the purpose of a default constructor?

    class Student3{  
    int id;  
    String name;  
      
    void display(){System.out.println(id+" "+name);}  
      
    public static void main(String args[]){  
    Student3 s1=new Student3();  
    Student3 s2=new Student3();  
    s1.display();  
    s2.display();  
    }  
    }  


Output:

    0 null
    0 null

Explanation: In the above class, you are not creating any constructor, so **compiler provides you a default constructor.** Here 0 and null values are provided by default constructor.


## 30) Does constructor return any value?

Ans: yes, The constructor **implicitly returns the current instance of the class** (You can't use an explicit return type with the constructor).

## 31)Is constructor inherited?

No, **The constructor is not inherited**.

## 32) Can you make a constructor final?

No, **the constructor can't be final**.

## 33) Can we overload the constructors?

Yes, the constructors can **be overloaded by changing the number of arguments accepted by the constructor or by changing the data type of the parameters.** Consider the following example.

    class Test   
    {  
        int i;   
        public Test(int k)  
        {  
            i=k;  
        }  
        public Test(int k, int m)  
        {  
            System.out.println("Hi I am assigning the value max(k, m) to i");  
            if(k>m)  
            {  
                i=k;   
            }  
            else   
            {  
                i=m;  
            }  
        }  
    }  
    public class Main   
    {  
        public static void main (String args[])   
        {  
            Test test1 = new Test(10);  
            Test test2 = new Test(12, 15);  
            System.out.println(test1.i);  
            System.out.println(test2.i);  
        }  
    }  
      

## 35) What are the differences between the constructors and methods?


**A constructor is used to initialize the state of an object.** 
**A constructor must not have a return type.**  
**The constructor is invoked implicitly.**  
**The constructor name must be same as the class name**.    



## 36) What is the output of the following Java program?

    public class Test   
    {  
        Test(int a, int b)  
        {  
            System.out.println("a = "+a+" b = "+b);  
        }  
        Test(int a, float b)  
        {  
            System.out.println("a = "+a+" b = "+b);  
        }  
        public static void main (String args[])  
        {  
            byte a = 10;   
            byte b = 15;  
            Test test = new Test(a,b);  
        }  
    }  

The output of the following program is:

    a = 10 b = 15



## 37) What is the output of the following Java program?

    class Test   
    {  
        int i;   
    }  
    public class Main   
    {  
        public static void main (String args[])   
        {  
            Test test = new Test();   
            System.out.println(test.i);  
        }  
    }  

**The output of the program is 0 because the variable i is initialized to 0 internally.** As we know that a default constructor is invoked implicitly if there is no constructor in the class, the variable i is initialized to 0 since there is no constructor in the class.

## 38) What is the output of the following Java program?

    class Test   
    {  
        int test_a, test_b;  
        Test(int a, int b)   
        {  
        test_a = a;   
        test_b = b;   
        }  
        public static void main (String args[])   
        {  
            Test test = new Test();   
            System.out.println(test.test_a+" "+test.test_b);  
        }  
    } 

 
**There is a compiler error in the program because there is a call to the default constructor in the main method which is not present in the class.** However, there is only one parameterized constructor in the class Test. Therefore, no default constructor is invoked by the constructor implicitly.
