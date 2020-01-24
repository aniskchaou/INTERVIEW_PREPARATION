
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
 

**Spring Boot:** Spring Boot is a module of Spring Framework. **It allows us to build a stand-alone application with minimal or zero configurations.** 

# Spring Boot Architecture

Spring Boot follows a layered architecture **in which each layer communicates with the layer directly below or above (hierarchical structure) it.**

Before understanding the  **Spring Boot Architecture**, we must know the different layers and classes present in it. There are  **four**  layers in Spring Boot are as follows:

-   **Presentation Layer**
-   **Business Layer**
-   **Persistence Layer**
-   **Database Layer**

![Spring Boot Architecture](https://static.javatpoint.com/springboot/images/spring-boot-architecture.png)

**Presentation Layer:**  In short, it consists of  **views**  i.e., frontend part.

**Business Layer:**  It also performs  **authorization**  and  **validation**.

**Persistence Layer:**  The persistence layer contains all the  **storage logic**  and translates business objects from and to database rows.

**Database Layer:**  In the database layer,  **CRUD**  (create, retrieve, update, delete) operations are performed.

## Spring Boot Flow Architecture

![Spring Boot Architecture](https://static.javatpoint.com/springboot/images/spring-boot-architecture2.png)


## Spring Initializr

**Spring Initializr**  is a  **web-based tool**  provided by the Pivotal Web Service. 

**With the help of  **Spring Initializr**, we can easily generate the structure of the  **Spring Boot Project**.**

## SpringBootExampleApplication

**SpringBootExampleApplication.java**

    1.  package com.javatpoint.springbootexample;
    2.  import org.springframework.boot.SpringApplication;
    3.  import org.springframework.boot.autoconfigure.SpringBootApplication;
    4.  
    5. @SpringBootApplication
    6.  public  class SpringBootExampleApplication
    7.  {
    8.  public  static  void main(String[] args)
    9.  {
    10.  SpringApplication.run(SpringBootExampleApplication.class, args);
    11.  }
    12.  }

# Spring Boot Annotations

Spring Boot Annotations is a form of **metadata that provides data about a program.** 

## Core Spring Framework Annotations

## **@Required:**


The @Required annotation in spring is a method-level annotation applied to the setter method of a bean property and thus making the setter-injection mandatory.

**Example**

    1.  public  class Machine
    2.  {
    3.  private Integer cost;
    4.  @Required
    5.  public  void setCost(Integer cost)
    6.  {
    7.  this.cost = cost;
    8.  }
    9.  public Integer getCost()
    10.  {
    11.  return cost;
    12.  }
    13.  }

## **@Autowired:**

  When we use @Autowired annotation, the spring container auto-wires the bean by matching data-type.
**Autowiring feature of spring framework enables you to inject the object dependency implicitly. It internally uses setter or constructor injection.**

**Example**

    1.  @Component
    2.  public  class Customer
    3.  {
    4.  private Person person;
    5.  @Autowired
    6.  public Customer(Person person)
    7.  {
    8.  this.person=person;
    9.  }
    10.  }

## **@Configuration:**

Spring Configuration annotation indicates that the class has @Bean definition methods. So Spring container can process the class and generate Spring Beans to be used in the application.

**Example**

    1.  @Configuration
    2.  public  class Vehicle
    3.  {
    4.  @Bean
    5.   Vehicle engine()
    6.  {
    7.  return  new Vehicle();
    8.  }
    9.  }

## example

    @Configuration
    public class MyConfiguration {
    
        @Bean
        public MyBean myBean() {
            return new MyBean();
        }
        
    }

    public class MySpringApp {
    
        public static void main(String[] args) {
            AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext();
            ctx.register(MyConfiguration.class);
            ctx.refresh();
    
            // MyBean mb1 = ctx.getBean(MyBean.class);
    
            // MyBean mb2 = ctx.getBean(MyBean.class);
    
            ctx.close();
        }
    
    }

## **@ComponentScan:**

  It is used when we want to scan a package for beans. **It is used with the annotation @Configuration.** We can also specify the base packages to scan for Spring Components.

**Example**

    1.  @ComponentScan(basePackages = "com.javatpoint")
    2.  @Configuration
    3.  public  class ScanComponent
    4.  {
    5.  // ...
    6.  }

## **@Bean:**

 It is a method-level annotation.

**Example**

    1.  @Bean
    2.  public BeanExample beanExample()
    3.  {
    4.  return  new BeanExample ();
    5.  }

## Spring Framework Stereotype Annotations

## **@Component:**

  It is a class-level annotation. **It is used to mark a Java class as a bean.** A Java class annotated with  **@Component**  is found during the classpath. The Spring Framework pick it up and configure it in the application context as a  **Spring Bean**.

**Example**

    1.  @Component
    2.  public  class Student
    3.  {
    4.  .......
    5.  }

## example

    @SpringBootApplication
    public class DemoApplication {
    
        public static void main(String[] args) {
            ConfigurableApplicationContext applicationContext = SpringApplication.run(DemoApplication.class, args);
            ComponentDemo componentDemo = (ComponentDemo) applicationContext.getBean("componentDemo");
            System.out.println(componentDemo.getValue());
        }
    }
    
    @Component
    class ComponentDemo {
        public String getValue() {
            return "Hello World";
        }
    }

## **@Controller:**

 The @Controller is a class-level annotation. It is a specialization of  **@Component**. **It marks a class as a web request handler. It is often used to serve web pages.** By default, it returns a string that indicates which route to redirect. It is mostly used with  **@RequestMapping**  annotation.

**Example**

    1.  @Controller
    2.  @RequestMapping("books")
    3.  public  class BooksController
    4.  {
    5.  @RequestMapping(value = "/{name}", method = RequestMethod.GET)
    6.  public Employee getBooksByName()
    7.  {
    8.  return booksTemplate;
    9.  }
    10.  }

## **@Service:**

 It is also used at class level. It tells the Spring that class contains the  **business logic**.

**Example**

    1.  package com.javatpoint;
    2.  @Service
    3.  public  class TestService
    4.  {
    5.  public  void service1()
    6.  {
    7.  //business code
    8.  }
    9.  }

## **@Repository:**

  It is a class-level annotation. **The repository is a  **DAOs**  (Data Access Object) that access the database directly. The repository does all the operations related to the database.**

    1.  package com.javatpoint;
    2.  @Repository
    3.  public  class TestRepository
    4.  {
    5.  public  void delete()
    6.  {
    7.  //persistence code
    8.  }
    9.  }

## Spring Boot Annotations

-   **@EnableAutoConfiguration:**  It auto-configures the bean that is present in the classpath and configures it to run the methods.
-   **@SpringBootApplication:**  It is a combination of three annotations  **@EnableAutoConfiguration, @ComponentScan,**  and  **@Configuration**.

### Spring MVC and REST Annotations

-   **@RequestMapping:**  It is used to map the  **web requests**. It has many optional elements like  **consumes, header, method, name, params, path, produces**, and  **value**. We use it with the class as well as the method.

**Example**

    1.  @Controller
    2.  public  class BooksController
    3.  {
    4. 
    5.  @RequestMapping("/computer-science/books")
    6.  public String getAllBooks(Model model)
    7.  {
    8.  
    9.  return  "bookList";
    10.  }

## GET

## @GetMapping

    @GetMapping
        List<Produit> getProduit(){
            return produitService.getProduit();
        }

## @RequestMapping(method = RequestMethod.GET)

    @RequestMapping(value="/contacts",method=RequestMethod.GET)
       private List<Contact> getAll() {
        return cr.findAll();
       }
      
      @RequestMapping(value="/contacts/{id}",method=RequestMethod.GET)
       private Optional<Contact> getContactById(@PathVariable Long id) {
        return cr.findById(id);
       }

## POST

 

## @PostMapping

       @PostMapping
        void addProduit(@RequestBody Produit produit) {
            produitService.addProduit(produit);
        }

## @RequestMapping(method = RequestMethod.POST)

     @RequestMapping(value="/contacts",method=RequestMethod.POST)
       private Contact save(@RequestBody Contact c) {
        return cr.save(c);
       }

## PUT

  

## @PutMapping

    @PutMapping
        void updateProduit( @RequestBody Produit produit) {
            produitService.updateProduit(produit);
        }
      

## @RequestMapping(method = RequestMethod.PUT)

 

        @RequestMapping(value="/contacts/{id}",method=RequestMethod.PUT)
       private Contact update(@PathVariable Long id,@RequestBody Contact c) {
           c.setId(id);
        return cr.save(c);
       }

## DELETE

## @DeleteMapping:

    @DeleteMapping("/{id}")
        void deleteProduit(@PathVariable Long id) {
            produitService.removeProduitById(id);
        }

  

## @RequestMapping(method = RequestMethod.DELETE)

     @RequestMapping(value="/contacts/{id}",method=RequestMethod.DELETE)
       private boolean delete(@PathVariable Long id) {
        cr.deleteById(id);
        return true;
       }

-   **@RequestBody:**  It is used to  **bind**  HTTP request with an object in a method parameter. 
- 
-   **@ResponseBody:**  It binds the method return value to the response body. It tells the Spring Boot Framework to serialize a return an object into JSON and XML format.
- 
-   **@PathVariable:**  It is used to extract the values from the URI. It is most suitable for the RESTful web service, where the URL contains a path variable. We can define multiple @PathVariable in a method.
- 
-   **@RequestParam:**  It is used to extract the query parameters form the URL. It is also known as a  **query parameter**. It is most suitable for web applications. It can specify default values if the query parameter is not present in the URL.
- 
-   **@RequestHeader:**  It is used to get the details about the HTTP request headers. We use this annotation as a  **method parameter**. 
- 
-   **@RestController:**  It can be considered as a combination of  **@Controller**  and  **@ResponseBody** annotations**.**  
- 
-   **@RequestAttribute:**  It binds a method parameter to request attribute. It provides convenient access to the request attributes from a controller method. With the help of @RequestAttribute annotation, we can access objects that are populated on the server-side.

# Spring Boot Application Properties

Spring Boot Framework comes with a built-in mechanism for application configuration using a file called  **application.properties**. It is located inside the  **src/main/resources**  folder, as shown in the following figure.

![Spring Boot application properties](https://static.javatpoint.com/springboot/images/spring-boot-application-properties1.png)

Spring Boot provides various properties that can be configured in the  **application.properties** file. The properties have default values. We can set a property(s) for the Spring Boot application. Spring Boot also allows us to define our own property if required.

# Spring Boot Starters

**Spring Boot**  provides a number of  **starters**  that allow us to add jars in the classpath. Spring Boot built-in **starters**  make development easier and rapid. **Spring Boot Starters**  are the  **dependency descriptors**.

In the Spring Boot Framework, all the starters follow a similar naming pattern:  **spring-boot-starter-***, where  ***** denotes a particular type of application. For example, if we want to use Spring and JPA for database access, we need to include the  **spring-boot-starter-data-jpa**  dependency in our  **pom.xml**  file of the project.


