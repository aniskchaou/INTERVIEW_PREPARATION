### 1) What is Spring?

It is a lightweight, loosely coupled and integrated framework for developing enterprise applications in java.

----------

### 2) What are the advantages of spring framework?

1.  Predefined Templates
2.  Loose Coupling
3.  Easy to test
4.  Lightweight
5.  Fast Development
6.  Powerful Abstraction
7.  Declarative support


----------

### 3) What are the modules of spring framework?

1.  Test
2.  Spring Core Container
3.  AOP, Aspects and Instrumentation
4.  Data Access/Integration
5.  Web


----------

### 4) What is IOC and DI?

IOC (Inversion of Control) and DI (Dependency Injection) is a design pattern to provide loose coupling. It removes the dependency from the program.

Let's write a code without following IOC and DI.

    1.  public  class Employee{
    2.  Address address;
    3.  Employee(){
    4.  address=new Address();//creating instance
    5.  }
    6.  }

Now, there is dependency between Employee and Address because Employee is forced to use the same address instance.

Let's write the IOC or DI code.

    1.  public  class Employee{
    2.  Address address;
    3.  Employee(Address address){
    4.  this.address=address;//not creating instance
    5.  }
    6.  }

Now, there is no dependency between Employee and Address because Employee is not forced to use the same address instance. It can use any address instance.

----------

### 5) What is the role of IOC container in spring?

IOC container is responsible to:

-   create the instance
-   configure the instance, and
-   assemble the dependencies


----------

### 6) What are the types of IOC container in spring?

There are two types of IOC containers in spring framework.

1.  BeanFactory
2.  ApplicationContext




### 9) What is autowiring in spring? What are the autowiring modes?

Autowiring enables the programmer to inject the bean automatically. We don't need to write explicit injection logic.

Let's see the code to inject bean using dependency injection.

     < bean id="emp"  class="com.javatpoint.Employee" autowire="byName" />



### 18) What is AOP?

AOP is an acronym for Aspect Oriented Programming. It is a methodology that divides the program logic into pieces or parts or concerns.

It increases the modularity and the key unit is Aspect.


### 33) What is the front controller class of Spring MVC?

The  **DispatcherServlet**  class works as the front controller in Spring MVC.



### 34) What does @Controller annotation?

The  **@Controller**  annotation marks the class as controller class. It is applied on the class.

----------

### 35) What does @RequestMapping annotation?

The  **@RequestMapping**  annotation maps the request with the method. It is applied on the method.
