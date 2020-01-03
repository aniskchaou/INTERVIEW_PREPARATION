

## Factory method pattern
In class-based programming, the factory method pattern is a creational pattern that uses factory methods **to deal with the problem of creating objects without having to specify the exact class of the object that will be created.** 
![Related image](https://www.researchgate.net/profile/Awny_Alnusair/publication/262572084/figure/fig6/AS:507160770682880@1497927958062/Structure-of-the-Factory-Method-design-pattern-in-UML.png)

## Product

    public interface Shape {
       void draw();
    }

## ConcreteProduct

    public class Square implements Shape {
    
       @Override
       public void draw() {
          System.out.println("Inside Square::draw() method.");
       }
    }
    public class Square implements Shape {
    
       @Override
       public void draw() {
          System.out.println("Inside Square::draw() method.");
       }
    }

## ConcreteCreator

    public class ShapeFactory {
    	
       //use getShape method to get object of type shape 
       public Shape getShape(String shapeType){
          if(shapeType == null){
             return null;
          }		
          if(shapeType.equalsIgnoreCase("CIRCLE")){
             return new Circle();
             
          } else if(shapeType.equalsIgnoreCase("RECTANGLE")){
             return new Rectangle();
             
          } else if(shapeType.equalsIgnoreCase("SQUARE")){
             return new Square();
          }
          
          return null;
       }
    }

## Main

    public class FactoryPattern {
    
       public static void main(String[] args) {
          ShapeFactory shapeFactory = new ShapeFactory();
    
          //get an object of Circle and call its draw method.
          Shape shape1 = shapeFactory.getShape("CIRCLE");
    
          //call draw method of Circle
          shape1.draw();
    
          //get an object of Rectangle and call its draw method.
          Shape shape2 = shapeFactory.getShape("RECTANGLE");
    
          //call draw method of Rectangle
          shape2.draw();
    
          //get an object of Square and call its draw method.
          Shape shape3 = shapeFactory.getShape("SQUARE");
    
          //call draw method of square
          shape3.draw();
       }
    }
