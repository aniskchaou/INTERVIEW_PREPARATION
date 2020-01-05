EXAM H

QUESTION 1
Given:

1. public class Target {
2. private int i = 0;
3. public int addOne() {
4. return ++i;
5. }
6. }

And:

1. public class Client {
2. public static void main(String[] args){
3. System.out.println(new Target().addOne());
4. }
5. }

Which change can you make to Target without affecting Client?

A. Line 4 of class Target can be changed to return i++;
B. Line 2 of class Target can be changed to private int i = 1;
C. Line 3 of class Target can be changed to private int addOne(){
D. Line 2 of class Target can be changed to private Integer i = 0;

Answer: D
Section: All

Explanation/Reference:

QUESTION 2
Given:

class Animal {
     public String noise() {
          return "peep";
     }
}
class Dog extends Animal {
     public String noise() {
          return "bark";
     }
}
class Cat extends Animal {
     public String noise() {
          return "meow";
     }
}
...
30. Animal animal = new Dog();
31. Cat cat = (Cat)animal;
32. System.out.println(cat.noise());

What is the result?

A. peep
B. bark
C. meow
D. Compilation fails.
E. An exception is thrown at runtime.

Answer: E
Section: All

Explanation/Reference:
 Exception in thread "main" java.lang.ClassCastException: Dog cannot be cast to
Cat at Client.main(Client.java:12)
   
QUESTION 3
Given:

abstract class A {
     abstract void a1();
   
     void a2() {
     }
}
class B extends A {
     void a1() {
     }
   
     void a2() {
     }
}
class C extends B {
     void c1() {
     }
}

And:

A x = new B();
C y = new C();
A z = new C();

What are four valid examples of polymorphic method calls? (Choose four.)

A. x.a2();
B. z.a2();
C. z.c1();
D. z.a1();
E. y.c1();
F. x.a1();

Answer: ABDF
Section: All

Explanation/Reference:

QUESTION 4
Given:

class Employee {
     String name;
     double baseSalary;
   
     Employee(String name, double baseSalary) {
          this.name = name;
          this.baseSalary = baseSalary;
     }
}

public class SalesPerson extends Employee {
     double commission;
   
     public SalesPerson(String name, double baseSalary, double commission) {
          // insert code here Line 13
     }
}

Which two code fragments, inserted independently at line 13, will compile? (Choose two.)

A. super(name, baseSalary);
B. this.commission = commission;
C. super(); this.commission = commission;
D. this.commission = commission; super();
E. super(name, baseSalary); this.commission = commission;
F. this.commission = commission; super(name, baseSalary);
G. super(name, baseSalary, commission);

Answer: AE
Section: All

Explanation/Reference:

QUESTION 5
A team of programmers is involved in reviewing a proposed design for a new utility class.
After some discussion, they realize that the current design allows other classes to access
methods in the utility class that should be accessible only to methods within the utility class itself.

What design issue has the team discovered?

A. Tight coupling
B. Low cohesion
C. High cohesion
D. Loose coupling
E. Weak encapsulation
F. Strong encapsulation

Answer: E
Section: All

Explanation/Reference:

QUESTION 6
Given that:

Gadget has-a Sprocket and Gadget has-a Spring and Gadget is-a Widget and Widget has-a Sprocket
Which two code fragments represent these relationships? (Choose two.)

A. class Widget {
        Sprocket s;
   }
 
   class Gadget extends Widget {
        Spring s;
   }
B. class Widget {
   }
 
   class Gadget extends Widget {
        Spring s1;
        Sprocket s2;
   }
C. class Widget {
        Sprocket s1;
        Spring s2;
   }
 
   class Gadget extends Widget {
   }
D. class Gadget {
        Spring s;
   }
 
   class Widget extends Gadget {
        Sprocket s;
   }
E. class Gadget {
   }
 
   class Widget extends Gadget {
        Sprocket s1;
        Spring s2;
   }
F. class Gadget {
        Spring s1;
        Sprocket s2;
   }
 
   class Widget extends Gadget {
   }
 
Answer: AC
Section: All

Explanation/Reference:



QUESTION 7
Given:

class Pizza {
     java.util.ArrayList toppings;
   
     public final void addTopping(String topping) {
          toppings.add(topping);
     }
     public void removeTopping(String topping) {
          toppings.remove(topping);
     }
}
public class PepperoniPizza extends Pizza {
     public void addTopping(String topping) {
          System.out.println("Cannot add Toppings");
     }   
     public static void main(String[] args) {
          Pizza pizza = new PepperoniPizza();
          pizza.addTopping("Mushrooms");
          pizza.removeTopping("Peperoni");
     }   
}

What is the result?

A. Compilation fails.
B. Cannot add Toppings
C. The code runs with no output.
D. A NullPointerException is thrown in Line 4.

Answer: A
Section: All

Explanation/Reference:

QUESTION 8
Which three statements are true? (Choose three.)

A. A final method in class X can be abstract if and only if X is abstract.
B. A protected method in class X can be overridden by any subclass of X.
C. A private static method can be called only within other static methods in class X.
D. A non-static public final method in class X can be overridden in any subclass of X.
E. A public static method in class X can be called by a subclass of X without explicitly referencing the class X.
F. A method with the same signature as a private final method in class X can be implemented in a
   subclass of X.
G. A protected method in class X can be overridden by a subclass of X only if the subclass is in the same package as X.
 
Answer: BEF
Section: All

Explanation/Reference:

QUESTION 9
Click the Exhibit button.

1. public class Car {
2. private int wheelCount;
3. private String vin;
4. public Car(String vin){
5. this.vin = vin;
6. this.wheelCount = 4;
7. }
8. public String drive(){
9. return "zoom-zoom";
10. }
11. public String getInfo() {
12. return "VIN: " + vin + " wheels: " + wheelCount;
13. }
14. }

And

1. public class MeGo extends Car {
2. public MeGo(String vin) {
3. this.wheelCount = 3;
4. }
5. }

What two must the programmer do to correct the compilation errors? (Choose two.)

A. insert a call to this() in the Car constructor
B. insert a call to this() in the MeGo constructor
C. insert a call to super() in the MeGo constructor
D. insert a call to super(vin) in the MeGo constructor
E. change the wheelCount variable in Car to protected
F. change line 3 in the MeGo class to super.wheelCount = 3;

Answer: DE
Section: All

Explanation/Reference:

QUESTION 10
Click the Exhibit button.

1. import java.util.*;
2. public class TestSet{
3. enum Example {ONE, TWO, THREE }
4. public static void main(String[] args) {
5. Collection coll = new ArrayList();
6. coll.add(Example.THREE);
7. coll.add(Example.THREE);
8. coll.add(Example.THREE);
9. coll.add(Example.TWO);
10. coll.add(Example.TWO);
11. coll.add(Example.ONE);
12. Set set = new HashSet(coll);
13. }
14. }

Which statement is true about the set variable on line 12?

A. The set variable contains all six elements from the coll collection, and the order is guaranteed to be preserved.
B. The set variable contains only three elements from the coll collection, and the order is guaranteed to be preserved.
C. The set variable contains all six elements from the coll collection, but the order is NOT guaranteed to be preserved.
D. The set variable contains only three elements from the coll collection, but the order is NOT guaranteed to be preserved.
 
Answer: D
Section: All

Explanation/Reference:

QUESTION 11
Given:

public class Person {
     private String name, comment;
     private int age;
   
     public Person(String n, int a, String c) {
          name = n;
          age = a;
          comment = c;
     }
   
     public boolean equals(Object o) {
          if (!(o instanceof Person))
               return false;
          Person p = (Person) o;
          return age == p.age && name.equals(p.name);
     }
}

What is the appropriate definition of the hashCode method in class Person?

A. return super.hashCode();
B. return name.hashCode() + age * 7;
C. return name.hashCode() + comment.hashCode() / 2;
D. return name.hashCode() + comment.hashCode() / 2 - age * 3;

Answer: B
Section: All

Explanation/Reference:

QUESTION 12
Given:

public class Key {
     private long id1;
     private long id2;   
     // class Key methods
}
A programmer is developing a class Key, that will be used as a key in a standard java.util.HashMap.
Which two methods should be overridden to assure that Key works correctly as a key? (Choose two.)

A. public int hashCode()
B. public boolean equals(Key k)
C. public int compareTo(Object o)
D. public boolean equals(Object o)
E. public boolean compareTo(Key k)

Answer: AD
Section: All

Explanation/Reference:

QUESTION 13
Given:
import java.util.*;
public class Hancock {
          // insert code here Linea 5
          list.add("foo");
     }
}

Which two code fragments, inserted independently at line 5, will compile without warnings? (Choose two.)

A. public void addStrings(List list) {
B. public void addStrings(List<String> list) {
C. public void addStrings(List<? super String> list) {
D. public void addStrings(List<? extends String> list) { B,C

Answer: BC
Section: All

Explanation/Reference:

QUESTION 14
A programmer has an algorithm that requires a java.util.List that provides an efficient implementation of add (0, object), but does NOT need to support quick random access.
What supports these requirements?

A. java.util.Queue
B. java.util.ArrayList
C. java.util.LinearList
D. java.util.LinkedList

Answer: D
Section: All

Explanation/Reference:

QUESTION 15
Given a class whose instances, when found in a collection of objects, are sorted by using the compareTo() method, which two statements are true? (Choose two.)

A. The class implements java.lang.Comparable.
B. The class implements java.util.Comparator.
C. The interface used to implement sorting allows this class to define only one sort sequence.
D. The interface used to implement sorting allows this class to define many different sort sequences.

Answer: AC
Section: All

Explanation/Reference:

QUESTION 16
Given:
1. import java.util.*;
2.
3. public class Explorer3 {
4. public static void main(String[] args) {
5. TreeSet<Integer> s = new TreeSet<Integer>();
6. TreeSet<Integer> subs = new TreeSet<Integer>();
7. for (int i = 606; i < 613; i++)
8. if (i % 2 == 0)
9. s.add(i);
10. subs = (TreeSet) s.subSet(608, true, 611, true);
11. subs.add(629);
12. System.out.println(s + " " + subs);
13. }
14. }

What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. [608, 610, 612, 629] [608, 610]
D. [608, 610, 612, 629] [608, 610, 629]
E. [606, 608, 610, 612, 629] [608, 610]
F. [606, 608, 610, 612, 629] [608, 610, 629]

Answer: B
Section: All

Explanation/Reference:
 Exception in thread "main" java.lang.IllegalArgumentException: key out of
range
     at java.util.TreeMap$NavigableSubMap.put(TreeMap.java:1386)
     at java.util.TreeSet.add(TreeSet.java:238)
     at Explorer3.main(Explorer3.java:11)
   
QUESTION 17
Given:
1. import java.util.*;
2.
3. public class LetterASort {
4. public static void main(String[] args) {
5. ArrayList<String> strings = new ArrayList<String>();
6. strings.add("aAaA");
7. strings.add("AaA");
8. strings.add("aAa");
9. strings.add("AAaa");
10. Collections.sort(strings);
11. for (String s : strings) {
12. System.out.print(s + " ");
13. }
14. }
15. }

What is the result?

A. Compilation fails.
B. aAaA aAa AAaa AaA
C. AAaa AaA aAa aAaA
D. AaA AAaa aAaA aAa
E. aAa AaA aAaA AAaa
F. An exception is thrown at runtime.

Answer: C
Section: All

Explanation/Reference:

QUESTION 18
Given:
1. class A {
2. void foo() throws Exception {
3. throw new Exception();
4. }
5. }
6.
7. class SubB2 extends A {
8. void foo() {
9. System.out.println("B ");
10. }
11. }
12. class Tester {
13. public static void main(String[] args) {
14. A a = new SubB2();
15. a.foo();
16. }
17. }

What is the result?

A. B
B. B, followed by an Exception.
C. Compilation fails due to an error on line 9.
D. Compilation fails due to an error on line 15.
E. An Exception is thrown with no other output

Answer: D
Section: All

Explanation/Reference:
 Unhandled exception type Exception


QUESTION 19
Given a method that must ensure that its parameter is not null:

              11. public void someMethod(Object value) {
              12. // check for null value
              ...
              20. System.out.println(value.getClass());
              21. }
           
What, inserted at line 12, is the appropriate way to handle a null value?

A. assert value == null;
B. assert value != null, "value is null";
C. if (value == null) { throw new AssertionException("value is null"); }
D. if (value == null) { throw new IllegalArgumentException("value is null"); }

Answer: D
Section: All

Explanation/Reference:

QUESTION 20
Given:
1. public class Mule {
2. public static void main(String[] args) {
3. boolean assert = true;
4. if(assert) {
5. System.out.println("assert is true");
6. }
7. }
8. }

Which command-line invocations will compile?

A. javac Mule.java
B. javac -source 1.3 Mule.java
C. javac -source 1.4 Mule.java
D. javac -source 1.5 Mule.java

Answer: B
Section: All

Explanation/Reference:

QUESTION 21
Click the Exhibit button

1. public class A {
2. public void method1(){
3. B b = new B();
4. b.method2();
5. // more code here
6. }
7. }

1. public class B{
2. public void method2() {
3. C c = new C();
4. c.method3();
5. // more code here
6. }
7. }

1. public class C {
2. public void method3(){
3. // more code here
4. }
5. }

Given:
          try {
              A a = new A();
              a.method1();
          } catch (Exception e) {
              System.out.print("an error occurred");
          }
       
Which two statements are true if a NullPointerException is thrown on line 3 of class C? (Choose two.)

A. The application will crash.
B. The code on line 29 will be executed.
C. The code on line 5 of class A will execute.
D. The code on line 5 of class B will execute.
E. The exception will be propagated back to line 27.

Answer: BE
Section: All

Explanation/Reference:

QUESTION 22
Given:
1. public class Venus {
2. public static void main(String[] args) {
3. int[] x = { 1, 2, 3 };
4. int y[] = { 4, 5, 6 };
5. new Venus().go(x, y);
6. }
7.
8. void go(int[]... z) {
9. for (int[] a : z)
10. System.out.print(a[0]);
11. }
12. }

What is the result?

A. 1
B. 12
C. 14
D. 123
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: C
Section: All

Explanation/Reference:

QUESTION 23
Given:
1. public class Test {
2. public enum Dogs {collie, harrier, shepherd};
3. public static void main(String [] args) {
4. Dogs myDog = Dogs.shepherd;
5. switch (myDog) {
6. case collie:
7. System.out.print("collie ");
8. case default:
9. System.out.print("retriever ");
10. case harrier:
11. System.out.print("harrier ");
12. }
13. }
14. }
What is the result?

A. harrier
B. shepherd
C. retriever
D. Compilation fails.
E. retriever harrier
F. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:
   Test.java:10: illegal start of expression
                      case default:
                            ^
   Test.java:11: : expected
                                System.out.print("retriever ");
                                                                    ^
   2 errors
 
QUESTION 24
Given:
      static void test() {
          try {
              String x = null;
              System.out.print(x.toString() + " ");
          } finally {
              System.out.print("finally ");
          }
     }   
     public static void main(String[] args) {
          try {
              test();
          } catch (Exception ex) {
              System.out.print("exception ");
          }
     }   
   
What is the result?

A. null
B. finally
C. null finally
D. Compilation fails.
E. finally exception

Answer: E
Section: All

Explanation/Reference:

QUESTION 25
Given:
1. public class Breaker2 {
2. static String o = "";
3.
4. public static void main(String[] args) {
5. z: for (int x = 2; x < 7; x++) {
6. if (x == 3)
7. continue;
8. if (x == 5)
9. break z;
10. o = o + x;
11. }
12. System.out.println(o);
13. }
14. }
15.
What is the result?

A. 2
B. 24
C. 234
D. 246
E. 2346
F. Compilation fails.

Answer: B
Section: All

Explanation/Reference:

QUESTION 26
Given:
     public static void main(String[] args) {
          String str = "null";
          if (str == null) {
              System.out.println("null");
          } else (str.length() == 0) {
              System.out.println("zero");
           
          } else {
              System.out.println("some");
          }
     }
   
What is the result?

A. null
B. zero
C. some
D. Compilation fails.
E. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 27
Given:
1. import java.io.IOException;
2.
3. class A {
4.
5. public void process() {
6. System.out.print("A,");
7. }
8.
9. }
10.
11.
12. class B extends A {
13.
14. public void process() throws IOException {
15. super.process();
16. System.out.print("B,");
17. throw new IOException();
18. }
19.
20. public static void main(String[] args) {
21. try {
22. new B().process();
23. } catch (IOException e) {
24. System.out.println("Exception");
25. }
26. }
27. }

What is the result?

A. Exception
B. A,B,Exception
C. Compilation fails because of an error in line 20.
D. Compilation fails because of an error in line 14.
E. A NullPointerException is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:
Exception IOException is not compatible with throws clause in A.process()

QUESTION 28
Given:
1.
2.
3.
4.
5.
6.
7.
8.
9.
10.
11. public void genNumbers() {
12. ArrayList numbers = new ArrayList();
13. for (int i = 0; i < 10; i++) {
14. int value = i * ((int) Math.random());
15. Integer intObj = new Integer(value);
16. numbers.add(intObj);
17. }
18. System.out.println(numbers);
19. }


Which line of code marks the earliest point that an object referenced by intObj becomes a candidate for garbage collection?

A. Line 16
B. Line 17
C. Line 18
D. Line 19
E. The object is NOT a candidate for garbage collection.

Answer: D
Section: All

Explanation/Reference:

QUESTION 29
Click the Exhibit button.




Given the fully-qualified class names:

com.foo.bar.Dog
com.foo.bar.blatz.Book
com.bar.Car
com.bar.blatz.Sun

Which graph represents the correct directory structure for a JAR file from which those classes can be used
by the compiler and JVM?

A. Jar A
B. Jar B
C. Jar C
D. Jar D
E. Jar E

Answer: A
Section: All

Explanation/Reference:

QUESTION 30
Given:
1. public class GC {
2. private Object o;
3. private void doSomethingElse(Object obj) { o = obj; }
4. public void doSomething() {
5. Object o = new Object();
6. doSomethingElse(o);
7. o = new Object();
8. doSomethingElse(null);
9. o = null;
10. }
11. }

When the doSomething method is called, after which line does the Object created in line 5 become
available for garbage collection?

A. Line 5
B. Line 6
C. Line 7
D. Line 8
E. Line 9
F. Line 10

Answer: D
Section: All

Explanation/Reference:

QUESTION 31
Given:
public class Spock {
     public static void main(String[] args) {
          Long tail = 2000L;
          Long distance = 1999L;
          Long story = 1000L;
          if ((tail > distance) ^ ((story * 2) == tail))
              System.out.print("1");
          if ((distance + 1 != tail) ^ ((story * 2) == distance))
              System.out.print("2");
     }
}

What is the result?

A. 1
B. 2
C. 12
D. Compilation fails.
E. No output is produced.
F. An exception is thrown at runtime.

Answer: E
Section: All
