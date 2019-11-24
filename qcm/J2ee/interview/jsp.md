## What are the life-cycle methods for a JSP?

 - **public void jspInit()**

It is invoked only once, same as init method of the servlet.
 - **public void _jspService(ServletRequest request,ServletResponse)**

It is invoked at each request, same as service() method of the servlet.

 - **public void jspDestroy()**

It is invoked only once, same as destroy() method of the servlet.

## Give the syntax for JSP comments.

The syntax for JSP comments is:

<%-- Comment --%>

## JSP Objects

 - **request**

 The request object is an instance of the class javax.servlet.http.HttpServletRequest.

 - **response**

JSP also creates the response object which is an instance of class javax.servlet.http.HttpServletResponse. 

 - **session**

 The session object is an instance of the class javax.servlet.http.HttpSession.

 - **The out object**

 the out object is an instance of the class javax.servlet.jsp.JspWriter.

 - **pageContext**

The pageContext object represents the entire JSP page. You can use the pageContext object to get attributes of a page. the pageContext object is an instance of the class javax.servlet.jsp.pagecontext.

 - **application** 

The application object is a representation of JSP page through its life cycle.

 - **config**

The config object is an instance of the class javax.servlet.ServletConfig.

 - **page**

The page object is an instance of a JSP page. By using the page object, you can call any method of the page’s servlet.


 - **exception**

The exception object contains the exception which is thrown from the previous JSP page.

## 15) How is JSP used in the MVC model?

JSP is usually used for presentation in the MVC pattern (Model View Controller ), i.e., it plays the role of the view. 