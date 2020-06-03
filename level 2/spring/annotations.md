## Core Spring Framework Annotations

## @Required:

The @Required annotation in spring is a method-level annotation **applied to the setter method of a bean property and thus making the setter-injection mandatory.**


    class Machine {
      private Integer cost;
    
      @Required
      public void setCost(Integer cost) {
        this.cost = cost;
      }
    
      public Integer getCost() {
        return cost;
      }
    }

## @Autowired:

 Autowiring feature of spring framework **enables you to inject the object dependency implicitly.** It internally uses setter or constructor injection.

    @SpringBootApplication
    public class TestSpringApplication {
      @Autowired
      private Person person;
      
      public static void main(String[] args) {
        SpringApplication.run(TestSpringApplication.class, args);
      }
    
    }



## @Configuration:

Spring **Configuration annotation indicates that the class has @Bean definition methods.** So Spring container can process the class and generate Spring Beans to be used in the application.

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
        ctx.close();
      }
    }



## @ComponentScan:

It is used when we want to scan a package for beans. 

    @ComponentScan(basePackages = "com.javatpoint")
    @Configuration
    public class ScanComponent {
      // ...
    }



## @Bean:

    @Bean
    public BeanExample beanExample()
    {
    return new BeanExample ();
    } 

## @Component:

It is a class-level annotation. It is used to mark a Java class as a bean. 

    @Component
    class ComponentDemo {
      public String getValue() {
        return "Hello World";
      }
    }
    @SpringBootApplication
    public class DemoApplication {
    
      public static void main(String[] args) {
        ConfigurableApplicationContext applicationContext = SpringApplication.run(DemoApplication.class, args);
        ComponentDemo componentDemo = (ComponentDemo) applicationContext.getBean("componentDemo");
        System.out.println(componentDemo.getValue());
      }
    }

## @Controller:

The @Controller is a class-level annotation. **It marks a class as a web request handler. **It is mostly used with @RequestMapping annotation.

    @Controller
    @RequestMapping("books")
    public class BooksController {
      @RequestMapping(value = "/{name}", method = RequestMethod.GET)
      public Employee getBooksByName() {
        return new Employee();
      }
    }


## @Service

:
 It is also used at class level. **It tells the Spring that class contains the business logic.**

    @Service
    public class TestService {
      public void service1() {
        // business code
      }
    }

## @Repository:

It is a class-level annotation. **The repository is a DAOs (Data Access Object) that access the database directly.** The repository does all the operations related to the database.

    @Repository
    public class TestRepository
    {
      public void delete()
      {
        // persistence code
      }
    }    

   

## @EnableAutoConfiguration

 It auto-configures the bean that is present in the classpath and configures it to run the methods. 

## @SpringBootApplication

 It is a combination of three annotations **@EnableAutoConfiguration,** **@ComponentScan**, and **@Configuration.** 

## @RequestMapping

It is used to map the web requests


    @Controller
    public class BooksController {
      @RequestMapping("/computer-science/books")
      public String getAllBooks(Model model) {
        return "bookList";
      }
    }

 - **GET** @GetMapping  
 - **POST** @PostMapping  
 - **PUT** @PutMapping  
 - **DELETE** @DeleteMapping
