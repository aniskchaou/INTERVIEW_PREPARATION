## AOP (Aspect-Oriented programming)

Aspect Oriented Programming is sensibly new and it is not a replacement for Object Oriented Programming. In fact, AOP is another way of organizing your Program Structure. 

**for example, when a method is execute, Spring AOP can hijack the executing method, and add extra functionality before or after the method execution.**

**Aspect = Point cut + Advice**
![enter image description here](https://howtodoinjava.com/wp-content/uploads/2015/01/spring-aop-diagram.jpg)
For example: Logging, Transaction and security are some Aspects. 
![enter image description here](https://media.geeksforgeeks.org/wp-content/uploads/20190313112315/Types-of-Advice-in-AOP.jpg)
## Exemple
    @Component
    public class Alien {
    
        public void show()
        {
            System.out.println("hello world");
        }
    }
    @Component
    @Aspect
    @EnableAspectJAutoProxy
    public class Helper {
        
        @Before("execution(public void show())")
        public void logBefore()
        {
            System.out.println("logging before");
        }
        
        @After("execution(public void show())")
        public void logAfter()
        {
            System.out.println("logging after");
        }
    }

**output**

    logging before
    hello world
    logging after
