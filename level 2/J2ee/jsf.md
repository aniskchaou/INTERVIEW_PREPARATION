## ManagedBean

Managed Bean is a regular Java Bean class registered with JSF. **In other words, Managed Beans is a Java bean managed by JSF framework. Managed bean contains the getter and setter methods, business logic, or even a backing bean (a bean contains all the HTML form value).**

**Managed beans works as Model for UI component**. Managed Bean can be accessed from JSF page
## @ManagedBean Annotation

**@ManagedBean**  marks a bean to be a managed bean with the name specified in name attribute. If the name attribute is not specified, then the managed bean name will default to class name portion of the fully qualified class name. 
Another important attribute is  **eager**. If eager = "true" then managed bean is created before it is requested for the first time otherwise "lazy" initialization is used in which bean will be created only when it is requested.

## Scope Annotations


**@RequestScoped**

Bean lives as long as the HTTP request-response lives.


**@NoneScoped**

Bean lives as long as a single EL evaluation. It gets created upon an EL evaluation and gets destroyed immediately after the EL evaluation.



**@ViewScoped**

Bean lives as long as the user is interacting with the same JSF view in the browser window/tab.

**@SessionScoped**

Bean lives as long as the HTTP session lives.

**@ApplicationScoped**

Bean lives as long as the web application lives.

**@CustomScoped**

Bean lives as long as the bean's entry in the custom Map, which is created for this scope lives.

## Facelets

JSF provides special tags to create common layout for a web application called facelets tags. These tags provide flexibility to manage common parts of multiple pages at one place.


    <html  
       xmlns = "http://www.w3.org/1999/xhtml"  
       xmlns:ui = "http://java.sun.com/jsf/facelets">

Following are important Facelets Tags in JSF 2.0.


## 1) Create User Interface

We will use default page index.xhtml to render input web page. Modify your index.xhtml source code as the given below.

    1.  // index.xhtml
    2.  <?xml  version='1.0'  encoding='UTF-8'  ?>
    3.  <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN""http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
    4.  <html  xmlns="http://www.w3.org/1999/xhtml"
    5.  xmlns:h="http://xmlns.jcp.org/jsf/html">
    6.  <h:head>
    7.  <title>User Form</title>
    8.  </h:head>
    9.  <h:body>
    10.  <h:form>
    11.  <h:outputLabel  for="username">User Name</h:outputLabel>
    12.  <h:inputText  id="username"  value="#{user.name}"  required="true"  requiredMessage="User Name is required"  /><br/>
    13.  <h:commandButton  id="submit-button"  value="Submit"  action="response.xhtml"/>
    14.  </h:form>
    15.  </h:body>
    16.  </html>

After creating response.xhtml page. Now, modify it's source code as the given below.

**// response.xhtml**

    1.  <?xml  version='1.0'  encoding='UTF-8'  ?>
    2.  <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN""http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
    3.  <html  xmlns="http://www.w3.org/1999/xhtml"
    4.  xmlns:h="http://xmlns.jcp.org/jsf/html">
    5.  <h:head>
    6.  <title>Welcome Page</title>
    7.  </h:head>
    8.  <h:body>
    9.  <h2>Hello, <h:outputText  value="#{user.name}"></h:outputText></h2>
    10.  </h:body>
    11.  </html>

## 2) Create a Managed Bean

It is a Java class which contains properties and getter setter methods. JSF uses it as a Model. So, you can use it to write your business logic also.
After creating a Java class put the below code into your User.java file.

**// User.java**

    1.  package managedbean;
    2.  Facelet Title
    3.  import javax.faces.bean.ManagedBean;
    4.  import javax.faces.bean.RequestScoped;
    5.  @ManagedBean
    6.  @RequestScoped
    7.  public  class User {
    8.  String name;
    
    10.  public String getName() {
    11.  return name;
    12.  }
    13.  public  void setName(String name) {
    14.  this.name = name;
    15.  }
    16.  }

## 3) Configure Application

To configure application, project contains a web.xml file which helps to set FacesServlet instances. You can also set your application welcome page and any more.

Below is the code of web.xml code for this application.

**// web.xml**

    1.  <?xml  version="1.0"  encoding="UTF-8"?>
    2.  <web-app  version="3.1"  xmlns="http://xmlns.jcp.org/xml/ns/javaee"
    3.  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee
    4.  http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd">
    5.  <context-param>
    6.  <param-name>javax.faces.PROJECT_STAGE</param-name>
    7.  <param-value>Development</param-value>
    8.  </context-param>
    9.  <servlet>
    10.  <servlet-name>Faces Servlet</servlet-name>
    11.  <servlet-class>javax.faces.webapFacelet Titlep.FacesServlet</servlet-class>
    12.  <load-on-startup>1</load-on-startup>
    13.  </servlet>
    14.  <servlet-mapping>
    15.  <servlet-name>Faces Servlet</servlet-name>
    16.  <url-pattern>/faces/*</url-pattern>
    17.  </servlet-mapping>
    18.  <session-config>
    19.  <session-timeout>
    20.  30
    21.  </session-timeout>
    22.  </session-config>
    23.  <welcome-file-list>
    24.  <welcome-file>faces/index.xhtml</welcome-file>
    25.  </welcome-file-list>
    26.  </web-app>

