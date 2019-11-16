# Hibernate Tutorial

This hibernate tutorial provides in-depth concepts of Hibernate Framework with simplified examples. It was started in 2001 by Gavin King as an alternative to EJB2 style entity bean.

## Hibernate Framework

Hibernate is a Java framework that simplifies the development of Java application to interact with the database. It is an open source, lightweight, ORM (Object Relational Mapping) tool. Hibernate implements the specifications of JPA (Java Persistence API) for data persistence.

## ORM Tool

An ORM tool simplifies the data creation, data manipulation and data access. It is a programming technique that maps the object to the data stored in the database.

The ORM tool internally uses the JDBC API to interact with the database.

## What is JPA?

Java Persistence API (JPA) is a Java specification that provides certain functionality and standard to ORM tools. The  **javax.persistence**  package contains the JPA classes and interfaces.
# Hibernate Architecture

The Hibernate architecture includes many objects such as persistent object, session factory, transaction factory, connection factory, session, transaction etc.
Hibernate framework uses many objects such as session factory, session, transaction etc. alongwith existing Java API such as JDBC (Java Database Connectivity), JTA (Java Transaction API) and JNDI (Java Naming Directory Interface).
# First Hibernate Example without IDE


Here, we are going to create the first hibernate application without IDE. For creating the first hibernate application, we need to follow the following steps:

1.  Create the Persistent class
2.  Create the mapping file for Persistent class
3.  Create the Configuration file
4.  Create the class that retrieves or stores the persistent object
5.  Load the jar file
6.  Run the first hibernate application by using command prompt

### 1) Create the Persistent class

A simple Persistent class should follow some rules:

-   **A no-arg constructor:**  It is recommended that you have a default constructor at least package visibility so that hibernate can create the instance of the Persistent class by newInstance() method.
-   **Provide an identifier property:**  It is better to assign an attribute as id. This attribute behaves as a primary key in database.
-   **Declare getter and setter methods:**  The Hibernate recognizes the method by getter and setter method names by default.
-   **Prefer non-final class:**  Hibernate uses the concept of proxies, that depends on the persistent class. The application programmer will not be able to use proxies for lazy association fetching.

Let's create the simple Persistent class:

#### Employee.java

    1.  package com.javatpoint.mypackage;
    
    3.  public  class Employee {
    4.  private  int id;
    5.  private String firstName,lastName;
    
    7.  public  int getId() {
    8.  return id;
    9.  }
    10.  public  void setId(int id) {
    11.  this.id = id;
    12.  }
    13.  public String getFirstName() {
    14.  return firstName;
    15.  }
    16.  public  void setFirstName(String firstName) {
    17.  this.firstName = firstName;
    18.  }
    19.  public String getLastName() {
    20.  return lastName;
    21.  }
    22.  public  void setLastName(String lastName) {
    23.  this.lastName = lastName;
    24.  }
    
    27.  }

----------

### 2) Create the mapping file for Persistent class

The mapping file name conventionally, should be class_name.hbm.xml. There are many elements of the mapping file.

-   **hibernate-mapping :**  It is the root element in the mapping file that contains all the mapping elements.
-   **class :**  It is the sub-element of the hibernate-mapping element. It specifies the Persistent class.
-   **id :**  It is the subelement of class. It specifies the primary key attribute in the class.
-   **generator :**  It is the sub-element of id. It is used to generate the primary key. There are many generator classes such as assigned, increment, hilo, sequence, native etc. We will learn all the generator classes later.
-   **property :**  It is the sub-element of class that specifies the property name of the Persistent class.

Let's see the mapping file for the Employee class:

#### employee.hbm.xml

    1.  <?xml version='1.0' encoding='UTF-8'?>
    2.  <!DOCTYPE hibernate-mapping PUBLIC
    3.  "-//Hibernate/Hibernate Mapping DTD 5.3//EN"
    4.  "http://hibernate.sourceforge.net/hibernate-mapping-5.3.dtd">
    
    6.  <hibernate-mapping>
    7.  <class name="com.javatpoint.mypackage.Employee" table="emp1000">
    8.  <id name="id">
    9.  <generator class="assigned"></generator>
    10.  </id>
    
    12.  <property name="firstName"></property>
    13.  <property name="lastName"></property>
    
    15.  </class>
    
    17.  </hibernate-mapping>

----------

### 3) Create the Configuration file

The configuration file contains information about the database and mapping file. Conventionally, its name should be hibernate.cfg.xml .

#### hibernate.cfg.xml

    1.  <?xml version='1.0' encoding='UTF-8'?>
    2.  <!DOCTYPE hibernate-configuration PUBLIC
    3.  "-//Hibernate/Hibernate Configuration DTD 5.3//EN"
    4.  "http://hibernate.sourceforge.net/hibernate-configuration-5.3.dtd">
    
    6.  <hibernate-configuration>
    
    8.  <session-factory>
    9.  <property name="hbm2ddl.auto">update</property>
    10.  <property name="dialect">org.hibernate.dialect.Oracle9Dialect</property>
    11.  <property name="connection.url">jdbc:oracle:thin:@localhost:1521:xe</property>
    12.  <property name="connection.username">system</property>
    13.  <property name="connection.password">jtp</property>
    14.  <property name="connection.driver_class">oracle.jdbc.driver.OracleDriver</property>
    15.  <mapping resource="employee.hbm.xml"/>
    16.  </session-factory>
    
    18.  </hibernate-configuration>

----------

### 4) Create the class that retrieves or stores the object

In this class, we are simply storing the employee object to the database.

    1.  package com.javatpoint.mypackage;
    
    2.  import org.hibernate.Session;
    3.  import org.hibernate.SessionFactory;
    4.  import org.hibernate.Transaction;
    5.  import org.hibernate.boot.Metadata;
    6.  import org.hibernate.boot.MetadataSources;
    7.  import org.hibernate.boot.registry.StandardServiceRegistry;
    8.  import org.hibernate.boot.registry.StandardServiceRegistryBuilder;
    
    9.  public  class StoreData {
    10.  public  static  void main(String[] args) {
    
    11.  //Create typesafe ServiceRegistry object
    12.  StandardServiceRegistry ssr = new StandardServiceRegistryBuilder().configure("hibernate.cfg.xml").build();
    
    13.  Metadata meta = new MetadataSources(ssr).getMetadataBuilder().build();
    
    14.  SessionFactory factory = meta.getSessionFactoryBuilder().build();
    15.  Session session = factory.openSession();
    16.  Transaction t = session.beginTransaction();
    
    17.  Employee e1=new Employee();
    18.  e1.setId(101);
    19.  e1.setFirstName("Gaurav");
    20.  e1.setLastName("Chawla");
    
    21.  session.save(e1);
    22.  t.commit();
    23.  System.out.println("successfully saved");
    24.  factory.close();
    25.  session.close();
    
    26.  }
    27.  }


# Web Application with Hibernate (using XML)


Here, we are going to create a web application with hibernate. For creating the web application, we are using JSP for presentation logic, Bean class for representing data and DAO class for database codes.

As we create the simple application in hibernate, we don't need to perform any extra operations in hibernate for creating web application. In such case, we are getting the value from the user using the JSP file.

----------

### Example to create web application using hibernate

In this example, we are going to insert the record of the user in the database. It is simply a registration form.

----------

#### index.jsp

This page gets input from the user and sends it to the register.jsp file using post method.

    1.  <form action="register.jsp" method="post">
    2.  Name:<input type="text" name="name"/><br><br/>
    3.  Password:<input type="password" name="password"/><br><br/>
    4.  Email ID:<input type="text" name="email"/><br><br/>
    5.  <input type="submit" value="register"/>"
    
    7.  </form>

----------

#### register.jsp

This file gets all request parameters and stores this information into an object of User class. Further, it calls the register method of UserDao class passing the User class object.

    1.  <%@page  import="com.javatpoint.mypack.UserDao"%>
    2.  <jsp:useBean id="obj"  class="com.javatpoint.mypack.User">
    3.  </jsp:useBean>
    4.  <jsp:setProperty property="*" name="obj"/>
    
    6.  <%
    7.  int i=UserDao.register(obj);
    8.  if(i>0)
    9.  out.print("You are successfully registered");
    
    11.  %>

----------

#### User.java

It is the simple bean class representing the Persistent class in hibernate.



     package com.javatpoint.mypack;
    
    3.  public  class User {
    4.  private  int id;
    5.  private String name,password,email;
    
    7.  //getters and setters
    
    9.  }

----------

#### user.hbm.xml

It maps the User class with the table of the database.

    1.  <?xml version='1.0' encoding='UTF-8'?>
    2.  <!DOCTYPE hibernate-mapping PUBLIC
    3.  "-//Hibernate/Hibernate Mapping DTD 5.3//EN"
    4.  "http://hibernate.sourceforge.net/hibernate-mapping-5.3.dtd">
    
    6.  <hibernate-mapping>
    7.  <class name="com.javatpoint.mypack.User" table="u400">
    8.  <id name="id">
    9.  <generator class="increment"></generator>
    10.  </id>
    11.  <property name="name"></property>
    12.  <property name="password"></property>
    13.  <property name="email"></property>
    14.  </class>
    
    16.  </hibernate-mapping>

----------

#### UserDao.java

A Dao class, containing method to store the instance of User class.

    1.  package com.javatpoint.mypack;
    
    3.  import org.hibernate.Session;
    4.  import org.hibernate.SessionFactory;
    5.  import org.hibernate.Transaction;
    6.  import org.hibernate.boot.Metadata;
    7.  import org.hibernate.boot.MetadataSources;
    8.  import org.hibernate.boot.registry.StandardServiceRegistry;
    9.  import org.hibernate.boot.registry.StandardServiceRegistryBuilder;
    
    11.  public  class UserDao {
    
    13.  public  static  int register(User u){
    14.  int i=0;
    
    16.  StandardServiceRegistry ssr = new StandardServiceRegistryBuilder().configure("hibernate.cfg.xml").build();
    17.  Metadata meta = new MetadataSources(ssr).getMetadataBuilder().build();
    
    19.  SessionFactory factory = meta.getSessionFactoryBuilder().build();
    20.  Session session = factory.openSession();
    21.  Transaction t = session.beginTransaction();
    
    23.  i=(Integer)session.save(u);
    
    25.  t.commit();
    26.  session.close();
    
    28.  return i;
    
    30.  }
    31.  }

----------

#### hibernate.cfg.xml

It is a configuration file, containing informations about the database and mapping file.

    1.  <?xml version='1.0' encoding='UTF-8'?>
    2.  <!DOCTYPE hibernate-configuration PUBLIC
    3.  "-//Hibernate/Hibernate Configuration DTD 5.3//EN"
    4.  "http://hibernate.sourceforge.net/hibernate-configuration-5.3.dtd">
    
    5.  <hibernate-configuration>
    
    6.  <session-factory>
    7.  <property name="hbm2ddl.auto">create</property>
    8.  <property name="dialect">org.hibernate.dialect.Oracle9Dialect</property>
    9.  <property name="connection.url">jdbc:oracle:thin:@localhost:1521:xe</property>
    10.  <property name="connection.username">system</property>
    11.  <property name="connection.password">jtp</property>
    12.  <property name="connection.driver_class">oracle.jdbc.driver.OracleDriver</property>
    
    13.  <mapping resource="user.hbm.xml"/>
    14.  </session-factory>
    
    15.  </hibernate-configuration>

16. 
# Generator classes in Hibernate



The <generator> class is a sub-element of id. It is used to generate the unique identifier for the objects of persistent class. There are many generator classes defined in the Hibernate Framework.

  

All the generator classes implements the  **org.hibernate.id.IdentifierGenerator  [interface](https://www.javatpoint.com/interface-in-java)**. The application programmer may create one's own generator classes by implementing the IdentifierGenerator interface. Hibernate framework provides many built-in generator classes:

1.  assigned
2.  increment
3.  sequence
4.  hilo
5.  native
6.  identity
7.  seqhilo
8.  uuid
9.  guid
10.  select
11.  foreign
12.  sequence-identity
# SQL Dialects in Hibernate

The dialect specifies the type of database used in hibernate so that hibernate generate appropriate type of SQL statements. For connecting any hibernate application with the database, it is required to provide the configuration of SQL dialect.

### Syntax of SQL Dialect

    1.  <property name="dialect">org.hibernate.dialect.Oracle9Dialect</property>

# Hibernate Query Language (HQL)



Hibernate Query Language (HQL) is same as SQL (Structured Query Language) but it doesn't depends on the table of the database. Instead of table name, we use class name in HQL. So it is database independent query language.

### Advantage of HQL

There are many advantages of HQL. They are as follows:

-   database independent
-   supports polymorphic queries
-   easy to learn for Java Programmer

----------

### Query Interface

It is an object oriented representation of Hibernate Query. The object of Query can be obtained by calling the createQuery() method Session interface.

The query interface provides many methods. There is given commonly used methods:

1.  **public int executeUpdate()**  is used to execute the update or delete query.
2.  **public List list()**  returns the result of the ralation as a list.
3.  **public Query setFirstResult(int rowno)**  specifies the row number from where record will be retrieved.
4.  **public Query setMaxResult(int rowno)**  specifies the no. of records to be retrieved from the relation (table).
5.  **public Query setParameter(int position, Object value)**  it sets the value to the JDBC style query parameter.
6.  **public Query setParameter(String name, Object value)**  it sets the value to a named query parameter.

----------

### Example of HQL to get all the records

    1.  Query query=session.createQuery("from Emp");//here persistent class name is Emp
    2.  List list=query.list();

----------

### Example of HQL to get records with pagination

    1.  Query query=session.createQuery("from Emp");
    2.  query.setFirstResult(5);
    3.  query.setMaxResult(10);
    4.  List list=query.list();//will return the records from 5 to 10th number

----------

### Example of HQL update query

    1.  Transaction tx=session.beginTransaction();
    2.  Query q=session.createQuery("update User set name=:n where id=:i");
    3.  q.setParameter("n","Udit Kumar");
    4.  q.setParameter("i",111);
    
    6.  int status=q.executeUpdate();
    7.  System.out.println(status);
    8.  tx.commit();

----------

### Example of HQL delete query

    1.  Query query=session.createQuery("delete from Emp where id=100");
    2.  //specifying class name (Emp) not tablename
    3.  query.executeUpdate();

### HQL with Aggregate functions

You may call avg(), min(), max() etc. aggregate functions by HQL. Let's see some common examples:

### Example to get total salary of all the employees

    1.  Query q=session.createQuery("select sum(salary) from Emp");
    2.  List<Integer> list=q.list();
    3.  System.out.println(list.get(0));

----------

### Example to get maximum salary of employee

    1.  Query q=session.createQuery("select max(salary) from Emp");

----------

### Example to get minimum salary of employee

    1.  Query q=session.createQuery("select min(salary) from Emp");

----------

### Example to count total number of employee ID

    1.  Query q=session.createQuery("select count(id) from Emp");

----------

### Example to get average salary of each employees

    1.  Query q=session.createQuery("select avg(salary) from Emp");
