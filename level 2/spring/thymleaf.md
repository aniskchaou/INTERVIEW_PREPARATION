
## Thymeleaf

It is a server side Java template engine for web application. It's main goal is to bring elegant natural templates to your web application.

It can be integrate with Spring Framework and ideal for HTML5 Java web applications.


Our project has the following directly structure.

![Spring Boot thymeleaf view 1](https://static.javatpoint.com/springboot/images/spring-boot-thymeleaf-view1.png)

In our project, we have following files.

// index.html

    1.  <html  lang="en">
    2.  <head>
    3.  <title>Index Page</title>
    4.  </head>
    5.  <body>
    6.  <form  action="save"  method="post">
    7.  <table>
    8.  <tr>
    9.  <td><label  for="user-name">User Name</label></td>
    10.  <td><input  type="text"  name="name"></input></td>
    11.  </tr>
    12.  <tr>
    13.  <td><label  for="email">Email</label></td>
    14.  <td><input  type="text"  name="email"></input></td>
    15.  </tr>
    16.  <tr>
    17.  <td></td>
    18.  <td><input  type="submit"  value="Submit"></input></td>
    19.  </tr>
    20.  </table>
    21.  </form>
    22.  </body>
    23.  </html>

// user-data.html

    1.  <html  xmlns:th="https://thymeleaf.org">
    2.  <table>
    3.  <tr>
    4.  <td><h4>User Name: </h4></td>
    5.  <td><h4  th:text="${user.name}"></h4></td>
    6.  </tr>
    7.  <tr>
    8.  <td><h4>Email ID: </h4></td>
    9.  <td><h4  th:text="${user.email}"></h4></td>
    10.  </tr>
    11.  </table>
    12.  </html>
    
    // User.java
    
    1.  package com.javatpoint;
    2.  public  class User {
    3.  String name;
    4.  String email;
    5.  public String getName() {
    6.  returnname;
    7.  }
    8.  public  void setName(String name) {
    9.  this.name = name;
    10.  }
    11.  public String getEmail() {
    12.  returnemail;
    13.  }
    14.  public  void setEmail(String email) {
    15.  this.email = email;
    16.  }
    
    18.  }



// HomeController.java

    1.  package com.javatpoint;
    2.  import org.springframework.web.bind.annotation.ModelAttribute;
    3.  import org.springframework.web.bind.annotation.RequestMapping;
    4.  import org.springframework.web.bind.annotation.RequestMethod;
    5.  import org.springframework.web.servlet.ModelAndView;
    6.  import org.springframework.stereotype.Controller;
    7.  @Controller
    8.  public  class HomeController {
    9.  @RequestMapping("/")
    10.  public String index(){
    11.  return"index";
    12.  }
    13.  @RequestMapping(value="/save", method=RequestMethod.POST)
    14.  public ModelAndView save(@ModelAttribute User user){
    15.  ModelAndView modelAndView = new ModelAndView();
    16.  modelAndView.setViewName("user-data");
    17.  modelAndView.addObject("user", user);
    18.  returnmodelAndView;
    19.  }
    20.  }

// SpringBootExampleApplication.java

    1.  package com.javatpoint;
    2.  import org.springframework.boot.SpringApplication;
    3.  import org.springframework.boot.autoconfigure.SpringBootApplication;
    4.  @SpringBootApplication
    5.  public  class SpringBootExample {
    6.  public  static  void main(String[] args) {
    7.  SpringApplication.run(SpringBootExample.class, args);
    8.  }
    9.  }

Output:

After running the application. It produce the following output.

Index Page

![Spring Boot thymeleaf view 2](https://static.javatpoint.com/springboot/images/spring-boot-thymeleaf-view2.png)

Entering details

![Spring Boot thymeleaf view 3](https://static.javatpoint.com/springboot/images/spring-boot-thymeleaf-view3.png)

After submitting form

![Spring Boot thymeleaf view 4](https://static.javatpoint.com/springboot/images/spring-boot-thymeleaf-view4.png)

----------

