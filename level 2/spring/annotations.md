## Core Spring Framework Annotations

## @Required:

The @Required annotation in spring is a method-level annotation applied to the setter method of a bean property and thus making the setter-injection mandatory.

Example

1.  public  class Machine
2.  {
3.  private Integer cost;
4.  @Required
5.  public  void setCost(Integer cost)
6.  {
7.  this.cost = cost;
8.  }
9.  public Integer getCost()
10.  {
11.  return cost;
12.  }
13.  }

## @Autowired:

When we use @Autowired annotation, the spring container auto-wires the bean by matching data-type. Autowiring feature of spring framework enables you to inject the object dependency implicitly. It internally uses setter or constructor injection.

Example

1.  @Component
2.  public  class Customer
3.  {
4.  private Person person;
5.  @Autowired
6.  public Customer(Person person)
7.  {
8.  this.person=person;
9.  }
10.  }

## @Configuration:

Spring Configuration annotation indicates that the class has @Bean definition methods. So Spring container can process the class and generate Spring Beans to be used in the application.

Example

1.  @Configuration
2.  public  class Vehicle
3.  {
4.  @Bean
5.   Vehicle engine()
6.  {
7.  return  new Vehicle();
8.  }
9.  }
example
@Configuration
public class MyConfiguration {

    @Bean
    public MyBean myBean() {
        return new MyBean();
    }
    
}

public class MySpringApp {

    public static void main(String[] args) {
        AnnotationConfigApplicationContext ctx = new AnnotationConfigApplicationContext();
        ctx.register(MyConfiguration.class);
        ctx.refresh();

        // MyBean mb1 = ctx.getBean(MyBean.class);

        // MyBean mb2 = ctx.getBean(MyBean.class);

        ctx.close();
    }

}

## @ComponentScan:

It is used when we want to scan a package for beans. It is used with the annotation @Configuration. We can also specify the base packages to scan for Spring Components.

Example

1.  @ComponentScan(basePackages = "com.javatpoint")
2.  @Configuration
3.  public  class ScanComponent
4.  {
5.  // ...
6.  }
@Bean:
It is a method-level annotation.

Example

1.  @Bean
2.  public BeanExample beanExample()
3.  {
4.  return  new BeanExample ();
5.  }
Spring Framework Stereotype Annotations

## @Component:

It is a class-level annotation. It is used to mark a Java class as a bean. A Java class annotated with @Component is found during the classpath. The Spring Framework pick it up and configure it in the application context as a Spring Bean.

Example

1.  @Component
2.  public  class Student
3.  {
4.  .......
5.  }
example
@SpringBootApplication
public class DemoApplication {

    public static void main(String[] args) {
        ConfigurableApplicationContext applicationContext = SpringApplication.run(DemoApplication.class, args);
        ComponentDemo componentDemo = (ComponentDemo) applicationContext.getBean("componentDemo");
        System.out.println(componentDemo.getValue());
    }
}

@Component
class ComponentDemo {
    public String getValue() {
        return "Hello World";
    }
}

## @Controller:

The @Controller is a class-level annotation. It is a specialization of @Component. It marks a class as a web request handler. It is often used to serve web pages. By default, it returns a string that indicates which route to redirect. It is mostly used with @RequestMapping annotation.

Example

1.  @Controller
2.  @RequestMapping("books")
3.  public  class BooksController
4.  {
5.  @RequestMapping(value = "/{name}", method = RequestMethod.GET)
6.  public Employee getBooksByName()
7.  {
8.  return booksTemplate;
9.  }
10.  }
@Service:
It is also used at class level. It tells the Spring that class contains the business logic.

Example

1.  package com.javatpoint;
2.  @Service
3.  public  class TestService
4.  {
5.  public  void service1()
6.  {
7.  //business code
8.  }
9.  }
@Repository:
It is a class-level annotation. The repository is a DAOs (Data Access Object) that access the database directly. The repository does all the operations related to the database.

1.  package com.javatpoint;
2.  @Repository
3.  public  class TestRepository
4.  {
5.  public  void delete()
6.  {
7.  //persistence code
8.  }
9.  }

## Spring Boot Annotations

@EnableAutoConfiguration: It auto-configures the bean that is present in the classpath and configures it to run the methods.
@SpringBootApplication: It is a combination of three annotations @EnableAutoConfiguration, @ComponentScan, and @Configuration.
Spring MVC and REST Annotations
@RequestMapping: It is used to map the web requests. It has many optional elements like consumes, header, method, name, params, path, produces, and value. We use it with the class as well as the method.
Example

1.  @Controller
2.  public  class BooksController
3.  {
4. 
5.  @RequestMapping("/computer-science/books")
6.  public String getAllBooks(Model model)
7.  {
8.  
9.  return  "bookList";
10.  }
GET
@GetMapping
@GetMapping
    List<Produit> getProduit(){
        return produitService.getProduit();
    }
@RequestMapping(method = RequestMethod.GET)
@RequestMapping(value="/contacts",method=RequestMethod.GET)
   private List<Contact> getAll() {
    return cr.findAll();
   }
  
  @RequestMapping(value="/contacts/{id}",method=RequestMethod.GET)
   private Optional<Contact> getContactById(@PathVariable Long id) {
    return cr.findById(id);
   }
POST
@PostMapping
   @PostMapping
    void addProduit(@RequestBody Produit produit) {
        produitService.addProduit(produit);
    }
@RequestMapping(method = RequestMethod.POST)
 @RequestMapping(value="/contacts",method=RequestMethod.POST)
   private Contact save(@RequestBody Contact c) {
    return cr.save(c);
   }
PUT
@PutMapping
@PutMapping
    void updateProduit( @RequestBody Produit produit) {
        produitService.updateProduit(produit);
    }
@RequestMapping(method = RequestMethod.PUT)
    @RequestMapping(value="/contacts/{id}",method=RequestMethod.PUT)
   private Contact update(@PathVariable Long id,@RequestBody Contact c) {
       c.setId(id);
    return cr.save(c);
   }
DELETE
@DeleteMapping:
@DeleteMapping("/{id}")
    void deleteProduit(@PathVariable Long id) {
        produitService.removeProduitById(id);
    }
@RequestMapping(method = RequestMethod.DELETE)
 @RequestMapping(value="/contacts/{id}",method=RequestMethod.DELETE)
   private boolean delete(@PathVariable Long id) {
    cr.deleteById(id);
    return true;
   }
@RequestBody: It is used to bind HTTP request with an object in a method parameter.
@ResponseBody: It binds the method return value to the response body. It tells the Spring Boot Framework to serialize a return an object into JSON and XML format.
@PathVariable: It is used to extract the values from the URI. It is most suitable for the RESTful web service, where the URL contains a path variable. We can define multiple @PathVariable in a method.
@RequestParam: It is used to extract the query parameters form the URL. It is also known as a query parameter. It is most suitable for web applications. It can specify default values if the query parameter is not present in the URL.
@RequestHeader: It is used to get the details about the HTTP request headers. We use this annotation as a method parameter.
@RestController: It can be considered as a combination of @Controller and @ResponseBody annotations**.**
@RequestAttribute: It binds a method parameter to request attribute. It provides convenient access to the request attributes from a controller method. With the help of @RequestAttribute annotation, we can access objects that are populated on the server-side.