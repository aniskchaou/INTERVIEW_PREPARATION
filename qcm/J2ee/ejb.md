### 1) What is EJB?

EJB stands for Enterprise Java Bean. It is a server-side component to develop scalable, robust and secured enterprise applications in java. 

----------

### 2) What are the types of Enterprise Bean?

There are three types of enterprise bean in java.

1.  Session Bean
2.  Message Driven Bean
3.  Entity Bean



----------

### 3) What is session bean?

Session Bean encapsulates business logic. It can be invoked by local, remote or web service client.

There are 3 types of session bean.

1.  Stateless Session Bean
2.  Stateful Session Bean
3.  Singleton Session Bean



----------

### 4) What is stateless session bean?

A Stateless session bean is a business object that doesn't maintain the conversational state with the client.

### 5) Write down the steps for the creation of stateless EJB.

-   Create a local interface.
-   The interface is to be used by the client application.
-   In case the EJB client environment is the same, use @Local annotation.
-   In case the EJB client environment is different, use @Remote annotation.
-   Create a stateful session bean.
-   To signify a stateful bean, use @Stateful annotation.

----------

### 6) What is stateful session bean?

A Stateful session bean is a business object that maintains the conversational state with the client. 

### 7) What is singleton session bean?

Singleton session bean is instantiated only once for the application. It exists for the life cycle of the application.

----------

### 8) What is JMS?

Java Message Service is a messaging service to create, send and receive messages asynchronously. 

----------


### 13) What is Entity Bean?

Entity Bean is a server-side component that represents the persistent data. Since EJB 3.x, it is replaced by JPA. 


### 17) Name the attributes of javax.ejb.Stateful.

-   Name
-   mappedName
-   Description