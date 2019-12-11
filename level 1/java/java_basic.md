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

isLetter() 
isDigit() 
isWhitespace() 
isUpperCase() 
isLowerCase() 
toUpperCase()
toLowerCase()
toString()

## **InnerStaticClass**
does not have access to the instance variables and methods of the outer class. 

    public class InnerStaticClassTutorial {
    
    static class Nested_Demo {
    
    public void my_method() {
    
    System.out.println("This is my nested class");
    
    }
    
    }
    
    public static void main(String args[]) {
    
    InnerStaticClassTutorial.Nested_Demo nested = new InnerStaticClassTutorial.Nested_Demo();
    
    nested.my_method();
    
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

## **How objects are stored in Java?**

In java, each object when created  **`gets a memory space from a heap`**.

## I have multiple constructors defined in a class. Is it possible to call a constructor from another constructor's body?

, it's possibl**`e to call one constructor from the body of another one using this().`**

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

Difference between HashMap and HashTable. Difference between HashSet and TreeSet.

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

**char charAt(int index)**  returns char value for the particular index
**int length()**  returns string length
**static String format(String format, Object... args)** returns a formatted string.
**String substring(int beginIndex)**  returns substring for given begin index.
**boolean contains(CharSequence s)**  returns true or false after matching the sequence of char value.
**boolean equals(Object another)**  checks the equality of string with the given object.
**boolean isEmpty()** checks if string is empty.
**String concat(String str)** concatenates the specified string.
**String replace(char old, char new)**  replaces all occurrences of the specified char value.
**static String equalsIgnoreCase(String another)**  compares another string. It doesn't check case.
**String[] split(String regex)**  returns a split string matching regex.
**String intern()** returns an interned string.
**int indexOf(int ch)** returns the specified char value index.
**String toLowerCase()**  returns a string in lowercase.
**String toUpperCase()**  returns a string in uppercase.
**String trim()** removes beginning and ending spaces of this string.
**static String valueOf(int value)**

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

    Date date = new Date();
    System.out.println(date.toString());
    String str = String.format("Current Date/Time : %tc", date );

System.out.printf(str);
boolean after(Date date) 
boolean before(Date date) 
int compareTo(Object obj) 
long getTime( ) 
void setTime(long time) 