J2EE Interview Questions
A list of top frequently asked J2EE Interview Questions and answers are given below.

1) What do you understand by J2EE?
J2EE stands for Java 2 Enterprise Edition. The functionality of J2EE is developing and deploying multi-tier web-based enterprise applications. The J2EE platform is the combination of a set of services, application programming interfaces (APIs), and protocols. The J2EE platform adds the capabilities required to provide a complete, stable, secure, and fast Java platform at the enterprise level.

2) What do you mean by J2EE Module?
A J2EE module is a software unit that consists of one or more J2EE components for the same container type with one deployment descriptor of that type. Modules can be easily deployed or assembled into J2EE applications.


3) What are the four types of J2EE modules?
J2EE defines four types of modules:

Application Client Module
WEB Module
Enterprise JavaBeans Module
Resource Adapter Module
4) What does the application client module contain?
Application client module contains the following:

Class files
Client deployment descriptor
It is packaged as JAR files with a .jar extension.

5) What does the web module contain?
The web module contains the following:

JSP (Java Server Pages) files
Class files for servlets
Web deployment descriptor
GIF (Graphics Interchange Format) and HTML (Hypertext Markup Language) files
These modules are packaged as JAR files with a .war (Web Archive) extension.

6) What does Enterprise JavaBeans module contain?
The Enterprise JavaBeans (EJB) module contains the following:

Class files for enterprise beans
An EJB deployment descriptor
These modules are packaged as JAR files with a .jar extension.

7) What does resource adapt module contain?
The resource adapter module contains the following:

Java interfaces
Classes
Native libraries
Other documentation
Resource Adapter deployment descriptor
These modules are packaged as JAR files with a .rar (Resource Adapter Archive) extension.

8) What are the main components of the J2EE application?
A J2EE component is assembled into a J2EE application with its related classes and files. It can also communicate with other components. The J2EE defines the following main components:

Application clients components.
Java Servlet and JavaServer Pages technology components.
Business Components (Enterprise JavaBeans).
Resource adaptor components.
9) What is considered as a web component?
Java Servlet and Java Server Pages technology components are considered as web components. Servlets are based on Java programming language which dynamically receives requests and generates responses. Java Server pages execute as servlets and allow a more natural approach to creating static content.

10) What are the types of J2EE clients?
Applets
Application clients
Java Web Start-enabled clients
Wireless clients
11) What do you understand by a word applet?
An applet is a J2EE component that typically executes in a web browser. It can also be executed in a variety of other applications or devices that support the applet programming model.

12) What is the container?
A container is the runtime support of a system level entity. Containers provide components with features such as lifecycle management, security, deployment, and threading.

13) What is an "applet container"?
A container that provides support for the applet programming model is known as "applet container."

14) What do you understand by a thin client?
A thin client is a light-weight interface to the application that does not support operations like query database, execute complex business rules, or connect to legacy applications.

15) What is JavaServer Faces (JSF)?
JavaServer Faces is a user interface (UI) designing framework which is used for Java-based web applications. JavaServer Faces provides a set of reusable UI components- a standard for web applications. JSF is based on the MVC design pattern. It automatically saves the form data to the server and populates the form dates when display on the client side.

16) What is an EJB platform?
EJB stands for The Enterprise JavaBeans. EJB platform manages functions such as transaction and state management, resource pooling, multithreading, and simple searches while you concentrate on writing business logic.

17) What do you mean by the deployment descriptor?
A deployment descriptor is based on XML (Extensible Markup Language) that supports .xml extension. It is used to describe a component's deployment settings. A J2EE application and its module, both have its deployment descriptor.

18) Define the Struts in the J2EE framework?
Struts is an application development framework based on MVC (Model-View-Controller) architecture. It is a combination of Java Servlets, JSP, Custom tags, and messages. It is used to design applications for large enterprises. It can be described as:

Model
The model defines the internal state of a system. It can be either single or a cluster of Java Beans based on app architecture.

View
JSP technology is used to design a view of any enterprise application.

Controller
A controller is used to manage the actions of users. It processes the client request and responds based on the request. The main component in the framework is a servlet of class ActionServlet. This servlet is configured by defining a set of ActionMappings.

19) Define Hashtable in J2EE?
Hashtable is similar to HashMap except that Hashtable is synchronized. Hashtable is a cluster of synchronized objects where null values and duplicate values are not allowed.

20) Define Hibernate and HQL?
Hibernate is an object-relational mapping and query service. In hibernate, we can write HQL (Hibernate Query Language) scripts instead of SQL, which saves lots of time and effort. Hibernate provides a more powerful association, inheritance, polymorphism, composition, and collections. We can process queries easily into the database using the Java objects. Hibernate also allows us to express queries using Java-based criteria.

21) What are the limitations of Hibernate?
Following are some limitations of hibernate:

Slower execution of queries.
Only HQL support is available for composite keys.
No shared references are available to the value type.
22) What are the major benefits of hibernate?
Following are some major benefits of hibernate:

Hibernate is independent of database and vendor so it is the portable framework.
Domain objects can be mapped to the relational database.
JPA support for standard ORM.
Better database connectivity in Hibernate when compared to JDBC.
23) Define ORM and its working in J2EE?
ORM refers to Object-Relational mapping. It is the object in a Java class which is mapped into the tables of a relational database using the metadata that describes the mapping between the objects and database. It transforms the data from one representation to another.

24) What is authorization?
An authorization is a process by which access to a method or resource is determined. It relies on the determination of whether the principal associated with a request through authentication is in a given security role. A security role can be explained as a logical grouping of users defined by the person who assembles the application. A deployer maps the security roles to security identities. Security identities may be principles or groups in the operational environment.

25) Define authorization constraint?
An authorization rule which determines who is permitted to access Web resource collection is known as authorization constraint.

26) How will you explain save() and saveorupdate() methods in hibernate?
The Save() method in hibernate is used to store an object in the database. It creates a new entry if the record doesn't exist.

The Saveorupdate() method in hibernate is used for updating the object using the identifier. If the identifier is unavailable, this method calls save(). If the identifier is available, it will call the update method.

27) How will you explain load() and get() methods?
Load(): If an object is missing in the Cache or database, Load() method will throw an exception. Load() method never returns null.

Get(): If an object is missing in the Cache or database, Get() method returns a null value, not the exception.

28) What is a web container in J2EE?
An interface between a component and the low-level platform with defined functionality that is designed to support the component is defined as the web container in J2EE.

29) What is the concept of connection pooling?
Connection pooling is a simple concept which is popular to reuse existing connections. It means that if object connections are already well-defined and connected, then they can be reused whenever there is a requirement instead of generating a new one.

30) What do you understand by the servlet?
Servlet is a server-side component which provides full functionalities to create a server-side program. There are different servlets available with a specific design for a variety of protocols. The most popular type of protocol for the servlet is HTTP.Servlets, which use the classes in the java packages javax.servlet, javax.servlet.http.HttpServletRequest, javax.servlet.http.HttpServletResponse, javax.servlet.http.HttpSession;. All servlets must include the Servlet interface, which defines life-cycle methods.

31) Give some advantages of ORM (object-relational mapping)?
Productivity
The automatic code is generated to reduce the overall data access time based on the data model defined.

Performance
The complete requirements of an application are managed by the automated code generated by the ORM, which means that there is no need for any extra code, and the overall data access process is made faster and optimized.

Vendor Independent
The generated code is independent of the vendor, which increases the overall portability of an application.
Maintainability
The code is well tested and generated by the ORM, and only a developer can understand the code perfectly.

32) Tell about the core interfaces of the hibernate framework?
Session Interface
SessionFactory Interface
Configuration Interface
Transaction Interface
Query and Criteria Interface
33) What is B2b?
B2b indicates to business-to-business.

34) What is the file extension used for hibernate mapping file and hibernate configuration file?
For hibernate mapping, the file name should be like filename.hbm.xml.

For hibernate configuration, the file name should be like hibernate.cfg.xml.

35) Define a way to add Hibernate mapping file in hibernate configuration file?
It can be easily performed by:

<mapping resource="filename.hbm.xml"/>  
36) What are the main components of multi-tier architecture?
The main components of multi-tier architecture are:

Presentation Tier
The front-end component existing in this tier is used to display the presentation.

Resource Tier
The back-end component existing in this tier is used to communicate with the database.

Business Tier
The component existing in this tier is used to provide business logic for the system.

37) Explain JTA, JNDI, and JMS.
JTA represents JAVA Transaction API, which is used for coordinating and managing transactions across the enterprise information system.

JNDI represents Java Naming Directory Interface, which is used for accessing data from directory services.

JMS represents the Java Messaging Service, which is used for receiving and sending messages through messaging systems.

38) Explain the J2EE tiers.
J2EE has the following tiers:

Client Tier
It indicates to the browser from which request is processed to the server. The interfaces that are available in this tier are HTML browser, Java application, an applet, or a non-java application.

Middle Tier
It comprises of a presentation tier and integration tier. The UI (User Interface) is created in the presentation tier using JavaServer Pages. The business logic is written inside the business tier with the help of Enterprise Java Bean. The objects of the database are created in the integration tier.

Backend
It constitutes the Enterprise Information System (EIS) which is used to store the data.

39) Describe the EAR, WAR, and JAR.
EAR stands for Enterprise Archive file. It consists of the components of the web, EJB, and client. All the components of the EAR are packed in a compressed file with the extension .ear.

WAR stands for a Web Archive file. It consists of all the components related to the web application. All the components are packed in a compressed file with the extension .war.

JAR stands for Java Archive file. It consists of all the class files and library files, which constitute an API (Application Programming Interface). All the components are packed in a compressed file with the extension .jar.

Each type of file (.ear, .war, and .jar) is processed uniquely by application servers, servlet containers, EJB containers, etc.

40) What do you understand by Spring?
Spring is a light-weight open source framework for developing enterprise applications. It resolves the complexity of enterprise application development and provides easy development for the J2EE. It was initially written by Rod Johnson. It was released under the Apache 2.0 license in June 2003.

41) What are the different modules used in Spring?
There are mainly seven core modules in spring:

The Core container module
Object/Relational mapping module
DAO module
Application context module
Aspect Oriented Programming
Web module
MVC module
42) What is action mapping?
In action mapping, a user specifies action class for a particular URL, i.e., path and different target view, which means, forwards on to which request-response is forwarded. The ActionMapping defines the information that the ActionServlet knows about the mapping of a particular request to an instance of a specific Action class. The mapping is transferred to the execute() method of the Action class, enabling access to this information directly.

43) What do you understand by ActionForm?
ActionForm is a Java bean which may associate one or more ActionMappings. A java bean changes to FormBean when a user extends a class org.apache.struts.action.ActionForm. ActionForm object is generally populated on the server side automatically, and the client enters data from UI. ActionForm manages the session state for a web application.

44) What is backing bean?
A backing bean is a JavaBeans component which corresponds to JavaServer Pages that includes JavaServer Faces components. The backing bean describes the properties for the components on the page and methods which perform processing for the component.

This processing may include event handling, validation, and processing associated with navigation.

45) What is the build file?
A build file is an XML file that consists of one or more asant targets. A target is a set of tasks that a user wants to get executed. When starting asant, a user can select which target is to be executed. If there is no target, then the default target of the project is executed.

46) What do you understand by business logic?
Business logic is the code that includes the functionality of an application. In the EJB (Enterprise JavaBeans) architecture, this logic is implemented by the methods of an enterprise bean.

47) How will you explain CDATA?
A CDATA is a predefined XML tag for the character data, which means "don't interpret these characters," it is similar to parsed character data (PCDATA), in which the standard rules of XML syntax apply. CDATA sections are used to show examples of XML syntax.

48) What do you mean by the Component Contract?
The contract between the J2EE component and its container is known as the component contract. This type of contract includes:

Life-cycle management of the component
An interface which is used by instance to obtain various information and services from its container
List of services that every container must provide for its components.
49) What do you understand by Connector? Explain Connector Architecture.
A connector is a standard extension mechanism for containers, which provides connectivity to enterprise information systems. It is specific to an enterprise information system and contains a resource adapter and application development tools for enterprise information system connectivity. The resource adapter is plugged into a container through its support for system-level contracts, defined in the Connector architecture.

An architecture for the integration of J2EE products with enterprise information systems is known as the connector architecture. A connector architecture consists of:

A resource adapter which is given by an enterprise information system vendor
A J2EE product that allows this resource adapter to plug in.
Connector architecture also defines a set of contracts which a resource adapter must support to plug into a J2EE product (e.g., transactions, security, and resource management).