## **What's the purpose of Static methods and static variables?**

  When there is a requirement to  **share a method or a variable between multiple objects of a class**

## **How can we pass argument to a function by reference instead of pass by value?**

In java, we can pass argument to a function only by value and not by reference.




## **Can a class have multiple constructors?**

Ans: Yes, a class can have multiple constructors with different parameters.


## **What's difference between Stack and Queue?**

**stack**  is based on Last in First out (LIFO)  **queue**  is based on FIFO (First In First Out) principle.




## **Is the following class declaration correct?**

```
public abstract final class testClass {
// Class methods and variables
}

```

**`The above class declaration is incorrect as an abstract class can't be declared as Final.`**




## Java LocalDate Example

```
LocalDate date = LocalDate.now();
LocalDate yesterday = date.minusDays(1);
LocalDate tomorrow = yesterday.plusDays(2);
System.out.println("Today date: "+date);
System.out.println("Yesterday date: "+yesterday);
System.out.println("Tommorow date: "+tomorrow);

```

## Java LocalTime Example: now()

    ```
    
        LocalTime time = LocalTime.now();
        System.out.println(time);
        ```
        ## **GenericMethods**
        public static < E> void printArray(E[] inputArray) {
        
        // Display array elements
        
        for (E element : inputArray) {
        
        System.out.printf("%s ", element);
        
        }
        
        System.out.println();
        
        }
        
        Integer[] intArray = {1, 2, 3, 4, 5};
        
        Double[] doubleArray = {1.1, 2.2, 3.3, 4.4};
        
        Character[] charArray = {'H', 'E', 'L', 'L', 'O'};

## GenericCLassTutorial

    public class GenericCLassTutorial<T> {
    
    //As with generic methods, the type parameter section of a generic class can
    
    //have one or more type parameters separated by commas.
    
    private T t;
    
    public void add(T t) {
    
    this.t = t;
    
    }
    
    public T get() {
    
    return t;
    
    }
    
    public static void main(String[] args) {
    
    GenericCLassTutorial<Integer> integerBox = new GenericCLassTutorial<Integer>();
    
    GenericCLassTutorial<String> stringBox = new GenericCLassTutorial<String>();
    
    integerBox.add(new Integer(10));
    
    stringBox.add(new String("Hello World"));
    }



