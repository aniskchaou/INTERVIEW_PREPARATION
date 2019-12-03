
Some of the important Java 8 features are;

1.  [forEach() method in Iterable interface]
2.  [default and static methods in Interfaces]
3.  [Functional Interfaces and Lambda Expressions]
4.  [Java Stream API for Bulk Data Operations on Collections]
5.  [Java Time API]
6.  [Collection API improvements]
7.  [Concurrency API improvements]
8.  [Java IO improvements]
9.  [Miscellaneous Core API improvements]


-
3.  ### forEach() method in Iterable interface
    
 
    
    ```
    
    package com.journaldev.java8.foreach;
    
    import java.util.ArrayList;
    import java.util.Iterator;
    import java.util.List;
    import java.util.function.Consumer;
    import java.lang.Integer;
    
    public class Java8ForEachExample {
    
    	public static void main(String[] args) {
    		
    		//creating sample Collection
    		List<Integer> myList = new ArrayList<Integer>();
    		for(int i=0; i<10; i++) myList.add(i);
    		
    		//traversing using Iterator
    		Iterator<Integer> it = myList.iterator();
    		while(it.hasNext()){
    			Integer i = it.next();
    			System.out.println("Iterator Value::"+i);
    		}
    		
    		//traversing through forEach method of Iterable with anonymous class
    		myList.forEach(new Consumer<Integer>() {
    
    			public void accept(Integer t) {
    				System.out.println("forEach anonymous class Value::"+t);
    			}
    
    		});
    		
    		//traversing with Consumer interface implementation
    		MyConsumer action = new MyConsumer();
    		myList.forEach(action);
    		
    	}
    
    }
    
    //Consumer implementation that can be reused
    class MyConsumer implements Consumer<Integer>{
    
    	public void accept(Integer t) {
    		System.out.println("Consumer impl Value::"+t);
    	}
    
    
    }
    
    ```
    
    The number of lines might increase but forEach method helps in having the logic for iteration and business logic at separate place resulting in higher separation of concern and cleaner code.
    


8.  ### Functional Interfaces and Lambda Expressions
    

    One of the major benefits of functional interface is the possibility to use  **lambda expressions**  to instantiate them. We can instantiate an interface with  [anonymous class].
    
    ```
    
    Runnable r = new Runnable(){
    			@Override
    			public void run() {
    				System.out.println("My Runnable");
    			}};
    
    ```
    
  

11.  ### Java Stream API for Bulk Data Operations on Collections
    
    A new  `java.util.stream`  has been added in Java 8 to perform filter/map/reduce like operations with the collection. Stream API will allow sequential as well as parallel execution. This is one of the best feature for me because I work a lot with Collections and usually with Big Data, we need to filter out them based on some conditions.
    
    Collection interface has been extended with  _stream()_  and  _parallelStream()_  default methods to get the Stream for sequential and parallel execution. Let’s see their usage with simple example.
    
    ```
    
    package com.journaldev.java8.stream;
    
    import java.util.ArrayList;
    import java.util.List;
    import java.util.stream.Stream;
    
    public class StreamExample {
    
    	public static void main(String[] args) {
    		
    		List<Integer> myList = new ArrayList<>();
    		for(int i=0; i<100; i++) myList.add(i);
    		
    		//sequential stream
    		Stream<Integer> sequentialStream = myList.stream();
    		
    		//parallel stream
    		Stream<Integer> parallelStream = myList.parallelStream();
    		
    		//using lambda with Stream API, filter example
    		Stream<Integer> highNums = parallelStream.filter(p -> p > 90);
    		//using lambda in forEach
    		highNums.forEach(p -> System.out.println("High Nums parallel="+p));
    		
    		Stream<Integer> highNumsSeq = sequentialStream.filter(p -> p > 90);
    		highNumsSeq.forEach(p -> System.out.println("High Nums sequential="+p));
    
    	}
    
    }
    
    ```
    
    If you will run above example code, you will get output like this:
    
    ```
    
    High Nums parallel=91
    High Nums parallel=96
    High Nums parallel=93
    High Nums parallel=98
    High Nums parallel=94
    High Nums parallel=95
    High Nums parallel=97
    High Nums parallel=92
    High Nums parallel=99
    High Nums sequential=91
    High Nums sequential=92
    High Nums sequential=93
    High Nums sequential=94
    High Nums sequential=95
    High Nums sequential=96
    High Nums sequential=97
    High Nums sequential=98
    High Nums sequential=99
    
    ```
    

    

13.  ### Java Time API
    
It has always been hard to work with Date, Time and Time Zones in java. There was no standard approach or API in java for date and time in Java. One of the nice addition in Java 8 is the  `java.time`  package that will streamline the process of working with time in java.

Just by looking at Java Time API packages, I can sense that it will be very easy to use. It has some sub-packages  `java.time.format`  that provides classes to print and parse dates and times and  `java.time.zone`  provides support for time-zones and their rules.

The new Time API prefers enums over integer constants for months and days of the week. One of the useful class is  `DateTimeFormatter`  for converting datetime objects to strings.


