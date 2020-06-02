AOP (Aspect-Oriented programming)
Aspect Oriented Programming is sensibly new and it is not a replacement for Object Oriented Programming. In fact, AOP is another way of organizing your Program Structure. for example, when a method is execute, Spring AOP can hijack the executing method, and add extra functionality before or after the method execution.

For example: Logging, Transaction and security are some Aspects. In Logging we may have different aspect i.e. time calculation logging, simple in and out message logging and so on..

To be more clear I will use some diagrams:

What is Aspect?

|---------------------|------------------|------------------|
|      Aspect         =     Point cut    +  Advice          |
|---------------------|------------------|------------------|
|                     | Where the aspect | What code is     |
|                     |  is applied      |  executed.       |
|---------------------|------------------|------------------|
Aspect = Point cut + Advice

Type of Advice methods

enter image description here

Aspect and pointcut expression
public class EmployeeCRUDAspect {
      
    @Before("execution(* EmployeeManager.getEmployeeById(..))")         //point-cut expression
    public void logBeforeV1(JoinPoint joinPoint)
    {
        System.out.println("EmployeeCRUDAspect.logBeforeV1() : " + joinPoint.getSignature().getName());
    }
}
Methods (joint points)
@Component
public class EmployeeManager
{
    public EmployeeDTO getEmployeeById(Integer employeeId) {
        System.out.println("Method getEmployeeById() called");
        return new EmployeeDTO();
    }
}
Main
public class TestAOP
{
    @SuppressWarnings("resource")
    public static void main(String[] args) {
  
        ApplicationContext context = new ClassPathXmlApplicationContext
                            ("com/howtodoinjava/demo/aop/applicationContext.xml");
 
        EmployeeManager manager = context.getBean(EmployeeManager.class);
  
        manager.getEmployeeById(1);
    }
}
Output
EmployeeCRUDAspect.logBeforeV1() : getEmployeeById
Method getEmployeeById() called