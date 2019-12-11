# Servlets 

**Servlet**  technology is used to create a web application (resides at server side and generates a dynamic web page).

There are many interfaces and classes in the Servlet API such as 

 - Servlet
 - GenericServlet
 - HttpServlet
 - ServletRequest
 - ServletResponse

### What is a web application?

 A web application is composed of web components like Servlet, JSP, Filter, etc. and other elements such as HTML, CSS, and JavaScript. The web components typically execute in Web Server and respond to the HTTP request.

## Servlet Api

The  **javax.servlet**  package contains many interfaces and classes that are used by the servlet or web container. These are not specific to any protocol.

The  **javax.servlet.http**  package contains interfaces and classes that are responsible for http requests only.

# Servlet Interface


**Servlet interface provides**  common behavior to all the servlets.Servlet interface **defines methods that all servlets must implement.**

 - **public void init(ServletConfig config)**

initializes the servlet. It is the life cycle method of servlet and **invoked by the web container only once.**

 - **public void service(ServletRequest request,ServletResponse response)**

provides response for the incoming request. It is invoked at each request by the web container.

 - **public void destroy()**

is invoked only once and indicates that servlet is being destroyed.

 - **public ServletConfig getServletConfig()**

returns the object of ServletConfig.

 - **public String getServletInfo()**

returns information about servlet such as writer, copyright, version etc.

## exemple :

    1.  public  class First implements Servlet{
    2.  ServletConfig config=null;
    
    4.  public  void init(ServletConfig config){
    5.  this.config=config;
    6.  System.out.println("servlet is initialized");
    7.  }
    
    9.  public  void service(ServletRequest req,ServletResponse res)
    10.  throws IOException,ServletException{
    
    12.  res.setContentType("text/html");
    
    14.  PrintWriter out=res.getWriter();
    15.  out.print("<html><body>");
    16.  out.print("<b>hello simple servlet</b>");
    17.  out.print("</body></html>");
    
    19.  }
    20.  public  void destroy(){System.out.println("servlet is destroyed");}
    21.  public ServletConfig getServletConfig(){return config;}
    22.  public String getServletInfo(){return  "copyright 2007-1010";}
    
    24.  }

## GenericServlet class


**GenericServlet**  class implements  **Servlet**,  **ServletConfig**  and  **Serializable**  interfaces. It provides the implementation of all the methods of these interfaces except the service method.

**GenericServlet class can handle any type of request so it is protocol-independent.**

You may create a generic servlet by inheriting the GenericServlet class and providing the implementation of the service method.

    1.  public  class First extends GenericServlet{
    2.  public  void service(ServletRequest req,ServletResponse res)
    3.  throws IOException,ServletException{
    
    4.  res.setContentType("text/html");
    
    5.  PrintWriter out=res.getWriter();
    6.  out.print("<html><body>");
    7.  out.print("<b>hello generic servlet</b>");
    8.  out.print("</body></html>");
    
    9.  }
    10.  }

# HttpServlet class
The HttpServlet class extends the GenericServlet class and implements Serializable interface. It provides http specific methods such as doGet, doPost, doHead, doTrace etc.

 - **public void service(ServletRequest req,ServletResponse res)**  dispatches the request to the protected service method by converting
   the request and response object into http type.
 -  **protected void service(HttpServletRequest req, HttpServletResponse res)**  receives the request from the service method, and dispatches the request to the doXXX() method depending on the incoming http request type.
 -  **protected void doGet(HttpServletRequest req, HttpServletResponse res)**  handles the GET request. It is invoked by the web container.
 -  **protected void doPost(HttpServletRequest req, HttpServletResponse res)**  handles the POST request. It is invoked by the web container.
 -  **protected void doHead(HttpServletRequest req, HttpServletResponse res)**  handles the HEAD request. It is invoked by the web container.
 -  **protected void doOptions(HttpServletRequest req, HttpServletResponse res)**  handles the OPTIONS request. It is invoked by the web container.
 -  **protected void doPut(HttpServletRequest req, HttpServletResponse res)**  handles the PUT request. It is invoked by the web container.
 -  **protected void doTrace(HttpServletRequest req, HttpServletResponse res)**  handles the TRACE request. It is invoked by the web container.
 -  **protected void doDelete(HttpServletRequest req, HttpServletResponse res)**  handles the DELETE request. It is invoked by the web container.
 -  **protected long getLastModified(HttpServletRequest req)**  returns the time when HttpServletRequest was last modified since midnight January 1, 1970 GMT.

## Life Cycle of a Servlet (Servlet Life Cycle)

The web container maintains the life cycle of a servlet instance. Let's see the life cycle of the servlet:

1.  Servlet class is loaded.
2.  Servlet instance is created.
3.  init method is invoked.
4.  service method is invoked.
5.  destroy method is invoked.

# Steps to create a servlet example


The servlet example can be created by three ways:

1.  By implementing Servlet interface,
2.  By inheriting GenericServlet class, (or)
3.  By inheriting HttpServlet class

The mostly used approach is by extending HttpServlet because it provides http request specific method such as doGet(), doPost(), doHead() etc.

## web.xml

Let's see the web.xml file that defines the welcome files.

    1.  < web-app>
    4.  < welcome-file-list >
    5.  < welcome-file>home.html< /welcome-file>
    6.  < welcome-file>default.html< /welcome-file>
    7.  < /welcome-file-list>
    8.  < /web-app>



# load on startup in web.xml

The  **load-on-startup**  element of  **web-app**  loads the servlet at the time of deployment or server start if value is positive. It is also known as  **pre initialization of servlet**.



The  **load-on-startup**  element of  **web-app**  loads the servlet at the time of deployment or server start if value is positive. It is also known as  **pre initialization of servlet**.

You can pass positive and negative value for the servlet.

----------

#### Advantage of load-on-startup element

As you know well, servlet is loaded at first request. That means it consumes more time at first request. If you specify the load-on-startup in web.xml, servlet will be loaded at project deployment time or server start. So, it will take  **less time**  for responding to first request.

----------

#### Passing positive value

If you pass the positive value, the lower integer value servlet will be loaded before the higher integer value servlet. In other words, container loads the servlets in ascending integer value. The 0 value will be loaded first then 1, 2, 3 and so on.

Let's try to understand it by the example given below:

**web.xml**

    1.  < web-app>
    2.  ....
    
    3.  < servlet>
    4.  < servlet-name>servlet1< /servlet-name>
    5.  < servlet-class>com.javatpoint.FirstServlet< /servlet-class>
    6.  < load-on-startup>0< /load-on-startup>
    7.  < /servlet>
    
    8.  < servlet>
    9.  < servlet-name>servlet2< /servlet-name>
    10.  < servlet-class>com.javatpoint.SecondServlet< /servlet-class>
    11.  < load-on-startup>1< /load-on-startup>
    12.  < /servlet>
    
    13.  ...
    14.  < /web-app>

# ServletRequest Interface


An object of ServletRequest is used to provide the client request information to a servlet such as content type, content length, parameter names and values, header informations, attributes etc.

  
  

### Methods of ServletRequest interface

There are many methods defined in the ServletRequest interface. Some of them are as follows:

 - **public String getParameter(String name)**

is used to obtain the value of a parameter by name.

 - **public String[] getParameterValues(String name)**

returns an array of String containing all values of given parameter name. It is mainly used to obtain values of a Multi select list box.

 - **java.util.Enumeration getParameterNames()**

returns an enumeration of all of the request parameter names.

 - **public int getContentLength()**

Returns the size of the request entity data, or -1 if not known.

 - **public String getCharacterEncoding()**

Returns the character set encoding for the input of this request.

 - **public String getContentType()**

Returns the Internet Media Type of the request entity data, or null if not known.

 - **public ServletInputStream getInputStream() throws IOException**

Returns an input stream for reading binary data in the request body.

 - **public abstract String getServerName()**

Returns the host name of the server that received the request.

 - **public int getServerPort()**

Returns the port number on which this request was received.

----------

### Example of ServletRequest to display the name of the user

In this example, we are displaying the name of the user in the servlet. For this purpose, we have used the getParameter method that returns the value for the given request parameter name.

  
**index.html**

    1.  < form action="welcome" method="get">
    2.  Enter your name<input type="text" name="name"><br>
    3.  < input type="submit" value="login">
    4.  < /form>

  
**DemoServ.java**

    1.  import javax.servlet.http.*;
    2.  import javax.servlet.*;
    3.  import java.io.*;
    4.  public  class DemoServ extends HttpServlet{
    5.  public  void doGet(HttpServletRequest req,HttpServletResponse res)
    6.  throws ServletException,IOException
    7.  {
    8.  res.setContentType("text/html");
    9.  PrintWriter pw=res.getWriter();
    
    10.  String name=req.getParameter("name");//will return value
    11.  pw.println("Welcome "+name);
    
    12.  pw.close();
    13.  }}

# RequestDispatcher in Servlet


The RequestDispatcher interface provides the facility of dispatching the request to another resource it may be html, servlet or jsp. This interface can also be used to include the content of another resource also. It is one of the way of servlet collaboration.

There are two methods defined in the RequestDispatcher interface.

 - **public void forward(ServletRequest request,ServletResponse response)throws ServletException,java.io.IOException:** Forwards a
   request from a servlet to another resource (servlet, JSP file, or
   HTML file) on the server.
   
 - **public void include(ServletRequest request,ServletResponse response)throws ServletException,java.io.IOException:** Includes the
   content of a resource (servlet, JSP page, or HTML file) in the
   response.

### How to get the object of RequestDispatcher

The getRequestDispatcher() method of ServletRequest interface returns the object of RequestDispatcher. Syntax:

#### Syntax of getRequestDispatcher method

    1.  public RequestDispatcher getRequestDispatcher(String resource);

#### Example of using getRequestDispatcher method

    1.  RequestDispatcher rd=request.getRequestDispatcher("servlet2");
    2.  //servlet2 is the url-pattern of the second servlet
    
    3.  rd.forward(request, response);//method may be include or forward

# SendRedirect in servlet


The  **sendRedirect()**  method of  **HttpServletResponse**  interface can be used to redirect response to another resource, it may be servlet, jsp or html file.

It accepts relative as well as absolute URL.

It works at client side because it uses the url bar of the browser to make another request. So, it can work inside and outside the server.
## Difference between forward() and sendRedirect() method

There are many differences between the forward() method of RequestDispatcher and sendRedirect() method of HttpServletResponse interface. They are given below:

forward() method

sendRedirect() method

The forward() method works at server side.

The sendRedirect() method works at client side.

It sends the same request and response objects to another servlet.

It always sends a new request.

It can work within the server only.

It can be used within and outside the server.

Example: request.getRequestDispacher("servlet2").forward(request,response);

Example: response.sendRedirect("servlet2");

----------

### Syntax of sendRedirect() method

1.  public  void sendRedirect(String URL)throws IOException;

### Example of sendRedirect() method

1.  response.sendRedirect("http://www.javatpoint.com");

# ServletConfig Interface

**An object of ServletConfig is created by the web container for each servlet. This object can be used to get configuration information from web.xml file.**

If the configuration information is modified from the web.xml file, we don't need to change the servlet. So it is easier to manage the web application if any specific content is modified from time to time.

### Methods of ServletConfig interface

 - **public String getInitParameter(String name):** Returns the parameter value for the specified parameter name.
 - **public Enumeration getInitParameterNames():** Returns an enumeration of all the initialization parameter names.
 - **public String getServletName():** Returns the name of the servlet.
 - **public ServletContext getServletContext():** Returns an object of ServletContext.

### Example of ServletConfig to get initialization parameter

In this example, we are getting the one initialization parameter from the web.xml file and printing this information in the servlet.

  
**DemoServlet.java**


    5.  public  class DemoServlet extends HttpServlet {
    6.  public  void doGet(HttpServletRequest request, HttpServletResponse response)
    7.  throws ServletException, IOException {
    
    9.  response.setContentType("text/html");
    10.  PrintWriter out = response.getWriter();
    
    12.  ServletConfig config=getServletConfig();
    13.  String driver=config.getInitParameter("driver");
    14.  out.print("Driver is: "+driver);
    
    16.  out.close();
    17.  }
    
    19.  }

  
**web.xml**

    1.  < web-app>
    
    2.  < servlet>
    3.  < servlet-name>DemoServlet< /servlet-name>
    4.  < servlet-class>DemoServlet< /servlet-class>
    
    5.  < init-param>
    6.  < param-name>driver< /param-name>
    7.  < param-value>sun.jdbc.odbc.JdbcOdbcDriver< /param-value>
    8.  < /init-param>
    
    9.  < /servlet>
    
    10.  < servlet-mapping>
    11.  < servlet-name>DemoServlet< /servlet-name>
    12.  < url-pattern>/servlet1< /url-pattern>
    13.  < /servlet-mapping>
    
    14.  < /web-app>


# ServletContext Interface



An object of ServletContext is created by the web container at time of deploying the project. This object can be used to get configuration information from web.xml file. There is only one ServletContext object per web application.

    If any information is shared to many servlet, it is better to provide it from the web.xml file using the  **< context-param>**  element.

### Commonly used methods of ServletContext interface

There is given some commonly used methods of ServletContext interface.

  **public String getInitParameter(String name):** Returns the parameter value for the specified parameter name.
 **public Enumeration getInitParameterNames():** Returns the names of the context's initialization parameters.
  **public void setAttribute(String name,Object object):** sets the given object in the application scope.
 **public Object getAttribute(String name):** Returns the attribute for the specified name.
  **public Enumeration getInitParameterNames():** Returns the names of the context's initialization parameters as an Enumeration of String objects.
  **public void removeAttribute(String name):** Removes the attribute with the given name from the servlet context.

### Example of ServletContext to get the initialization parameter

In this example, we are getting the initialization parameter from the web.xml file and printing the value of the initialization parameter. Notice that the object of ServletContext represents the application scope. So if we change the value of the parameter from the web.xml file, all the servlet classes will get the changed value. So we don't need to modify the servlet. So it is better to have the common information for most of the servlets in the web.xml file by context-param element. Let's see the simple example:

  
**DemoServlet.java**

    1.  import java.io.*;
    2.  import javax.servlet.*;
    3.  import javax.servlet.http.*;
    
    6.  public  class DemoServlet extends HttpServlet{
    7.  public  void doGet(HttpServletRequest req,HttpServletResponse res)
    8.  throws ServletException,IOException
    9.  {
    10.  res.setContentType("text/html");
    11.  PrintWriter pw=res.getWriter();
    
    13.  //creating ServletContext object
    14.  ServletContext context=getServletContext();
    
    16.  //Getting the value of the initialization parameter and printing it
    17.  String driverName=context.getInitParameter("dname");
    18.  pw.println("driver name is="+driverName);
    
    20.  pw.close();
    
    22.  }}

**web.xml**

    1.  < web-app>
    
    2.  < servlet>
    3.  < servlet-name>sonoojaiswal< /servlet-name>
    4.  < servlet-class>DemoServlet< /servlet-class>
    5.  < /servlet>
    
    6.  < context-param>
    7.  < param-name>dname< /param-name>
    8.  < param-value>sun.jdbc.odbc.JdbcOdbcDriver< /param-value>
    9.  < /context-param>
    
    10.  < servlet-mapping>
    11.  < servlet-name>sonoojaiswal< /servlet-name>
    12.  < url-pattern>/context< /url-pattern>
    13.  < /servlet-mapping>
    
    14.  < /web-app>


 

## Servlet HttpSession Login and Logout Example

We can bind the objects on HttpSession instance and get the objects by using setAttribute and getAttribute methods.


    8.  public  class LoginServlet extends HttpServlet {
    9. 
    10.  protected  void doPost(HttpServletRequest request, HttpServletResponse response)
    11.  throws ServletException, IOException {
    12. 
    13.  response.setContentType("text/html");
    14.  PrintWriter out=response.getWriter();
    15.  request.getRequestDispatcher("link.html").include(request, response);
    
    16.  String name=request.getParameter("name");
    17.  String password=request.getParameter("password");
    
    18.  if(password.equals("admin123")){
    19.  out.print("Welcome, "+name);
    20.  HttpSession session=request.getSession();
    21.  session.setAttribute("name",name);
    22.  }
    23.  else{
    24.  out.print("Sorry, username or password error!");
    25.  request.getRequestDispatcher("login.html").include(request, response);
    26.  }
    27.  out.close();
    28.  }
    29.  }
    30. 

## Servlet with Annotation (feature of servlet3)


Annotation represents the metadata. If you use annotation, deployment descriptor (web.xml file) is not required. But you should have tomcat7 as it will not run in the previous versions of tomcat. @WebServlet annotation is used to map the servlet with the specified name.

