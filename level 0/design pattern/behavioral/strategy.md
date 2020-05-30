

## Strategy pattern
the strategy pattern (also known as the policy pattern) is a behavioral software design pattern that enables selecting an algorithm at runtime. Instead of implementing a single algorithm directly, **code receives run-time instructions as to which in a family of algorithms to use.**

![](https://upload.wikimedia.org/wikipedia/commons/3/39/Strategy_Pattern_in_UML.png)


class Add implements StrategyOperation{
     @Override
    public void doOperation(int number1, int number2) {
      System.out.println( number1+number2);
    }
}

class Substract implements StrategyOperation {

    @Override
    public void doOperation(int number1, int number2) {
      System.out.println( number1-number2);
    }
    
}

class Multiply implements StrategyOperation{

    @Override
    public void doOperation(int number1, int number2) {
       System.out.println( number1*number2);
    }
    
}

class Devide implements StrategyOperation{

    @Override
    public void doOperation(int number1, int number2) {
        System.out.println(number1/number2); ;
    }
    
}
interface StrategyOperation{
    void doOperation(int number1,int number2);
}


class OperationContext{
    StrategyOperation strategy;

    public OperationContext(StrategyOperation strategy) {
        this.strategy = strategy;
    }

    public void setStrategy(StrategyOperation strategy) {
        this.strategy = strategy;
    }
    
    void executeStrategy(int number1,int number2){
        this.strategy.doOperation(number1, number2);
    }
}
    class Client{
        public static void main(String[] args) {
            int number1=1;
            int number2=1;
            
            Add  add=new Add();
            Substract substract=new Substract();
            Multiply multiply=new Multiply();
            Devide devide=new Devide();
            
           OperationContext operationContext=new OperationContext(add);
           operationContext.executeStrategy(number1, number2);
           
           operationContext.setStrategy(substract);
            operationContext.executeStrategy(number1, number2);
            
            operationContext.setStrategy(multiply);
            operationContext.executeStrategy(number1, number2);
            
            operationContext.setStrategy(devide);
            operationContext.executeStrategy(number1, number2);
            
        }
   }
    
