# JSP Tutorial



**JSP**  technology is used to create web application just like Servlet technology. It can be thought of as an extension to Servlet because it provides more functionality than servlet such as expression language, JSTL, etc.

A JSP page consists of HTML tags and JSP tags. The JSP pages are easier to maintain than Servlet because we can separate designing and development. It provides some additional features such as Expression Language, Custom Tags, etc.
### The Lifecycle of a JSP Page

The JSP pages follow these phases:

-   Translation of JSP Page
-   Compilation of JSP Page
-   Classloading (the classloader loads class file)
-   Instantiation (Object of the Generated Servlet is created).
-   Initialization ( the container invokes jspInit() method).
-   Request processing ( the container invokes _jspService() method).
-   Destroy ( the container invokes jspDestroy() method).

#### Note: jspInit(), _jspService() and jspDestroy() are the life cycle methods of JSP.

### Creating a simple JSP Page

To create the first JSP page, write some HTML code as given below, and save it by .jsp extension. We have saved this file as index.jsp. Put it in a folder and paste the folder in the web-apps directory in apache tomcat to run the JSP page.

**index.jsp**

Let's see the simple example of JSP where we are using the scriptlet tag to put Java code in the JSP page. We will learn scriptlet tag later.

    1.  < html>
    2.  < body>
    3.  <% out.print(2*5); %>
    4.  < /body>
    5.  < /html>

It will print  **10**  on the browser.

### How to run a simple JSP Page?

Follow the following steps to execute this JSP page:

-   Start the server
-   Put the JSP file in a folder and deploy on the server
-   Visit the browser by the URL http://localhost:portno/contextRoot/jspfile, for example, http://localhost:8888/myapplication/index.jsp

----------

### Do I need to follow the directory structure to run a simple JSP?

No, there is no need of directory structure if you don't have class files or TLD files. For example, put JSP files in a folder directly and deploy that folder. It will be running fine. However, if you are using Bean class, Servlet or TLD file, the directory structure is required.

----------

### The Directory structure of JSP

The directory structure of JSP page is same as Servlet. We contain the JSP page outside the WEB-INF folder or in any directory.

# The JSP API


The JSP API consists of two packages:

1.  javax.servlet.jsp
2.  javax.servlet.jsp.tagext
## The JspPage interface

According to the JSP specification, all the generated servlet classes must implement the JspPage interface. It extends the Servlet interface. It provides two life cycle methods.


### Methods of JspPage interface

1.  **public void jspInit():**  It is invoked only once during the life cycle of the JSP when JSP page is requested firstly. It is used to perform initialization. It is same as the init() method of Servlet interface.
2.  **public void jspDestroy():**  It is invoked only once during the life cycle of the JSP before the JSP page is destroyed. It can be used to perform some clean up operation.

----------

## The HttpJspPage interface

The HttpJspPage interface provides the one life cycle method of JSP. It extends the JspPage interface.

### Method of HttpJspPage interface:

1.  **public void _jspService():**  It is invoked each time when request for the JSP page comes to the container. It is used to process the request. The underscore _ signifies that you cannot override this method.

We will learn all other classes and interfaces later.
# JSP Scriptlet tag (Scripting elements)


In JSP, java code can be written inside the jsp page using the scriptlet tag. Let's see what are the scripting elements first.

## JSP Scripting elements

The scripting elements provides the ability to insert java code inside the jsp. There are three types of scripting elements:

-   scriptlet tag
-   expression tag
-   declaration tag

----------

### JSP scriptlet tag

A scriptlet tag is used to execute java source code in JSP. 

    1.  <% java source code %>

### Example of JSP scriptlet tag

In this example, we are displaying a welcome message.

    1.  < html>
    2.  < body>
    3.  <% out.print("welcome to jsp"); %>
    4.  < /body>
    5.  < /html>

----------

### Example of JSP scriptlet tag that prints the user name



File: index.html

    1.  < html>
    2.  < body>
    3.  < form  action="welcome.jsp">
    4.  < input  type="text"  name="uname">
    5.  < input  type="submit"  value="go"><br/>
    6.  < /form>
    7.  < /body>
    8.  < /html>

File: welcome.jsp

    1.  < html>
    2.  < body>
    3.  <%
    4.  String name=request.getParameter("uname");
    5.  out.print("welcome "+name);
    6.  %>
    7.  < /form>
    8.  < /body>
    9.  < /html>

# JSP expression tag

The code placed within  **JSP expression tag**  is  _written to the output stream of the response_. So you need not write out.print() to write data. It is mainly used to print the values of variable or method.

### Syntax of JSP expression tag

1.  <%= statement %>

### Example of JSP expression tag

In this example of jsp expression tag, we are simply displaying a welcome message.

    1.  < html>
    2.  < body>
    3.  <%= "welcome to jsp" %>
    4.  < /body>
    5.  < /html>

#### Note: Do not end your statement with semicolon in case of expression tag.

### Example of JSP expression tag that prints current time

To display the current time, we have used the getTime() method of Calendar class. The getTime() is an instance method of Calendar class, so we have called it after getting the instance of Calendar class by the getInstance() method.

index.jsp

    1.  < html>
    2.  < body>
    3.  Current Time: <%= java.util.Calendar.getInstance().getTime() %>
    4.  < /body>
    5.  < /html>

### Example of JSP expression tag that prints the user name

In this example, we are printing the username using the expression tag. The index.html file gets the username and sends the request to the welcome.jsp file, which displays the username.

File: index.jsp

    1.  < html>
    2.  < body>
    3.  < form  action="welcome.jsp">
    4.  < input  type="text"  name="uname"><br/>
    5.  < input  type="submit"  value="go">
    6.  < /form>
    7.  < /body>
    8.  < /html>

File: welcome.jsp

    1.  < html>
    2.  < body>
    3.  <%= "Welcome "+request.getParameter("uname") %>
    4.  < /body>
    5.  < /html>

# JSP Declaration Tag



The  **JSP declaration tag**  is used  _to declare fields and methods_.

The code written inside the jsp declaration tag is placed outside the service() method of auto generated servlet.

So it doesn't get memory at each request.

#### Syntax of JSP declaration tag

The syntax of the declaration tag is as follows:

    1.  <%! field or method declaration %>

### Difference between JSP Scriptlet tag and Declaration tag

Jsp Scriptlet Tag

Jsp Declaration Tag

The jsp scriptlet tag can only declare variables not methods.

The jsp declaration tag can declare variables as well as methods.

The declaration of scriptlet tag is placed inside the _jspService() method.

The declaration of jsp declaration tag is placed outside the _jspService() method.

### Example of JSP declaration tag that declares field

In this example of JSP declaration tag, we are declaring the field and printing the value of the declared field using the jsp expression tag.

### index.jsp

    1.  < html>
    2.  < body>
    3.  <%! int data=50; %>
    4.  <%= "Value of the variable is:"+data %>
    5.  < /body>
    6.  < /html>



### Example of JSP declaration tag that declares method

In this example of JSP declaration tag, we are defining the method which returns the cube of given number and calling this method from the jsp expression tag. But we can also use jsp scriptlet tag to call the declared method.

### index.jsp

    1.  < html>
    2.  < body>
    3.  <%!
    4.  int cube(int n){
    5.  return n*n*n*;
    6.  }
    7.  %>
    8.  <%= "Cube of 3 is:"+cube(3) %>
    9.  < /body>
    10.  < /html>

# JSP request implicit object

The  **JSP request**  is an implicit object of type HttpServletRequest i.e. created for each jsp request by the web container. It can be used to get request information such as parameter, header information, remote address, server name, server port, content type, character encoding etc.

It can also be used to set, get and remove attributes from the jsp request scope.

Let's see the simple example of request implicit object where we are printing the name of the user with welcome message.

### Example of JSP request implicit object

### index.html

    1.  < form  action="welcome.jsp">
    2.  < input  type="text"  name="uname">
    3.  < input  type="submit"  value="go"><br/>
    4.  < /form>

### welcome.jsp

    1.  <%
    2.  String name=request.getParameter("uname");
    3.  out.print("welcome "+name);
    4.  %>

# 3) JSP response implicit object

In JSP, response is an implicit object of type HttpServletResponse. The instance of HttpServletResponse is created by the web container for each jsp request.

It can be used to add or manipulate response such as redirect response to another resource, send error etc.

Let's see the example of response implicit object where we are redirecting the response to the Google.

### Example of response implicit object

**index.html**

    1.  < form  action="welcome.jsp">
    2.  < input  type="text"  name="uname">
    3.  < input  type="submit"  value="go"><br/>
    4.  < /form>

**welcome.jsp**

    1.  <%
    2.  response.sendRedirect("http://www.google.com");
    3.  %>

# 4) JSP config implicit object

In JSP, config is an implicit object of type  _ServletConfig_. This object can be used to get initialization parameter for a particular JSP page. The config object is created by the web container for each jsp page.

Generally, it is used to get initialization parameter from the web.xml file.

### Example of config implicit object:

**index.html**

    1.  < form  action="welcome">
    2.  < input  type="text"  name="uname">
    3.  < input  type="submit"  value="go"><br/>
    4.  < /form>

**web.xml file**

    1.  < web-app>
    
    3.  < servlet>
    4.  < servlet-name>sonoojaiswal</servlet-name>
    5.  < jsp-file>/welcome.jsp</jsp-file>
    
    7.  < init-param>
    8.  < param-name>dname< /param-name>
    9.  < param-value>sun.jdbc.odbc.JdbcOdbcDriver< /param-value>
    10.  < /init-param>
    
    12.  < /servlet>
    
    14.  < servlet-mapping>
    15.  < servlet-name>sonoojaiswal< /servlet-name>
    16.  < url-pattern>/welcome< /url-pattern>
    17.  < /servlet-mapping>
    
    19.  < /web-app>

**welcome.jsp**

    1.  <%
    2.  out.print("Welcome "+request.getParameter("uname"));
    
    3.  String driver=config.getInitParameter("dname");
    4.  out.print("driver name is="+driver);
    5.  %>

# 5) JSP application implicit object

In JSP, application is an implicit object of type  _ServletContext_.

The instance of ServletContext is created only once by the web container when application or project is deployed on the server.

This object can be used to get initialization parameter from configuaration file (web.xml). It can also be used to get, set or remove attribute from the application scope.

This initialization parameter can be used by all jsp pages.

### Example of application implicit object:

**index.html**

    1.  < form  action="welcome">
    2.  < input  type="text"  name="uname">
    3.  < input  type="submit"  value="go"><br/>
    4.  < /form>

**web.xml file**

    1.  < web-app>
    
    3.  < servlet>
    4.  < servlet-name>sonoojaiswal< /servlet-name>
    5.  < jsp-file>/welcome.jsp< /jsp-file>
    6.  < /servlet>
    
    8.  < servlet-mapping>
    9.  < servlet-name>sonoojaiswal< /servlet-name>
    10.  < url-pattern>/welcome< /url-pattern>
    11.  < /servlet-mapping>
    
    13.  < context-param>
    14.  < param-name>dname< /param-name>
    15.  < param-value>sun.jdbc.odbc.JdbcOdbcDriver< /param-value>
    16.  < /context-param>
    
    18.  < /web-app>

**welcome.jsp**

    1.  <%
    
    2.  out.print("Welcome "+request.getParameter("uname"));
    
    3.  String driver=application.getInitParameter("dname");
    4.  out.print("driver name is="+driver);
    
    5.  %>

# 6) session implicit object

In JSP, session is an implicit object of type HttpSession.The Java developer can use this object to set,get or remove attribute or to get session information.

### Example of session implicit object

### index.html

    1.  < html>
    2.  < body>
    3.  < form action="welcome.jsp">
    4.  < input type="text" name="uname">
    5.  < input type="submit" value="go"><br/>
    6.  < /form>
    7.  < /body>
    8.  < /html>

### welcome.jsp

    1.  < html>
    2.  < body>
    3.  <%
    
    5.  String name=request.getParameter("uname");
    6.  out.print("Welcome "+name);
    
    8.  session.setAttribute("user",name);
    
    10.  < a href="second.jsp">second jsp page< /a>
    
    12.  %>
    13.  < /body>
    14.  < /html>

### second.jsp

    1.  < html>
    2.  < body>
    3.  <%
    
    4.  String name=(String)session.getAttribute("user");
    5.  out.print("Hello "+name);
    
    6.  %>
    7.  < /body>
    8.  < /html>
    9.  

# 8) page implicit object:

In JSP, page is an implicit object of type Object class.This object is assigned to the reference of auto generated servlet class. It is written as:

Object page=this;

For using this object it must be cast to Servlet type.For example:

    <% (HttpServlet)page.log("message"); %>

Since, it is of type Object it is less used because you can use this object directly in jsp.For example:

    <% this.log("message"); %>

# 9) exception implicit object

In JSP, exception is an implicit object of type java.lang.Throwable class. This object can be used to print the exception. But it can only be used in error pages.It is better to learn it after page directive. Let's see a simple example:

### Example of exception implicit object:

### error.jsp

    1.  <%@ page isErrorPage="true" %>
    2.  < html>
    3.  < body>
    
    4.  Sorry following exception occured:<%= exception %>
    
    5.  < /body>
    6.  < /html>

# JSP directives



The  **jsp directives**  are messages that tells the web container how to translate a JSP page into the corresponding servlet.

There are three types of directives:

-   page directive
-   include directive
-   taglib directive

### Syntax of JSP Directive

    1.  <%@ directive attribute="value" %>

----------

### JSP page directive

The page directive defines attributes that apply to an entire JSP page.

### Syntax of JSP page directive

    1.  <%@ page attribute="value" %>

### Attributes of JSP page directive

-   import
-   contentType
-   extends
-   info
-   buffer
-   language
-   isELIgnored
-   isThreadSafe
-   autoFlush
-   session
-   pageEncoding
-   errorPage
-   isErrorPage
# Jsp Include Directive

The include directive is used to include the contents of any resource it may be jsp file, html file or text file. The include directive includes the original content of the included resource at page translation time (the jsp page is translated only once so it will be better to include static resource).

### Syntax of include directive

    1.  <%@ include file="resourceName" %>

### Example of include directive

In this example, we are including the content of the header.html file. To run this example you must create an header.html file.

    1.  < html>
    2.  < body>
    
    3.  <%@ include file="header.html" %>
    
    4.  Today is: <%= java.util.Calendar.getInstance().getTime() %>
    
    5.  < /body>
    6.  < /html>

# JSP Taglib directive

The JSP taglib directive is used to define a tag library that defines many tags. We use the TLD (Tag Library Descriptor) file to define the tags. In the custom tag section we will use this tag so it will be better to learn it in custom tag.

#### Syntax JSP Taglib directive

    1.  <%@ taglib uri="uriofthetaglibrary" prefix="prefixoftaglibrary" %>

----------

### Example of JSP Taglib directive

In this example, we are using our tag named currentDate. To use this tag we must specify the taglib directive so the container may get information about the tag.

    1.  < html>
    2.  < body>
    
    4.  <%@ taglib uri="http://www.javatpoint.com/tags" prefix="mytag" %>
    
    6.  < mytag:currentDate/>
    
    8.  < /body>
    9.  < /html> 
