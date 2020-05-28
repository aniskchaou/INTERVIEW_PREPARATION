## Factory method pattern
![enter image description here](https://www.dofactory.com/images/diagrams/net/factory.gif)
 the factory method pattern is a creational pattern that uses factory methods to deal with the problem of creating objects without having to specify the exact class of the object that will be created.
**Transport.java**

    abstract class  Transport{
        public abstract String drive();
       
    }
**Car .java**

    class Car extends Transport{
    
        @Override
        public String drive() {
            return "drive a car";
        }
        
    }

**Bike .java**

    class Bike extends Transport{
    
        @Override
        public String drive() {
            return "drive a Bike";
        }
        
    }
**TransportFactory.java**

    abstract class TransportFactory{
        abstract Transport create();
    }
**BikeFactory .java**

    class BikeFactory extends TransportFactory{
    
        @Override
        Transport create() {
           return new Bike();
        }
        
    }

**CarFactory .java**

    class CarFactory extends TransportFactory{
    
        @Override
        Transport create() {
           return new Car();
        }
        
    }

**Client.java**

    class Client{
        
        public static void main(String[] args) {
            TransportFactory  bikeFactory=new BikeFactory();
            Transport bike=bikeFactory.create();
            System.out.println(bike.drive());
            
             TransportFactory  carFactory=new CarFactory();
            Transport car=carFactory.create();
            System.out.println(car.drive());
            
        }
    }
