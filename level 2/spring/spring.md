
## **What Is Spring?**
It is a lightweight, loosely coupled and integrated framework for developing enterprise applications in java.

## Modules

![enter image description here](https://static.javatpoint.com/images/sp/spmodules.jpg)
-   **Spring Security**
-   **Spring AOP**
-   **Spring Data** : ORM, JDBC, OXM, JMS
-   **Spring Test :** JUnit and TestNG
- **Spring Web (MVC)** : Web-Servlet, Web-Struts and Web-Portlet
- **Spring Core** : Beans, Context, Expression Language


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



# Spring Boot Application Properties

Spring Boot Framework comes with a built-in mechanism for application configuration using a file called  **application.properties**. It is located inside the  **src/main/resources**  folder, as shown in the following figure.

![Spring Boot application properties](https://static.javatpoint.com/springboot/images/spring-boot-application-properties1.png)

Spring Boot provides various properties that can be configured in the  **application.properties** file. The properties have default values. We can set a property(s) for the Spring Boot application. Spring Boot also allows us to define our own property if required.





