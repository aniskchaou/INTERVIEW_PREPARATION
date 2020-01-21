## **What is mean by `Exception`?**

Ans: An Exception is a problem that can occur  `during the normal flow of an execution.`  Exceptions are a subclass of  `java.lang.Exception`.

```
try{

//Risky  codes  are  surrounded  by  this block

}catch(Exception e){

//Exceptions  are  caught in catch block

}

```

## **What are the types of Exceptions?**

**Checked Exception:**  These exceptions  `are checked by the compiler at the time of compilation`. E.g. ClassNotFound Exception

**Unchecked Exception:**  These exceptions  `are not checked during the compile time by the compiler`.

It includes:

-   **Arithmetic**  Exception
-   **ArrayIndexOutOfBounds**  Exception

## **What are the different `ways` to handle exceptions?**

**Using try/catch:**

A risky code is surrounded by try block. If an exception occurs, then it is caught by the catch block which is followed by the try block.

```
class  Manipulation{

public  static  void  main(String[] args){
add();
}

Public void  add(){
    try{
    addition();
    }catch(Exception e){
    e.printStacktrace();
    }
}

}

```

**By declaring throws keyword:**

At the end of the method, we can declare the exception using throws keyword.

```
class  Manipulation{

public  static  void  main(String[] args){
add();
}

public  void  add() throws  Exception{
addition();
}
}

```

## **What are Exception handling keywords in Java?**

**try:**

When a risky code is surrounded by a try block. An exception occurring in the try block is caught by a catch block.

**catch:**

This is followed by try block. Exceptions are caught here.

**finally:**

This is followed either by try block (or) catch block. This block gets executed regardless of an exception.  `So generally clean up codes are provided here.`

## **Explain about Exception Propagation.**

```
public  class  Manipulation{
public  static  void  main(String[] args){
add();
}
public  void  add(){
addition();
}

```

**`If an exception occurred in the addition() method is not caught, then it moves to the method add(). Then it is moved to the main() method and then it will stop the flow of execution.`**  It is called Exception Propagation.

## **Is there any way to skip Finally block of exception even if some exception occurs in the exception block?**

System.exit(0);

## **How can an exception be thrown manually by a programmer?**

In order to throw an exception in a block of code manually, throw keyword is used. Then this exception is caught and handled in the catch block.

```
public void topMethod() { 
    try {
     excMethod();
      }catch (ManualException e) {
    }
}

public void excMethod { 
String name = null; 
if (name == null) { 
throw (new ManualException("Exception thrown manually "); 
}

```