
## Singleton pattern
In software engineering, the singleton pattern is a software design pattern that **restricts the instantiation of a class to one "single" instance.**
![](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fb/Singleton_UML_class_diagram.svg/1024px-Singleton_UML_class_diagram.svg.png)

    ## SingleObject
    public class SingleObject {
    
       //create an object of SingleObject
       private static SingleObject instance = new SingleObject();
    
       //make the constructor private so that this class cannot be
       //instantiated
       private SingleObject(){}
    
       //Get the only object available
       public static SingleObject getInstance(){
          return instance;
       }
    
       public void showMessage(){
          System.out.println("Hello World!");
       }
    }

## Main

    public class SingletonPattern {
       public static void main(String[] args) {
    
          //illegal construct
          //Compile Time Error: The constructor SingleObject() is not visible
          //SingleObject object = new SingleObject();
    
          //Get the only object available
          SingleObject object = SingleObject.getInstance();
    
          //show the message
          object.showMessage();
       }
    }
