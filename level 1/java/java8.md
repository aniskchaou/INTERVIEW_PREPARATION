## Lambda Expressions

    public class FirstLambdaExp {
     
        public static void main(String a[]){
             
            // create a thread with old way of java programming.
            // CASE - 1
            new Thread(new Runnable(){
                public void run(){
                    System.out.println("In run method, without lambda expression");
                }
            }).start();
             
            // now create the above code using lambda expression.
            // CASE - 2
            new Thread(() -> System.out.println("In run method, lambda expression")).start();
        }
     
    }
## Interface Default Methods



    public interface FirstInterface {
     
        default void someMethod(){
            System.out.println("from FirstInterface...");
        }
    }

Wait, what is default here? This is the new way of declaring the method body in Java 8 for an interface. As seen above, default methods comes along with implementation. You dont need to implement default methods if your class implements above interface, below is an example:



 

    public class TestMe implements FirstInterface {
     
        public static void main(String[] args) {
            new TestMe().someMethod();
        }
    }

We can also override the default methods, but you dont need to specify default in the method signature.


 

    public class TestMe implements FirstInterface {
     
        @Override
        public void someMethod(){
            System.out.println("from TestMe class...");
        }
    }

## forEach method example with Map

forEach is a new method introduced in Java 8 to iterate over collections. Here is an example on forEach method to iterate over Map.

       public  class A{
    
     public static void main(String args[]){  
    
       Map<String, String> countryMap = new HashMap<>();
            countryMap.put("India", "Delhi");
            countryMap.put("USA", "Washington, D.C.");
            countryMap.put("Japan", "Tokyo");
            countryMap.put("Canada", "Ottawa");
     
           countryMap.forEach((k,v)->System.out.println("Country: "+k+" : Capital: "+v));
        }
       
    }

## Java 8 Streams

  

First of all, please note that  _"Streams are not collections"_. java.util.stream is introduced to process elements in sequence. Streams are wrappers for collections and arrays. They wrap an existing collection to support operations expressed with lambdas, so you specify what you want to do, not how to do it. 

    public class StreamExample {
     
        public static void main(String a[]) {
     
            List<String> vechicles = Arrays.asList("bus", "car", "bicycle", "flight", "train");
     
            vechicles.stream().filter(str->str.length() > 3).map(String::toUpperCase).sorted().forEach(System.out::println);;
        }
    }

## Date and Time API

Prior to Java 8, Java Date and Time has below drawbacks:

The existing classes java.util.Date and SimpleDateFormatter are not thread-safe.
Poor API design. 

Following are some of the important classes introduced in java.time package.

Local: Simplified date-time API with no complexity of timezone handling.

Zoned: Specialized date-time API to deal with various timezones.

    import java.time.LocalDate;
    import java.time.Month;
     
    public class LocalDateEx {
     
        public static void main(String[] args) {
     
            // get current date
            LocalDate currDate = LocalDate.now();
            System.out.println("current date: "+currDate);
     
            // create date object with values
            LocalDate myBday = LocalDate.of(1982, Month.MARCH, 23);
            System.out.println("Created date: "+myBday);
     
            // get date on given year on 'n'th day
            LocalDate randomDay = LocalDate.ofYearDay(2015, 100);
            System.out.println("Random date: "+randomDay);
        }
    }
