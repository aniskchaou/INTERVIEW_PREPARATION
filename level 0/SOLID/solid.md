
## SOLID

## SRP : The Single Responsibility Principle

A class should have one, and only one, reason to change.
**Example**
The following example is a TypeScript class that defines a  `Person`, this class should not include email validation because that is not related with a person behaviour:

```
class Person {
    public name : string;
    public surname : string;
    public email : string;
    constructor(name : string, surname : string, email : string){
        this.surname = surname;
        this.name = name;
        if(this.validateEmail(email)) {
          this.email = email;
        }
        else {
            throw new Error("Invalid email!");
        }
    }
    validateEmail(email : string) {
        var re = /^([\w-]+(?:\.[\w-]+)*)@((?:[\w-]+\.)*\w[\w-]{0,66})\.([a-z]{2,6}(?:\.[a-z]{2})?)$/i;
        return re.test(email);
    }
    greet() {
        alert("Hi!");
    }
}
```

We can improve the class above by removing the responsibility of email validation from the Person class and creating a new  `Email`  class that will have that responsibility:

```
class Email {
    public email : string;
    constructor(email : string){
        if(this.validateEmail(email)) {
          this.email = email;
        }
        else {
            throw new Error("Invalid email!");
        }        
    }
    validateEmail(email : string) {
        var re = /^([\w-]+(?:\.[\w-]+)*)@((?:[\w-]+\.)*\w[\w-]{0,66})\.([a-z]{2,6}(?:\.[a-z]{2})?)$/i;
        return re.test(email);
    }
}

class Person {
    public name : string;
    public surname : string;
    public email : Email;
    constructor(name : string, surname : string, email : Email){
        this.email = email;
        this.name = name;
        this.surname = surname;
    }
    greet() {
        alert("Hi!");
    }
}
```
## OCP : The Open Closed Principle

You should be able to extend a classes behavior, without modifying it.
**Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.**


**calculator program without OCP**


IOperation.java

    public interface IOperation {
    }

Addition.java

    public class Addition implements IOperation 
    {
        private double firstOperand;
        private double secondOperand;
        private double result = 0.0;
         
        public Addition(double firstOperand, double secondOperand) {
            this.firstOperand = firstOperand;
            this.secondOperand = secondOperand;
        }
     
        //Setters and getters
    }

Substraction.java

    public class Substraction implements IOperation 
    {
        private double firstOperand;
        private double secondOperand;
        private double result = 0.0;
         
        public Substraction(double firstOperand, double secondOperand) {
            this.firstOperand = firstOperand;
            this.secondOperand = secondOperand;
        }
     
        //Setters and getters
    }

ICalculator.java
public interface ICalculator {
    void calculate(IOperation operation);
}
SimpleCalculator.java

    public class SimpleCalculator implements ICalculator 
    {
        @Override
        public void calculate(IOperation operation) 
        {
            if(operation == null) {
                throw new InvalidParameterException("Some message");
            }
             
            if(operation instanceof Addition) {
                Addition obj = (Addition) operation;
                obj.setResult(obj.getFirstOperand() + obj.getSecondOperand());
            } else if(operation instanceof Substraction) {
                Addition obj = (Addition) operation;
                obj.setResult(obj.getFirstOperand() - obj.getSecondOperand());
            } 
        }
    }
 
 **OCP compliant code**


IOperation.java

    public interface IOperation {
        void performOperation();
    }
    Addition.java
    public class Addition implements IOperation 
    {
        private double firstOperand;
        private double secondOperand;
        private double result = 0.0;
         
        public Addition(double firstOperand, double secondOperand) {
            this.firstOperand = firstOperand;
            this.secondOperand = secondOperand;
        }
     
        //Setters and getters
     
        @Override
        public void performOperation() {
            result = firstOperand + secondOperand;
        }
    }

Substraction.java

    public class Substraction implements IOperation 
    {
        private double firstOperand;
        private double secondOperand;
        private double result = 0.0;
         
        public Substraction(double firstOperand, double secondOperand) {
            this.firstOperand = firstOperand;
            this.secondOperand = secondOperand;
        }
     
        //Setters and getters
     
        @Override
        public void performOperation() {
            result = firstOperand - secondOperand;
        }
    }

ICalculator.java

    public interface ICalculator {
        void calculate(IOperation operation);
    }

SimpleCalculator.java

    public class SimpleCalculator implements ICalculator 
    {
        @Override
        public void calculate(IOperation operation) 
        {
            if(operation == null) {
                throw new InvalidParameterException("Some message");
            }
             
            operation.performOperation();
        }
    }

Now we can add as many operations as we want without changing the original module code. Any new operation will fit in easily. e.g. multiplication operation will be written like this and will work correctly.

Multiplication.java

    public class Multiplication implements IOperation 
    {
        private double firstOperand;
        private double secondOperand;
        private double result = 0.0;
         
        public Multiplication(double firstOperand, double secondOperand) {
            this.firstOperand = firstOperand;
            this.secondOperand = secondOperand;
        }
     
        //Setters and getters
     
        @Override
        public void performOperation() {
            result = firstOperand * secondOperand;
        }
    }

## LSP : The Liskov Substitution Principle

Derived classes must be substitutable for their base classes.
Let’s illustrate in Java:

    class TrasportationDevice
    {
       String name;
       String getName() { ... }
       void setName(String n) { ... }
    
       double speed;
       double getSpeed() { ... }
       void setSpeed(double d) { ... }
    
       Engine engine;
       Engine getEngine() { ... }
       void setEngine(Engine e) { ... }
    
       void startEngine() { ... }
    }
    
    class Car extends TransportationDevice
    {
       @Override
       void startEngine() { ... }
    }

There is no problem here, right? A car is definitely a transportation device, and here we can see that it overrides the startEngine() method of its superclass.

Let’s add another transportation device:

    class Bicycle extends TransportationDevice
    {
       @Override
       void startEngine() /*problem!*/
    }

Everything isn’t going as planned now! Yes, a bicycle is a transportation device, however, it does not have an engine and hence, the method startEngine() cannot be implemented.

These are the kinds of problems that violation of Liskov Substitution Principle leads to, and they can most usually be recognized by a method that does nothing, or even can’t be implemented.

The solution to these problems is a correct inheritance hierarchy, and in our case we would solve the problem by differentiating classes of transportation devices with and without engines. Even though a bicycle is a transportation device, it doesn’t have an engine. In this example our definition of transportation device is wrong. It should not have an engine.

We can refactor our TransportationDevice class as follows:

    class TrasportationDevice
    {
       String name;
       String getName() { ... }
       void setName(String n) { ... }
    
       double speed;
       double getSpeed() { ... }
       void setSpeed(double d) { ... }
    }

Now we can extend TransportationDevice for non-motorized devices.

    class DevicesWithoutEngines extends TransportationDevice
    {  
       void startMoving() { ... }
    }

And extend TransportationDevice for motorized devices. Here is is more appropriate to add the Engine object.

    class DevicesWithEngines extends TransportationDevice
    {  
       Engine engine;
       Engine getEngine() { ... }
       void setEngine(Engine e) { ... }
    
       void startEngine() { ... }
    }

Thus our Car class becomes more specialized, while adhering to the Liskov Substitution Principle.

    class Car extends DevicesWithEngines
    {
       @Override
       void startEngine() { ... }
    }

And our Bicycle class is also in compliance with the Liskov Substitution Principle.

    class Bicycle extends DevicesWithoutEngines
    {
       @Override
       void startMoving() { ... }
    }

## ISP : The Interface Segregation Principle

Make fine grained interfaces that are client specific.

To understand the ISP principle first we need to understand the voilation condition of this and then we refactor it according to ocpprinciple says.So lets move on to the Code Area.

ISP Voilation

     IWorker Interface:
    public interface IWorker {
       public void work();
       public void eat();
      
    }

Developer  Class :

    public class Developer implements IWorker {
    
         @Override
         public void work() {
               // TODO Auto-generated method stub
               System.out.println("Developer working");
    
         }
    
         @Override
         public void eat() {
               // TODO Auto-generated method stub
               System.out.println("developer eating");
    
         }
    
    }

3.Robot  Class :

    public class Robot implements IWorker {
    
         @Override
         public void work() {
               // TODO Auto-generated method stub
               System.out.println("robot is working");
    
         }
    
         @Override
         public void eat() {
               // TODO Auto-generated method stub
               throw new UnsupportedOperationException("cannot eat");
    
         }
    
    }
    
    
 IspTest Class
    
        public class IspTest {
             public static void main(String[] args) {
                   Developer developer = new Developer();
                   Robot robot = new Robot();
                   atCafetera(developer);
                   atCafetera(robot);
                   atWork(developer);
                   atWork(robot);
        
             }
        
             private static void atCafetera(IWorker worker) {
                   // TODO Auto-generated method stub
                   System.out.println("in the cafeteria");
                   worker.eat();
        
             }
        
             private static void atWork(IWorker iWorker) {
                   // TODO Auto-generated method stub
                   System.out.println("at the workstation");
                   iWorker.work();
        
             }
        
        }

OUTPUT :

    in the cafeteria
    developer eating
    in the cafeteria
    Exception in thread "main" java.lang.UnsupportedOperationException: cannot eat
           at isp.voilation.Robot.eat(Robot.java:15)
           at isp.voilation.test.IspTest.atCafetera(IspTest.java:21)
           at isp.voilation.test.IspTest.main(IspTest.java:12)
**ISP Refactor**

IEatable  Interface
    
    public interface IEatable {
         public void startEat();
    
         public void endEat();
    
    }
IWorkable Interface:

    public interface IWorkable {
        
         public void startWork();
        
         public void endWork();
    
    }

    IWorkableEtable  Interface :
        public interface IWorkableIEatable extends IWorkable, IEatable {
        
        }

Worker  Class :
    
    public class Worker implements IWorkable, IEatable {
    
         @Override
         public void startWork() {
               // TODO Auto-generated method stub
               System.out.println("worker start work");
    
         }
    
         @Override
         public void endWork() {
               // TODO Auto-generated method stub
               System.out.println("worker end work");
    
         }
    
         @Override
         public void startEat() {
               // TODO Auto-generated method stub
               System.out.println("worker start eating");
    
         }
    
         @Override
         public void endEat() {
               // TODO Auto-generated method stub
               System.out.println("worker end eating");
    
         }
    
    }
Robot   Class :

    public class Robot implements IWorkable {
    
         @Override
         public void startWork() {
               // TODO Auto-generated method stub
               System.out.println("robot start working");
    
         }
    
         @Override
         public void endWork() {
               // TODO Auto-generated method stub
               System.out.println("robot end working");
    
         }
    
    }

## DIP : The Dependency Inversion Principle

Depend on abstractions, not on concretions

The principle states:

-   High-level modules should not depend on low-level modules. **Both should depend on abstractions.**
-   Abstractions should not depend on details. **Details should depend on abstractions.**

By dictating that both high-level and low-level objects must depend on the same abstraction this design principle inverts the way some people may think about object-oriented programming.
![Image result for the-dependency-inversion-principle](https://upload.wikimedia.org/wikipedia/commons/9/96/Dependency_inversion.png)
# Practical Example(s)

## Violating the DIP



    class Mailer  
    {  
        // Methods for a Mailer class  
    }class SendWelcomeMessage  
    {  
        private $mailer;  
        public function __construct(Mailer $mailer)  
        {  
            $this->mailer = $mailer;  
        }  
    }

## Abiding by the DIP

    interface MailerInterface  
    {  
        public function send();  
    }class SmtpMailer implements MailerInterface  
    {  
        public function send()  
        {  
            // Send an email via SMTP  
        }  
    }class SendSlackMailer implements MailerInterface  
    {  
        public function send()  
        {  
            // Send a message via Slack  
        }  
    }class SendWelcomeMessage  
    {  
        private $mailer;  
        public function __construct(MailerInterface $mailer)  
        {  
            $this->mailer = $mailer;  
        }  
    }

