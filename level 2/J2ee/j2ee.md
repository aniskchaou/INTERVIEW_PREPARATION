**Q #1) What are the components of J2EE applications?**

-   Client-tier components. Run on the client machine.
-   Web tier components. Run on the J2EE server.
-   Business tier components. Run on the J2EE server.
-   Enterprise information system software (EIS software).Runs on the  **EIS**  server.

**Q #5) Describe the MVC on struts?**

**Ans)**  **MVC**  stands for Model View Controller. Each section in Model View Controller can describe as follows.

-   **Model –**Model represents the internal state of the system as a set of single or many **Java Beans**.
-   **View –** Most often view is a constructed using  **Java Server Pages (JSP)**  technology.
-   **Controller – The primary component of the controller in the framework is  **“ActionServlet”**  servlet class.

**Q #6) Define JSF?**

**Ans)**  **JSF**  stands for Java Server Faces. It is the user interface (UI) designing framework for Java Web Applications developments. There are set of reusable UI components associated with JSF. Also, JSF based on Model-View-Controller (MVC) design concepts and patterns. 

**Q #7) What is Hashtable?**

**Ans)**  Hash table is a Collection Synchronized objects. It allows Null values but not duplicate values. Hash table is like a HashMap.

**Q #8) Define Hibernate?**

**Ans)**  Hibernate is an open source object-relational mapping and query service which facilitate to write  **Hibernate Query Language (HQL)**  scripts instead of  **Structured Query Language (SQL)**  scripts. It is faster and easy than writing native  **SQL**. 

**Q #9) What are the identified limitation of hibernate?**

**Ans)**

-   **Slower in action –**  In execution of HQL queries take more time than it executes directly.


**Q #10) What the identified advantages are of hibernate?**

**Ans)**

-   Standard Object-relational mapping support..
-   Better performance than Java Database Connectivity.
-   Java Persistence  **API** based applications.

**Q #11) Describe ORM?.**

**Ans) Object-Relational mapping (ORM)**  can describe as follows.

The mapped objects in a Java class to the tables of the relational database using metadata which describes the database and object mapping. The working method is to transform data from one representation to another.

**Q #13) What is the use of method save()?**

**Ans)**  In hibernate this method is used to stores an object into the database. There is a check for duplicate records before inserting it.

**Q #14) What is the use of method saveorupdate()?**

**Ans)**  In hibernate this method is used to update an object using identifier. When the value for the identifier is NULL then the method direct to call save().

**Q #15) What is the difference between load() and get()?**

**Ans)**  When the object not available in either cache or database, load() thrown an exception. No null return from load().

When the object not available in either cache or database, get() returns null.

**Q #16) What is mean by connection pooling?**

**Ans)**  Simply connection pooling is a mechanism to re-use the existing connections. 


**Q #18) Define thin client?**

**Ans)**  A program interface that does not have any operations like database queries, complex business rules or any connection to the third-party application is called a thin client.

**Q #19) Describe the file types *.ear, * .jar and *.war?**

**Ans)**

-   ***.jar files –**  Property file contains libraries, resources and accessories are included with the *.jar file extension.
-   ***.war files –**  The files that need to development of web application (HTML, java scripts, JSP) included with a *.war file extension.
-   ***.ear files –**  The files for Enterprise Java Beans modules for the application is save as *.ear files.

**Q #20) What spring is in related to J2EE?**

**Ans)**  **Spring**  is an open source application that reduces the complexity of enterprise application development. Spring is based on an inversion of control or dependency injection design patterns.


**Q #25) What are the difference types of JSP tags?**

**Ans)**  _**There are 4 different types of tags associated with JSP.They are mentioned below**_

-   Directives
-   Declarations
-   Scriplets
-   Expressions

### Q #26) Describe action form?

**Ans)**  A java bean that is associated with single or multiple action mapping is called action form. Action form objects are automatically populated at server end when data has been enter from the client from a **user interface (UI)**.

Session states of a web application are maintained by action forms.



**Q #31) Is that Servlet is pure java object or not?**

**Ans)**  Yes, Servlet is pure java object.

**Q #32) What is EJB?**

**Ans)**  **EJB**  stands for Enterprise Java Beans. It is the server side components that executes in EJB container and encapsulates the business logic for the enterprise application.

**Q #33) What are the system services of EJB container?**

**Ans)**  _**EJB Container provides following system services.**_

-   Persistence
-   Security
-   Transaction
-   Connection pooling
-   Component lifecycle management
-   Threading


**Q #36) What are the Basic and subtypes of Enterprise Java Beans (EJB)?**

**Ans)**  _**Two main types and subtypes of EJB are as follows.**_

-   **Session Beans**
    -   Stateful session beans
    -   Stateless session beans
-   **Entity Beans**
    -   Bean Managed Persistence (BMP)
    -   Container Managed Persistence (CMP)
    -   Message Driven Beans


**Q #38) What are the two types of comments supported by JSP?**

**Ans)**  _**There are two types of comments are supported by JSP.**_

-   HTML comment.

[![HTML comment](https://cdn.softwaretestinghelp.com/wp-content/qa/uploads/2017/03/HTML-comment.jpg)](https://cdn.softwaretestinghelp.com/wp-content/qa/uploads/2017/03/HTML-comment.jpg)

-   JSP comment.

[![JSP comment](https://cdn.softwaretestinghelp.com/wp-content/qa/uploads/2017/03/JSP-comment.jpg)](https://cdn.softwaretestinghelp.com/wp-content/qa/uploads/2017/03/JSP-comment.jpg)

**Q #39) What is called JSP directive?**

**Ans)**  **JSP**  directive is the mechanism to provide Metadata information to web container about JSP file. In the translation and compilation phases of the  **JSP**  life cycle, these Metadata use by the web container.

**Q #40) What are the different types of JSP directive?**

**Ans)**  _**There are 3 different types of JSP directives available.**_

-   Page directive
-   Include directive
-   Taglib directive

### 34) What is the file extension used for hibernate mapping file and hibernate configuration file?

For hibernate mapping, the file name should be like  **filename.hbm.xml**.

For hibernate configuration, the file name should be like  **hibernate.cfg.xml**.

----------

### 35) Define a way to add Hibernate mapping file in hibernate configuration file?

It can be easily performed by:

1.  `<mapping resource="filename.hbm.xml"/>`

**22) What do you create a SessionFactory?**

Configuration cfg  =  new  Configuration();  cfg.addResource("dir/hibernate.hbm.xml");  cfg.setProperties(  System.getProperties()  );  SessionFactory sessions  =  cfg.buildSessionFactory();

**23) What is HQL?**

HQL stands for Hibernate Query Language. **Hibernate allows to the user to express queries in its portable SQL extension, and this is called as HQL.** It also allows the user to express in native SQL.