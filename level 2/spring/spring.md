## **What Is Spring?**
It is a lightweight, loosely coupled and integrated framework for developing enterprise applications in java.

## Modules


-   **Spring Security**
-   **Spring AOP**
-   **Spring Data** : ORM, JDBC, OXM, JMS
-   **Spring Test :** JUnit and TestNG
- **Spring Web (MVC)** : Web-Servlet, Web-Struts and Web-Portlet
- **Spring Core** : Beans, Context, Expression Language

## Spring Core :

#### Core and Beans

These modules provide IOC and Dependency Injection features.

#### Context

This module supports internationalization (I18N), EJB, JMS, Basic Remoting.
#### Expression Language

It is an extension to the EL defined in JSP.

## dependency injection
Any application is composed of many objects that collaborate with each other to perform some useful stuff. Traditionally each object is responsible for obtaining its own references to the dependent objects (dependencies) it collaborate with. This leads to highly coupled classes and hard-to-test code.

For example, consider a  `Car`  object.

A  `Car`  depends on wheels, engine, fuel, battery, etc. to run. Traditionally we define the brand of such dependent objects along with the definition of the  `Car`  object.

**Without Dependency Injection (DI):**

```
class Car{
  private Wheel wh = new NepaliRubberWheel();
  private Battery bt = new ExcideBattery();

  //The rest
}
```

Here, the  `Car`  object  _is responsible for creating the dependent objects._

What if we want to change the type of its dependent object - say  `Wheel`  - after the initial  `NepaliRubberWheel()`  punctures? We need to recreate the Car object with its new dependency say  `ChineseRubberWheel()`, but only the  `Car`  manufacturer can do that.

**_Then what does the  `Dependency Injection`  do for us...?_**

When using dependency injection, objects are given their dependencies  _at run time rather than compile time (car manufacturing time)_. So that we can now change the  `Wheel`  whenever we want. Here, the  `dependency`  (`wheel`) can be injected into  `Car`  at run time.

**After using dependency injection:**

Here, we are  **injecting**  the  **dependencies**  (Wheel and Battery) at runtime. Hence the term :  _Dependency Injection._

```
class Car{
  private Wheel wh; // Inject an Instance of Wheel (dependency of car) at runtime
  private Battery bt; // Inject an Instance of Battery (dependency of car) at runtime
  Car(Wheel wh,Battery bt) {
      this.wh = wh;
      this.bt = bt;
  }
  //Or we can have setters
  void setWheel(Wheel wh) {
      this.wh = wh;
  }
}
```

## AOP (Aspect-Oriented programming)
Aspect Oriented Programming is sensibly new and it is not a replacement for Object Oriented Programming. In fact, AOP is another way of organizing your Program Structure.
for example, when a method is execute, **Spring AOP can hijack the executing method, and add extra functionality before or after the method execution.**

**For example:**  Logging, Transaction and security are some  **Aspects**. In Logging we may have different aspect i.e. time calculation logging, simple in and out message logging and so on..


To be more clear I will use some diagrams:

1.  What is Aspect?
    
    ```
    |---------------------|------------------|------------------|
    |      Aspect         =     Point cut    +  Advice          |
    |---------------------|------------------|------------------|
    |                     | Where the aspect | What code is     |
    |                     |  is applied      |  executed.       |
    |---------------------|------------------|------------------|
    ```
    
    **Aspect = Point cut + Advice**
    
2.  Type of Advice methods
    
    [![enter image description here](https://i.stack.imgur.com/Fc9GJ.jpg)](https://i.stack.imgur.com/Fc9GJ.jpg)
    #### Aspect and pointcut expression
   

    ```` @Aspect
    public class EmployeeCRUDAspect {
          
        @Before("execution(* EmployeeManager.getEmployeeById(..))")         //point-cut expression
        public void logBeforeV1(JoinPoint joinPoint)
        {
            System.out.println("EmployeeCRUDAspect.logBeforeV1() : " + joinPoint.getSignature().getName());
        }
    }
#### Methods (joint points)

    @Component
    public class EmployeeManager
    {
        public EmployeeDTO getEmployeeById(Integer employeeId) {
            System.out.println("Method getEmployeeById() called");
            return new EmployeeDTO();
        }
    }
#### Main

    public class TestAOP
    {
        @SuppressWarnings("resource")
        public static void main(String[] args) {
      
            ApplicationContext context = new ClassPathXmlApplicationContext
                                ("com/howtodoinjava/demo/aop/applicationContext.xml");
     
            EmployeeManager manager = context.getBean(EmployeeManager.class);
      
            manager.getEmployeeById(1);
        }
    }
#### Output

    EmployeeCRUDAspect.logBeforeV1() : getEmployeeById
    Method getEmployeeById() called

## **What Is Spring Boot?**

Spring Boot **is basically an extension of the Spring framework** which **eliminated the boilerplate configurations** required for setting up a Spring application.

## What is the defference between SpringBoot ans Spring?
1.  Spring Boot **reduces the need to write a lot of configuration** and boilerplate code.
2.  It has an **opinionated view on Spring Platform and third-party libraries** so you can get started with minimum effort.
3.  Easy to create standalone applications **with embedded Tomcat/Jetty/Undertow**.
 ## What is autowiring in spring? What are the autowiring modes?

Autowiring enables the programmer to inject the bean automatically. We don't need to write explicit injection logic.

Let's see the code to inject bean using dependency injection.

```
 < bean id="emp"  class="com.javatpoint.Employee" autowire="byName" />
```
 
