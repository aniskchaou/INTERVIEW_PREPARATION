## 39) What is the static variable?

The static variable is used to refer to the common property of all objects (that is not unique for each object)

    //Program of static variable  
      
    class Student8{  
       int rollno;  
       String name;  

       static String college ="ITS";  
         
       Student8(int r,String n){  
       rollno = r;  
       name = n;  
       }  

     void display (){
     System.out.println(rollno+" "+name+" "+college);
     }  
      
     public static void main(String args[]){ 
      
     Student8 s1 = new Student8(111,"Karan");  
     Student8 s2 = new Student8(222,"Aryan");  
     s1.display();  
     s2.display();  
     }  
    }  


Output:

    111 Karan ITS
           222 Aryan ITS


## 40) What is the static method?

***A static method belongs to the class*** rather than the object.



## 41) What are the restrictions that are applied to the Java static methods?


The static method ***can not use non-static data member or call the non-static method directly.***
**this and super cannot be used in static context as they are non-static**.

## 42) Why is the main method static?

Because the object is not required to call the static method. ***If we make the main method non-static, JVM will have to create its object first and then call main() method which will lead to the extra memory allocation.*** 

## 43) Can we override the static methods?

No, **we can't override static methods.**

## 44) What is the static block?

***Static block is used to initialize the static data member. It is executed before the main method, at the time of classloading.***

    class A2{ 
     
      static{
      System.out.println("static block is invoked");}  
      public static void main(String args[]){  
       System.out.println("Hello main");  
      }  
    }  


Output: 

    static block is invoked
    Hello main



## 45) Can we execute a program without main() method?

Ans) Yes, one of the ways to execute the program without the main method is using static block. 

## 46) What if the static modifier is removed from the signature of the main method?

Program compiles. **However, at runtime, It throws an error "NoSuchMethodError."**


## 48) Can we make constructors static?

As we know that the static context (method, block, or variable) belongs to the class, not the object. ***Since Constructors are invoked only when the object is created, there is no sense to make the constructors static.*** However, if you try to do so, the compiler will show the compiler error.

## 49) Can we make the abstract methods static in Java?

In Java, if we make the abstract methods static, It will become the part of the class, and we can directly call it which is unnecessary. Calling an undefined method is completely useless therefore it is not allowed.

## 50) Can we declare the static variables and methods in an abstract class?

Yes, we can declare static variables and methods in an abstract method.

    abstract class Test  
    {  
        static int i = 102;  
        static void TestMethod()  
        {  
            System.out.println("hi !! I am good !!");  
        }  
    }  
    public class TestClass extends Test   
    {  
        public static void main (String args[])  
        {  
            Test.TestMethod();  
            System.out.println("i = "+Test.i);  
        }  
    }  

Output

    hi !! I am good !!
    i = 102


## 51) What is this keyword in java?

The this keyword ***is a reference variable that refers to the current object.*** 


## 53) Can we assign the reference to this variable?

***No, this cannot be assigned to any value because it always points to the current class object and this is the final reference in Java.*** However, if we try to do so, the compiler error will be shown. Consider the following example.

    public class Test  
    {  
        public Test()  
        {  
            this = null;   
            System.out.println("Test class constructor called");  
        }  
        public static void main (String args[])  
        {  
            Test t = new Test();  
        }  
    }  

Output

    Test.java:5: error: cannot assign a value to final variable this
            this = null; 
            ^
    1 error


## 54) Can this keyword be used to refer static members?

Yes, **It is possible to use this keyword to refer static members** because this is just a reference variable which refers to the current class object. 

    public class Test   
    {  
        static int i = 10;   
        public Test ()  
        {  
            System.out.println(this.i);      
        }  
        public static void main (String args[])  
        {  
            Test t = new Test();  
        }  
    }  

Output

10

## 55) How can constructor chaining be done using this keyword?

Constructor chaining **enables us to call one constructor from another constructor of the class with respect to the current class object.** 

    public class Employee  
    {  
        int id,age;   
        String name, address;  
        public Employee (int age)  
        {  
            this.age = age;  
        }  
        public Employee(int id, int age)  
        {  
            this(age);  
            this.id = id;  
        }  
        public Employee(int id, int age, String name, String address)  
        {  
            this(id, age);  
            this.name = name;   
            this.address = address;   
        }  
        public static void main (String args[])  
        {  
            Employee emp = new Employee(105, 22, "Vikas", "Delhi");  
            System.out.println("ID: "+emp.id+" Name:"+emp.name+" age:"+emp.age+" address: "+emp.address);  
        }  
          
    }  

Output

    ID: 105 Name:Vikas age:22 address: Delhi


