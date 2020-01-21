## **What are the `features` in JAVA?**

-   Object-oriented
-   Platform independent:
-   Multi-threaded

## Variables
There is no default value for local variables, so local variables should be declared and an initial value should be assigned before the first use.

    public void pupAge() {
    
    //This will produce the following error while compiling it
    
    int age2;
    
    age = age + 7;
    
    System.out.println("Puppy age is : " + age);
    
    }
For numbers, the default value is 0; for Booleans, it is false; and for object references, it is null.

## Character
//The Character class offers a number of useful class (i.e., static) methods for manipulating characters

//You can create a Character object with the Character constructor

Character ch = new Character('a');

## **InnerStaticClass**
**does not have access to the instance variables and methods of the outer class.** 

    public class InnerStaticClassTutorial {
    
        private int b;
    
        public int getB() {
            return b;
        }
    
        static class Nested_Demo {
    
            private int a;
    
            public void my_method() {
    
                System.out.println("This is my nested class");
    
            }
    
        }
    
        public static void main(String args[]) {
    
            InnerStaticClassTutorial.Nested_Demo nested = new InnerStaticClassTutorial.Nested_Demo();
            nested.my_method();
            System.err.println(nested.a);
    
        }
    
    }

## **VariableArgumentsTutorial**

    public static void main(String args[]) {
    
    // Call method with variable args
    
    printMax(34, 3, 3, 2, 56.5);
    
    printMax(new double[]{1, 2, 3});
    
    }
    
    public static void printMax( double... numbers) {
    
    if (numbers.length == 0) {
    
    System.out.println("No argument passed");
    
    return;
    
    }

## **What are the Java `IDE’s`?**

-   Eclipse
-   NetBeans

## **How garbage collection is done in Java?**

In java, when  `an object is not referenced any more, garbage collection takes place and the object is destroyed automatically.`  For **automatic garbage** collection java calls either System.gc() method or Runtime.gc() method.

## **What will be the output of following piece of code?**

```
public class operatorExample  {

public static void main(String args[]) {

int x = 4;

system.out.println(x++);
}}

```

**In this case postfix ++ operator is used which  `first returns the value and then increments`. Hence it's output will be 4.**

## **What are the two `environment variables` that must be set in order to run any Java programs**

1.  PATH variable
2.  CLASSPATH variable

## **What's the difference between comparison done by equals method and == operator?**

 - **equals()** is used to compare the **contents of two string objects**
   and returns true if the two have same value
 - **== operator** compares **the references of two string objects**.

        String s1 = "h";
        String s2 = "h" ;
        System.out.println(s1 == s2); 
        System.out.println(s1.equals(s2));
 
//true 
 // true

     String s1 = new String("HELLO"); 
            String s2 = new String("HELLO"); 
            System.out.println(s1 == s2); 
            System.out.println(s1.equals(s2));

//false
//true               
## I want my class to be developed in such a way that no other class (even derived class) can create its objects. How can I do so?

**`If we declare the constructor of a class as private,`**  it will not be accessible by any other class and hence, no other class will be able to instantiate it and formation of its object will be limited to itself only.

    class A {
        private A(){}
    }
    
    class B{
        
        public static void main(String[] args) {
            A a=new A(); //error
        }
    }

## **How objects are stored in Java?**

In java, each object when created  **`gets a memory space from a heap`**.

## I have multiple constructors defined in a class. Is it possible to call a constructor from another constructor's body?

, it's possibl**`e to call one constructor from the body of another one using this().`**

    class A {
       
        private int a;
       
        A(int a)
        {
            this();
            this.a=a;
        }
         A(){}
        
       
    }

## **What's the base class in Java from which all classes are derived?**


 java.lang.object

## What happens at compile time?

At compile time, java file is compiled by Java Compiler (It does not interact with OS) and converts the java code into bytecode.

## Java Variable

 - **Widening**

    int a=10;  
    float f=a;  
    System.out.println(a);  
    System.out.println(f);

10
10.0

 - **Typecasting**

    float f=10.5f;  
    //int a=f;//Compile time error  
    int a=(int)f;  
    System.out.println(f);  
    System.out.println(a); 

10.5
10

 - **Overflow**

 

    int a=130;  
    byte b=(byte)a;  
    System.out.println(a);  
    System.out.println(b); 

130
-126


## Difference between JDK, JRE, and JVM


**JVM**
JVM (Java Virtual Machine) is an abstract machine. It is called a virtual machine because it doesn't physically exist. **It can also run those programs which are written in other languages and compiled to Java bytecode.**


The JVM performs the following main tasks:

 - Loads code
 - Verifies code
 - Executes code
 - Provides runtime environment

 
**JRE**
JRE is an acronym for Java Runtime Environment. 

 - provide the runtime environment(JVM)
 - contains a set of libraries + other files that JVM uses at runtim

**JDK**
JDK is an acronym for Java Development Kit.

 - It contains JRE 
 - development tools(interpreter/loader (java)
 - a compiler (javac)
 - an archiver (jar)
 - a documentation generator (Javadoc))

## C++ Java

 - **platform dependence**

Platform-independent  C++ is platform-dependent.
Java is platform-independent.

 - **inheritance**

Multiple inheritance  C++ supports multiple inheritance.
  Java doesn't support multiple inheritance through class. It can be achieved by interfaces in java.

 - **pointer**

Pointers  C++ supports pointers. You can write pointer program in C++.  
Java supports pointer internally. However, you can't write the pointer program in java. 


## Java Continue


    for(int i=1;i<=10;i++){  
        if(i==5){  
            //using continue statement  
            continue;//it will skip the rest statement  
        }  
        System.out.println(i);  
    }  

1
2
3
4
6
7
8
9
10

## Java Break

       for(int i=1;i<=10;i++){  
            if(i==5){  
                //breaking the loop  
                break;  
            }  
            System.out.println(i);  
        }  

1
2
3
4

## Difference between `String`, `String Builder`, and `String Buffer`.

 - **String:**  String variables are stored in “constant string pool”. Once the string reference changes  **`the old value that exists in
   the “constant string pool”, it cannot be erased.`**
 - **String Buffer**  Here string values are stored in a stack. If the values are changed then the new value replaces the older value. (Synchronised)
 - **String Builder**  This is same as String Buffer except for the String Builder which is not threaded safety that is not synchronized. (Not synchronised)
   So obviously performance is fast.

**example**   

     StringBuilder sb=new StringBuilder("ab");
           sb.append("c");
            System.out.println(sb.capacity());//18
            System.out.println(sb.length()); //3
            System.out.println(sb.insert(3,"R")); //abcR

## **Is String a data type in java?**

String is not a primitive data type in java.  **`When a string is created in java, it's actually an object of Java.Lang.`**

## Why Strings in Java are called as Immutable?

In java, string objects are called immutable as once value has been assigned to a string,  **`it can't be changed and if changed, a new object is created`**.

In below example, reference str refers to a string object having value "Value one".

```
String str="Value One";

```

When a new value is assigned to it, a new String object  **gets created and the reference is moved to the new object.**


    str="New Value";
## String Methods

        String str = new String("abcd");
        String str1 = new String("ABCD");
        System.out.println(str.equals(str1)); //false
        System.out.println(str.equalsIgnoreCase(str1));  //true
        System.out.println(str.charAt(0)); //a
        System.out.println(str.length()); //4
        System.out.println(str.contains("b"));//true
        System.out.println(str.indexOf("b"));//1
        System.out.println(str.concat("e"));//abcde
        System.out.println(str.replace("a", "z"));//zbcd
        System.out.println(str.isEmpty()); //false
        System.out.println(str.substring(2));//cd
        System.out.println(str.toUpperCase()); //ABCD
        System.out.println(str.trim()); //abcd
        String[] strs = str.split("");
## Conversion

**String to int**

     //Declaring String variable
     String s="200";
     //Converting String into int using Integer.parseInt()
     int i=Integer.parseInt(s);
 **int to String**

     int i=10;
     String s=String.valueOf(i);//Now it will return "10"
## Date

 

    Date d = new Date();
            Date d2 = new Date("2006/01/01");
    
            String str = String.format("%tc", d);
            System.out.printf(str); //mar. janv. 21 15:49:38 CET 2020
            System.out.println(d.after(d2));//true
            System.out.println(d2.after(d));//false
            System.out.println(d.compareTo(d2));//1
            System.out.println(d2.compareTo(d));//-1
