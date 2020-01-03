

## Strategy pattern
the strategy pattern (also known as the policy pattern) is a behavioral software design pattern that enables selecting an algorithm at runtime. Instead of implementing a single algorithm directly, **code receives run-time instructions as to which in a family of algorithms to use.**

![](https://upload.wikimedia.org/wikipedia/commons/3/39/Strategy_Pattern_in_UML.png)

# Context

    public class Context {
       private Strategy strategy;
    
       public Context(Strategy strategy){
          this.strategy = strategy;
       }
    
       public int executeStrategy(int num1, int num2){
          return strategy.doOperation(num1, num2);
       }
    }

## Strategy

public interface Strategy {
     public int doOperation(int num1, int num2);
}

## OperationAdd

    public class OperationAdd implements Strategy{
       @Override
       public int doOperation(int num1, int num2) {
          return num1 + num2;
       }
    }

## OperationSustract

    public class OperationSubstract implements Strategy{
       @Override
       public int doOperation(int num1, int num2) {
          return num1 - num2;
       }
    }

## Main

    public class StrategyPatternDemo {
       public static void main(String[] args) {
          Context context = new Context(new OperationAdd());		
          System.out.println("10 + 5 = " + context.executeStrategy(10, 5));
    
          context = new Context(new OperationSubstract());		
          System.out.println("10 - 5 = " + context.executeStrategy(10, 5));
    
          context = new Context(new OperationMultiply());		
          System.out.println("10 * 5 = " + context.executeStrategy(10, 5));
       }
    }
