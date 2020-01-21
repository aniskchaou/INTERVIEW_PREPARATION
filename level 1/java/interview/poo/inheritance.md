## 58) Why is Inheritance used in Java?

**Inheritance provides code reusability.** The derived class does not need to redefine the method of base class unless it needs to provide the specific implementation of the method.

**Inheritance provides data hiding.** The base class can hide some data from the derived class by making it private.


## 59) Which class is the superclass for all the classes?

**The object class** is the superclass of all other classes in Java.

## 60) Why is multiple inheritance not supported in java?

***To reduce the complexity and simplify the language***, multiple inheritance is not supported in java. 

## 61) What is aggregation?

 Aggregation is best described as a has-a relationship. For example, The aggregate class Employee having various fields such as age, name, and salary **also contains an object of Address class** having various fields such as Address-Line 1, City, State, and pin-code. 

In other words**, we can say that Employee (class) has an object of Address class.** Consider the following example.

Address.java

    public class Address {  
    String city,state,country;  
      
    public Address(String city, String state, String country) {  
        this.city = city;  
        this.state = state;  
        this.country = country;  
    }  
      
    } 

 
Employee.java

    public class Emp {  
    int id;  
    String name;  
    
    Address address;  
      
    public Emp(int id, String name,Address address) {  
        this.id = id;  
        this.name = name;  
        this.address=address;  
    }  
      
    void display(){  
    System.out.println(id+" "+name);  
    System.out.println(address.city+" "+address.state+" "+address.country);  
    }  
      
    public static void main(String[] args) {  
    Address address1=new Address("gzb","UP","india");  
    Address address2=new Address("gno","UP","india");  
      
    Emp e=new Emp(111,"varun",address1);  
    Emp e2=new Emp(112,"arun",address2);  
          
    e.display();  
    e2.display();  
          
    }  
    }  

Output

    111 varun
    gzb UP india
    112 arun
    gno UP india

 

## 62) What is composition?

. ***When an object contains the other object, if the contained object cannot exist without the existence of container object, then it is called composition.*** 

Example: **A class contains students. A student cannot exist without a class.** There exists composition between class and students.

## 63) What is the difference between aggregation and composition?

**Aggregation represents the weak relationship whereas composition represents the strong relationship.** For example, the bike has an indicator (aggregation), but the bike has an engine (composition).

## 64) Why does Java not support pointers?

The pointer is a variable that refers to the memory address. They are not used in Java because they are unsafe(unsecured) and complex to understand.

## 65) What is super in java?

The super keyword in Java is a reference variable that is used to refer to the immediate parent class object. 

    class Animal{  
    
    Animal(){System.out.println("animal is created");}  
    }  
    
    class Dog extends Animal{  
    
    Dog(){  
    System.out.println("dog is created");  
    }  
    
    }  
    
    class TestSuper4{  
    public static void main(String args[]){  
    Dog d=new Dog();  
    }  
    }  


Output:

    animal is created
    dog is created


## 66) How can constructor chaining be done by using the super keyword?

    class Person  
    {  
        String name,address;   
        int age;  
       
        public Person(int age, String name, String address)  
        {  
            this.age = age;  
            this.name = name;  
            this.address = address;  
        }  
    }  
    class Employee extends Person   
    {  
        float salary;  
       
        public Employee(int age, String name, String address, float salary)  
        {  
            super(age,name,address);  
            this.salary = salary;  
        }  
    }  
    public class Test   
    {  
        public static void main (String args[])  
        {  
            Employee e = new Employee(22, "Mukesh", "Delhi", 90000);  
            System.out.println("Name: "+e.name+" Salary: "+e.salary+" Age: "+e.age+" Address: "+e.address);  
        }  
    }  

Output

    Name: Mukesh Salary: 90000.0 Age: 22 Address: Delhi

## 67) What are the main uses of the super keyword?

There are the following uses of super keyword.

super can be used to refer to the immediate parent class instance variable.
super can be used to invoke the immediate parent class method.
super() can be used to invoke immediate parent class constructor.

## 68) What are the differences between this and super keyword?

The super keyword always points to the parent class contexts whereas this keyword always points to the current class context.

## 69) What is the output of the following Java program?

    class Person   
    {  
        public Person()   
        {  
            System.out.println("Person class constructor called");  
        }  
    }  
    public class Employee extends Person   
    {  
        public Employee()   
        {  
            System.out.println("Employee class constructor called");  
        }  
        public static void main (String args[])  
        {  
            Employee e = new Employee();  
        }  
    }  

Output

    Person class constructor called
    Employee class constructor called

Explanation

The super() **is implicitly invoked by the compiler if no super() or this() is included explicitly within the derived class constructor.** Therefore, in this case, The Person class constructor is called first and then the Employee class constructor is called.

## 70) Can you use this() and super() both in a constructor?

No, **because this() and super() must be the first statement in the class constructor.**

Example:

    public class Test{  
        Test()  
         {  
             super();   
             this();  
             System.out.println("Test class object is created");  
         }  
         public static void main(String []args){  
         Test t = new Test();  
         }  
    }  

Output:

    Test.java:5: error: call to this must be first statement in constructor

## 71)What is object cloning?

The object cloning is used to create the exact copy of an object. The clone() method of the Object class is used to clone an object. 

    protected Object clone() throws CloneNotSupportedException    
      
