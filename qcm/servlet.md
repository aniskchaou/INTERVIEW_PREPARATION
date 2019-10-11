## 1) How many objects of a servlet is created?

Only ***one object at the time of first request*** by servlet or web container.

## 2) What is the life-cycle of a servlet?

1.  Servlet is loaded
2.  servlet is instantiated
3.  servlet is initialized
4.  service the request
5.  servlet is destroyed

## What are the life-cycle methods for a servlet?

 - **public void init(ServletConfig config)**

It is invoked only once when first request comes for the servlet

 - **public void service(ServletRequest request,ServletResponse)**

It is invoked at each request.

 - **public void destroy()**

It is invoked only once when servlet is unloaded.

## 4) Who is responsible to create the object of servlet?

The web container or servlet container.

## 5) When servlet object is created?

At the time of first request.

## 8) What is difference between GenericServlet and HttpServlet?

 - The GenericServlet is protocol independent
 - HttpServlet is HTTP protocol specific.

## 10) What is the purpose of RequestDispatcher Interface?

The RequestDispacher interface ***provides the facility of dispatching the request to another resource it may be html, servlet or jsp.*** 

    RequestDispatcher rd=req.getRequestDispatcher("Servlet2");   
    rd.forward(req, resp);

## 11) Can you call a jsp from the servlet?

Yes, one of the way is RequestDispatcher interface for example:

     RequestDispatcher rd=request.getRequestDispatcher("/login.jsp");
     rd.forward(request,response);

## Difference between forward() method and sendRedirect() method ?

***forward() method***

 - sends the same request to another resource.
 - method works at server side.

***sendRedirect() method***
sendRedirect() method works at client side.
 sendRedirect() method sends new request always because it uses the URL bar of the browser.
 

## 13) What is difference between ServletConfig and ServletContext?

 - The container creates object of ServletConfig for each servlet
 - ServletContext is created for  web application.

## load on startup in web.xml

The  **load-on-startup**  element of  **web-app**  loads the servlet at the time of deployment or server start if value is positive. 

     < web-app>
     < servlet>
    < servlet-name>servlet1< /servlet-name>
     < servlet-class>com.javatpoint.FirstServlet< /servlet-class>
     < load-on-startup>0< /load-on-startup>
     < /servlet>
    
     < servlet>
     < servlet-name>servlet2< /servlet-name>
    < servlet-class>com.javatpoint.SecondServlet</servlet-class>
     < load-on-startup>1< /load-on-startup>
    < /servlet>
     < /web-app>

 

## 23) What is war file?

A war (web archive) file specifies the web elements. A servlet or jsp project can be converted into a war file. 
***Moving one servlet project from one place to another will be fast as it is combined into a single file.***

## 30) What is the use of attribute in servlets?

Attribute is a map object that can be used to set, get or remove in request, session or application scope. ***It is mainly used to share information between one servlet to another.***

## How to get the IP address of client in servlet?

  `request.getRemoteAddr()` 

## What is a deployment descriptor?

The deployment descriptor **is a configuration file for the web application and its name is web.xml** and it resides in WEB-INF directory. 

**With servlet 3.0 annotations, we can remove a lot of clutter from web.xml** by configuring servlets, filters, and listeners using annotations.


## What is servlet attributes and their scope?

Servlet attributes are used for inter-servlet communication, we can set, get and remove attributes in web application. There are three scopes for servlet attributes – request scope, session scope and application scope.

ServletRequest, HttpSession, and ServletContext interfaces provide methods to get/set/remove attributes from request, session and application scope respectively.

***Servlet attributes are different from init parameters defined in web.xml for ServletConfig or ServletContext.***

## Are Servlets Thread Safe? How to achieve thread-safety in servlets?

service methods such as doGet() or doPost() ***are getting called in every client request and since servlet uses multithreading, we should provide thread safety in these method***


## What is difference between ServletConfig and ServletContext?

Some of the differences between ServletConfig and ServletContext are:

-   ServletConfig is a unique object per servlet whereas ServletContext is a unique object for complete application.
-   ServletConfig is used to provide init parameters to the servlet whereas ServletContext is used to provide application level init parameters that all other servlets can use.
-   We can’t set attributes in ServletConfig object whereas we can set attributes in ServletContext that other servlets can use in their implementation.

## **HTTP Session**

    // Create a session object if it is already not created.
    
    HttpSession session = request.getSession(true);
    
    // Get session creation time.
    
    Date createTime = new Date(session.getCreationTime());
    
    // Get last access time of this web page.
    
    Date lastAccessTime = new Date(session.getLastAccessedTime());
    
    String title = "Welcome Back to my website";
    
    Integer visitCount = new Integer(0);
    
    String visitCountKey = new String("visitCount");
    
    String userIDKey = new String("userID");
    
    String userID = new String("ABCD");
    
    // Check if this is new comer on your web page.
    
    if (session.isNew()) {
    
    title = "Welcome to my website";
    
    session.setAttribute(userIDKey, userID);
    
    } else {
    
    visitCount = (Integer)session.getAttribute(visitCountKey);
    
    visitCount = visitCount + 1;
    
    userID = (String)session.getAttribute(userIDKey);
    
    }



## Servlets Packages

Servlets can be created using the javax.servlet and javax.servlet.http packages, which are a standard part of the Java's enterprise edition

**Java servlets have been created and compiled just like any other Java class. After you install the servlet packages and add them to your computer's Classpath, you can compile servlets with the JDK's Java compiler or any other current compiler.**

## Methods to Set HTTP Status Code

These methods are available with HttpServletResponse object.

 - public void setStatus ( int statusCode )

 - public void sendRedirect(String url)

 - public void sendError(int code, String message)


## What do you mean by Servlet Context?

**Ans:**  Servlet Context is basically referred to as an object which has information regarding application and the Web Container. 


**There are some important methods of servlet context which are given below:**

**a)** **getInitParameter ()**  – return the value of parameter.

**b)** **getInitParameterNames ()**  – returns the name of parameter.

**c)** **void setAttribute ()**  – used to set the values of attributes.

**d) void getAttribute ()**  – used to get the values of attributes.

**e) void removeAttribute () –**  used to remove the attribute.

## java web structure

**Web Application Root Directory**  – This is the main or Root folder of web application. 

 - **WEB-INF-** This is the special directory under web application root directory.
 - **WEB-INF/lib-** All the required jar files or third party jar files will be placed inside this directory.
 - **WEB-INF/classes-** All the java code including servlets for the web application will go inside classes folder.
 - **web.xml**  – web.xml resides under WEB-INF folder and it is also known as deployment descriptor. All the configuration of web
   application like servlets configuration , filters configuration ,
   welcome file list etc are configured in web.xml. We will discuss
   web.xml in detail


 - ***META-INF/MAINFEST.MF-**** This is the manifest file
