EXAM C

QUESTION 1
A company has a business application that provides its users with many different reports:
receivables reports, payables reports, revenue projects, and so on. The company has just purchased some new, state-of-the-art, wireless printers, and a programmer has been assigned the task of enhancing all of the reports to use not only the company's old printers, but the new wireless printers as well. When the programmer starts looking into the application, the programmer discovers that because of the design of the application, it is necessary to make changes to each report to support the new printers.Which two design concepts most likely explain this situation? (Choose two.)

A. Inheritance
B. Low cohesion
C. Tight coupling
D. High cohesion
E. Loose coupling
F. Object immutability

Answer: BC
Section: All

Explanation/Reference:

QUESTION 2
Given:
10. public class SuperCalc {
11. protected static int multiply(int a, int b) { return a * b;}
12. }
and:
20. public class SubCalc extends SuperCalc{
21. public static int multiply(int a, int b) {
22. int c = super.multiply(a, b);
23. return c;
24. }
25. }
and:
30. SubCalc sc = new SubCalc ();
31. System.out.println(sc.multiply(3,4));
32. System.out.println(SubCalc.multiply(2,2));

What is the result?

A. 12
B. The code runs with no output.
C. An exception is thrown at runtime.
D. Compilation fails because of an error in line 21.
E. Compilation fails because of an error in line 22.
F. Compilation fails because of an error in line 31.

Answer: E
Section: All

Explanation/Reference:

QUESTION 3
Given:
class Foo {
     public int a = 3;
     public void addFive() { a += 5; System.out.print("f "); }
}
class Bar extends Foo {
     public int a = 8;
     public void addFive() { this.a += 5; System.out.print("b " ); }
}
Invoked with:

Foo f = new Bar();
f.addFive();
System.out.println(f.a);

What is the result?

A. b3
B. b8
C. b 13
D. f3
E. f8
F. f 13
G. Compilation fails.
H. An exception is thrown at runtime.

Answer: A
Section: All

Explanation/Reference:

QUESTION 4
A company that makes Computer Assisted Design (CAD) software has, within its application, some utility classes that are used to perform 3D rendering tasks. The company's chief scientist has just improved the performance of one of the utility classes' key rendering algorithms, and has assigned a programmer to replace the old algorithm with the new algorithm. When the programmer begins researching the utility classes, she is happy to discover that the algorithm to be replaced exists in only one class. The programmer reviews that class's API, and replaces the old algorithm with the new algorithm, being careful that her changes adhere strictly to the class's API. Once testing has begun, the programmer discovers that other classes that use the class she changed are no longer working properly. What design flaw is most likely the cause of these new bugs?

A. Inheritance
B. Tight coupling
C. Low cohesion
D. High cohesion
E. Loose coupling
F. Object immutability

Answer: B
Section: All

Explanation/Reference:

QUESTION 5
Given:
1. class ClassA {
2. public int numberOfInstances;
3. protected ClassA(int numberOfInstances) {
4. this.numberOfInstances = numberOfInstances;
5. }
6. }
7. public class ExtendedA extends ClassA {
8. private ExtendedA(int numberOfInstances) {
9. super(numberOfInstances);
10. }
11. public static void main(String[] args) {
12. ExtendedA ext = new ExtendedA(420);
13. System.out.print(ext.numberOfInstances);
14. }
15. }
Which statement is true?

A. 420 is the output.
B. An exception is thrown at runtime.
C. All constructors must be declared public.
D. Constructors CANNOT use the private modifier.
E. Constructors CANNOT use the protected modifier.

Answer: A
Section: All

Explanation/Reference:

QUESTION 6
Given:
class ClassA {}
class ClassB extends ClassA {}
class ClassC extends ClassA {}
and:
ClassA p0 = new ClassA();
ClassB p1 = new ClassB();
ClassC p2 = new ClassC();
ClassA p3 = new ClassB();
ClassA p4 = new ClassC();

Which three are valid? (Choose three.)

A. p0 = p1;
B. p1 = p2;
C. p2 = p4;
D. p2 = (ClassC)p1;
E. p1 = (ClassB)p3;
F. p2 = (ClassC)p4;

Answer: AEF
Section: All

Explanation/Reference:

QUESTION 7
Given:
class Thingy { Meter m = new Meter(); }
class Component { void go() { System.out.print("c"); } }
class Meter extends Component { void go() { System.out.print("m"); } } 8.
class DeluxeThingy extends Thingy {
     public static void main(String[] args) {
          DeluxeThingy dt = new DeluxeThingy();
          dt.m.go();
          Thingy t = new DeluxeThingy();
          t.m.go();
     }
}
Which two are true? (Choose two.)

A. The output is mm.
B. The output is mc.
C. Component is-a Meter.
D. Component has-a Meter.
E. DeluxeThingy is-a Component.
F. DeluxeThingy has-a Component.

Answer: AF
Section: All

Explanation/Reference:

QUESTION 8
Given:
10. interface Jumper { public void jump(); }
...
20. class Animal {}
...
30. class Dog extends Animal {
31. Tail tail;
32. }
...
40. class Beagle extends Dog implements Jumper{
41. public void jump() {}
42. }
...
50. class Cat implements Jumper{
51. public void jump() {}
52. }
Which three are true? (Choose three.)

A. Cat is-a Animal
B. Cat is-a Jumper
C. Dog is-a Animal
D. Dog is-a Jumper
E. Cat has-a Animal
F. Beagle has-a Tail
G. Beagle has-a Jumper

Answer: BCF
Section: All

Explanation/Reference:

QUESTION 9
Given:
1. import java.util.*;
2. public class WrappedString {
3. private String s;
4. public WrappedString(String s) { this.s = s; }
5. public static void main(String[] args) {
6. HashSet<Object> hs = new HashSet<Object>();
7. WrappedString ws1 = new WrappedString("aardvark");
8. WrappedString ws2 = new WrappedString("aardvark");
9. String s1 = new String("aardvark");
10. String s2 = new String("aardvark");
11. hs.add(ws1); hs.add(ws2); hs.add(s1); hs.add(s2);
12. System.out.println(hs.size()); } }

What is the result?

A. 0
B. 1
C. 2
D. 3
E. 4
F. Compilation fails.
G. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 10
Given:
11. //insert code here
     private N min, max;
     public N getMin() { return min; }
     public N getMax() { return max; }
     public void add(N added) {
          if (min == null || added.doubleValue() < min.doubleValue())
              min = added;
          if (max == null || added.doubleValue() > max.doubleValue())
              max = added;
     }
}
Which two, inserted at line 11, will allow the code to compile? (Choose two.)

A. public class MinMax<?> {
B. public class MinMax<? extends Number> {
C. public class MinMax<N extends Object> {
D. public class MinMax<N extends Number> {
E. public class MinMax<? extends Object> {
F. public class MinMax<N extends Integer> {

Answer: DF
Section: All

Explanation/Reference:

QUESTION 11
Given:
3. import java.util.*;
4. public class G1 {
5. public void takeList(List<? extends String> list) {
6. // insert code here
7. }
8. }
Which three code fragments, inserted independently at line 6, will compile? (Choose three.)

A. list.add("foo");
B. Object o = list;
C. String s = list.get(0);
D. list = new ArrayList<String>();
E. list = new ArrayList<Object>();

Answer: BCD
Section: All

Explanation/Reference:

QUESTION 12
Given that the elements of a PriorityQueue are ordered according to natural ordering, and:
import java.util.*;
public class GetInLine {
     public static void main(String[] args) {
          PriorityQueue<String> pq = new PriorityQueue<String>();
          pq.add("banana");
          pq.add("pear");
          pq.add("apple");
          System.out.println(pq.poll() + " " + pq.peek());
     }
}
What is the result?

A. apple pear
B. banana pear
C. apple apple
D. apple banana
E. banana banana

Answer: D
Section: All

Explanation/Reference:

QUESTION 13
Given:
enum Example { ONE, TWO, THREE }
Which statement is true?

A. The expressions (ONE == ONE) and ONE.equals(ONE) are both guaranteed to be true.
B. The expression (ONE < TWO) is guaranteed to be true and ONE.compareTo(TWO) is guaranteed to be  less than one.
C. The Example values cannot be used in a raw java.util.HashMap; instead, the programmer must use a  java.util.EnumMap.
D. The Example values can be used in a java.util.SortedSet, but the set will NOT be sorted because    enumerated types do NOT implement java.lang.Comparable.
 
Answer: A
Section: All

Explanation/Reference:

QUESTION 14
Given:
import java.util.*;
public class Mapit {
     public static void main(String[] args) {
          Set<Integer> set = new HashSet<Integer>();
          Integer i1 = 45;
          Integer i2 = 46;
          set.add(i1);
          set.add(i1);
          set.add(i2); System.out.print(set.size() + " ");
          set.remove(i1); System.out.print(set.size() + " ");
          i2 = 47;
          set.remove(i2); System.out.print(set.size() + " ");
     }
}
What is the result?

A. 210
B. 211
C. 321
D. 322
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: B
Section: All

Explanation/Reference:

QUESTION 15
Given:
import java.util.*;
public class Explorer1 {
     public static void main(String[] args) {
          TreeSet<Integer> s = new TreeSet<Integer>();
          TreeSet<Integer> subs = new TreeSet<Integer>();
          for(int i = 606; i < 613; i++)
               if(i%2 == 0) s.add(i);
          subs = (TreeSet)s.subSet(608, true, 611, true);
          s.add(609);
          System.out.println(s + " " + subs);
     }
}

What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. [608, 609, 610, 612] [608, 610]
D. [608, 609, 610, 612] [608, 609, 610]
E. [606, 608, 609, 610, 612] [608, 610]
F. [606, 608, 609, 610, 612] [608, 609, 610]

Answer: F
Section: All

Explanation/Reference:

QUESTION 16
Given:
import java.util.*;
public class Quest {
     public static void main(String[] args) {
          String[] colors = {"blue", "red", "green", "yellow", "orange"};
          Arrays.sort(colors);
          int s2 = Arrays.binarySearch(colors, "orange");
          int s3 = Arrays.binarySearch(colors, "violet");
          System.out.println(s2 + " " + s3);
     }
}
What is the result?

A. 2 -1
B. 2 -4
C. 2 -5
D. 3 -1
E. 3 -4
F. 3 -5
G. Compilation fails.
H. An exception is thrown at runtime.

Answer: C
Section: All

Explanation/Reference:

QUESTION 17
Given:
HashMap props = new HashMap();
props.put("key45", "some value");
props.put("key12", "some other value");
props.put("key39", "yet another value");
Set s = props.keySet();
//insert code here
What, inserted at line 39, will sort the keys in the props HashMap?

A. Arrays.sort(s);
B. s = new TreeSet(s);
C. Collections.sort(s);
D. s = new SortedSet(s);

Answer: B
Section: All

Explanation/Reference:

QUESTION 18
Which two statements are true? (Choose two.)

A. It is possible to synchronize static methods.
B. When a thread has yielded as a result of yield(), it releases its locks.
C. When a thread is sleeping as a result of sleep(), it releases its locks.
D. The Object.wait() method can be invoked only from a synchronized context.
E. The Thread.sleep() method can be invoked only from a synchronized context.
F. When the thread scheduler receives a notify() request, and notifies a thread, that thread immediately releases its lock.
 
Answer: AD
Section: All

Explanation/Reference:

QUESTION 19
Given:
public class TestOne implements Runnable {
     public static void main (String[] args) throws Exception {
          Thread t = new Thread(new TestOne());
          t.start();
          System.out.print("Started");
          t.join();
          System.out.print("Complete");
     }
     public void run() {
          for (int i = 0; i < 4; i++) {
              System.out.print(i);
          }
     }
}
What can be a result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. The code executes and prints "StartedComplete".
D. The code executes and prints "StartedComplete0123".
E. The code executes and prints "Started0123Complete".

Answer: E
Section: All

Explanation/Reference:

QUESTION 20
Which three will compile and run without exception? (Choose three.)

A. private synchronized Object o;
B. void go() {
   synchronized() { /* code here */ }
C. public synchronized void go() { /* code here */ }
D. private synchronized(this) void go() { /* code here */ }
E. void go() {
   synchronized(Object.class) { /* code here */ }
F. void go() {
   Object o = new Object();
   synchronized(o) { /* code here */ }
 
Answer: CEF
Section: All

Explanation/Reference:

QUESTION 21
Given:
1. public class TestFive {
2. private int x;
3. public void foo() {
4. int current = x;
5. x = current + 1;
6. }
7. public void go() {
8. for(int i = 0; i < 5; i++) {
9. new Thread() {
10. public void run() {
11. foo();
12. System.out.print(x + ", ");
13. } }.start();
14. } }
15. }

Which two changes, taken together, would guarantee the output: 1, 2, 3, 4, 5, ? (Choose two.)

A. move the line 12 print statement into the foo() method
B. change line 7 to public synchronized void go() {
C. change the variable declaration on line 2 to private volatile int x;
D. wrap the code inside the foo() method with a synchronized( this ) block
E. wrap the for loop code inside the go() method with a synchronized block synchronized(this) { // for loop
   code here }
 
Answer: AD
Section: All

Explanation/Reference:

QUESTION 22
Given that t1 is a reference to a live thread, which is true?

A. The Thread.sleep() method can take t1 as an argument.
B. The Object.notify() method can take t1 as an argument.
C. The Thread.yield() method can take t1 as an argument.
D. The Thread.setPriority() method can take t1 as an argument.
E. The Object.notify() method arbitrarily chooses which thread to notify.

Answer: E
Section: All

Explanation/Reference:

QUESTION 23
Given:
Runnable r = new Runnable() {
     public void run() {
          System.out.print("Cat");
     }
};
Thread t = new Thread(r) {
     public void run() {
          System.out.print("Dog");
     }
};
t.start();
What is the result?

A. Cat
B. Dog
C. Compilation fails.
D. The code runs with no output.
E. An exception is thrown at runtime.

Answer: B
Section: All

Explanation/Reference:

QUESTION 24
Given:
1. public class Threads5 {
2. public static void main (String[] args) {
3. new Thread(new Runnable() {
4. public void run() {
5. System.out.print("bar");
6. }}).start();
7. }
8. }

What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. The code executes normally and prints "bar".
D. The code executes normally, but nothing prints.

Answer: C
Section: All

Explanation/Reference:

QUESTION 25
Given:
class One {
     void foo() { }
}
class Two extends One {
14. // insert method here
}

Which three methods, inserted individually at line 14, will correctly complete class Two? (Choose three.)

A. int foo() { /* more code here */ }
B. void foo() { /* more code here */ }
C. public void foo() { /* more code here */ }
D. private void foo() { /* more code here */ }
E. protected void foo() { /* more code here */ }

Answer: BCE
Section: All

Explanation/Reference:

QUESTION 26
Given:
abstract public class Employee {
     protected abstract double getSalesAmount();
     public double getCommision() {
          return getSalesAmount() * 0.15;
     }
}
class Sales extends Employee {
17. // insert method here
}

Which two methods, inserted independently at line 17, correctly complete the Sales class? (Choose two.)

A. double getSalesAmount() { return 1230.45; }
B. public double getSalesAmount() { return 1230.45; }
C. private double getSalesAmount() { return 1230.45; }
D. protected double getSalesAmount() { return 1230.45; }

Answer: BD
Section: All

Explanation/Reference:

QUESTION 27
Given:
1. class X {
2. X() { System.out.print(1); }
3. X(int x) {
4. this(); System.out.print(2);
5. }
6. }
7. public class Y extends X {
8. Y() { super(6); System.out.print(3); }
9. Y(int y) {
10. this(); System.out.println(4);
11. }
12. public static void main(String[] a) { new Y(5); }
13. }
What is the result?

A. 13
B. 134
C. 1234
D. 2134
E. 2143
F. 4321

Answer: C
Section: All

Explanation/Reference:

QUESTION 28
Given:
package com.sun.scjp;
public class Geodetics {
     public static final double DIAMETER = 12756.32; // kilometers
}
Which two correctly access the DIAMETER member of the Geodetics class? (Choose two.)

A. import com.sun.scjp.Geodetics;
   public class TerraCarta {
        public double halfway()
        { return Geodetics.DIAMETER/2.0; }
B. import static com.sun.scjp.Geodetics;
   public class TerraCarta{
   public double halfway() { return DIAMETER/2.0; } }
C. import static com.sun.scjp.Geodetics.*;
   public class TerraCarta {
        public double halfway() { return DIAMETER/2.0; } }
D. package com.sun.scjp;
   public class TerraCarta {
        public double halfway() { return DIAMETER/2.0; } }
     
Answer: AC
Section: All

Explanation/Reference:

QUESTION 29
Given:
1. public class A {
2. public void doit() {
3. }
4. public String doit() {
5. return "a";
6. }
7. public double doit(int x) {
8. return 1.0;
9. }
10. }
What is the result?

A. An exception is thrown at runtime.
B. Compilation fails because of an error in line 7.
C. Compilation fails because of an error in line 4.
D. Compilation succeeds and no runtime errors with class A occur.

Answer: C
Section: All

Explanation/Reference:

QUESTION 30
Given:
35. String #name = "Jane Doe";
36. int $age = 24;
37. Double _height = 123.5;
38. double ~temp = 37.5;

Which two statements are true? (Choose two.)

A. Line 35 will not compile.
B. Line 36 will not compile.
C. Line 37 will not compile.
D. Line 38 will not compile.

Answer: AD
Section: All

Explanation/Reference:

QUESTION 31
Click the Exhibit button.
Given the fully-qualified class names:

   com.foo.bar.Dog
   com.foo.bar.blatz.Book
   com.bar.Car
   com.bar.blatz.Sun
 
Which graph represents the correct directory structure for a JAR file from which those classes can be used by the compiler and JVM?





A. Jar A
B. Jar B
C. Jar C
D. Jar D
E. Jar E

Answer: A
Section: All

Explanation/Reference:

QUESTION 32
Click the Exhibit button.
Given: ClassA a = new ClassA();
a.methodA();



What is the result?

A. Compilation fails.
B. ClassC is displayed.
C. The code runs with no output.
D. An exception is thrown at runtime.

Answer: D
Section: All
