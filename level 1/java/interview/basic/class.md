
## 213) What is the purpose of using java.lang.Class class?

Provides methods to get the metadata of a class at runtime.
Provides methods to examine and change the runtime behavior of a class.

## 214) What are the ways to instantiate the Class class?

There are three ways to instantiate the Class class.

forName() method of Class class: The forName() method is used to load the class dynamically.

getClass() method of Object class: It returns the instance of Class class.

the .class syntax: If a type is available, but there is no instance then it is possible to obtain a Class by appending ".class" to the name of the type. It can be used for primitive data type also.

## 215) What is the output of the following Java program?

    class Simple{    
     public Simple()  
     {  
       System.out.println("Constructor of Simple class is invoked");  
     }  
     void message(){System.out.println("Hello Java");}    
    }    
        
    class Test1{    
     public static void main(String args[]){    
      try{    
      Class c=Class.forName("Simple");    
      Simple s=(Simple)c.newInstance();    
      s.message();    
      }catch(Exception e){System.out.println(e);}    
     }    
    }

    
Output

    Constructor of Simple class is invoked
    Hello Java

Explanation

The newInstance() method of the Class class is used to invoke the constructor at runtime. In this program, the instance of the Simple class is created.



## 220) What is the output of the below Java program?

    public class Test1  
    {  
      public static void main(String[] args) {  
      Integer i = new Integer(201);  
      Integer j = new Integer(201);  
      if(i == j)  
      {  
        System.out.println("hello");  
      }  
      else   
      {  
        System.out.println("bye");  
      }  
      }  
    }  

Output

    bye

Explanation

The Integer class caches integer values from -127 to 127. Therefore, the Integer objects can only be created in the range -128 to 127. **The operator == will not work for the value greater than 127; thus bye is printed.**





## 225) What is the purpose of the System class?

The purpose of the System class is to provide access to system resources such as standard input and output. 



## 227) What is a singleton class?

Singleton class is the class which can not be instantiated more than once. 

    class Singleton{  
        private static Singleton single_instance = null;  
        int i;  
         private Singleton ()  
         {  
             i=90;  
         }  
         public static Singleton getInstance()  
         {  
             if(single_instance == null)  
             {  
                 single_instance = new Singleton();  
             }  
             return single_instance;  
         }  
    }  
    public class Main   
    {  
        public static void main (String args[])  
        {  
            Singleton first = Singleton.getInstance();  
            System.out.println("First instance integer value:"+first.i);  
            first.i=first.i+90;  
            Singleton second = Singleton.getInstance();  
            System.out.println("Second instance integer value:"+second.i);  
        }  
    }  
      

## 147) What is the output of the following Java program?

    public class Main   
    {  
        void a()  
        {  
            try{  
            System.out.println("a(): Main called");  
            b();  
            }catch(Exception e)  
            {  
                System.out.println("Exception is caught");  
            }  
        }  
        void b() throws Exception  
        {  
         try{  
             System.out.println("b(): Main called");  
             c();  
         }catch(Exception e){  
             throw new Exception();  
         }  
         finally   
         {  
             System.out.println("finally block is called");  
         }  
        }  
        void c() throws Exception   
        {  
            throw new Exception();  
        }  
      
        public static void main (String args[])  
        {  
            Main m = new Main();  
            m.a();  
        }  
    }  

Output

    a(): Main called
    b(): Main called
    finally block is called
    Exception is caught

Explanation

In the main method, a() of Main is called which prints a message and call b(). The method b() prints some message and then call c(). The method c() throws an exception which is handled by the catch block of method b. However, It propagates this exception by using throw Exception() to be handled by the method a(). As we know, finally block is always executed therefore the finally block in the method b() is executed first and prints a message. At last, the exception is handled by the catch block of the method a().

## 148) What is the output of the following Java program?

    public class Calculation   
    {  
        int a;   
        public Calculation(int a)  
        {  
            this.a = a;  
        }  
        public int add()  
        {  
            a = a+10;   
            try   
            {  
                a = a+10;   
                try   
                {  
                    a = a*10;   
                    throw new Exception();   
                }catch(Exception e){  
                    a = a - 10;  
                }  
            }catch(Exception e)  
            {  
                a = a - 10;   
            }  
            return a;  
        }  
          
        public static void main (String args[])  
        {  
            Calculation c = new Calculation(10);  
            int result = c.add();  
            System.out.println("result = "+result);  
        }  
    }  

Output

    result = 290

**Explanation**

The second try block throws the exception which is caught by the catch block associated with this try block. The catch block again alters the value of a by decrementing it by 10 to make it 290. 



## 169) What is a nested class?

The nested class can be defined as the class which is defined inside another class or interface. 

    class Java_Outer_class{    
     //code    
     class Java_Nested_class{    
      //code    
     }    
    }

    
      
There are two types of nested classes, static nested class, and non-static nested class. The non-static nested class can also be called as inner-class


## 170) What are the disadvantages of using inner classes?

There are the following main disadvantages of using inner classes.

Inner classes increase the total number of classes used by the developer and therefore increases the workload of JVM since it has to perform some routine operations for those extra classes which result in slower performance.


## 171) What are the types of inner classes (non-static nested class) used in Java?


Member Inner Class  A class created within class and outside method.
Anonymous Inner Class A class created for implementing an interface or extending class. Its name is decided by the java compiler.
Local Inner Class A class created within the method.



## 174) How many class files are created on compiling the OuterClass in the following program?

    public class Person {  
    String name, age, address;  
    class Employee{  
      float salary=10000;  
    }  
    class BusinessMen{  
      final String gstin="£4433drt3$";   
    }  
    public static void main (String args[])  
    {  
      Person p = new Person();  
    }  
    }  

3 class-files will be created named as Person.class, Person$BusinessMen.class, and Person$Employee.class.
## 176) What is the nested interface?

An Interface that is declared inside the interface or class is known as the nested interface. 

    interface interface_name{    
     ...    
     interface nested_interface_name{    
      ...    
     }    
    }   

  
 