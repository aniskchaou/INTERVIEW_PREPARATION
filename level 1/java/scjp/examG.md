EXAM G

QUESTION 1
Given that the current directory is empty, and that the user has read and write privileges to the current directory, and the following:

1. import java.io.*;
2. public class Maker {
3. public static void main(String[] args) {
4. File dir = new File("dir");
5. File f = new File(dir, "f");
6. }
7. }

Which statement is true?

A. Compilation fails.
B. Nothing is added to the file system.
C. Only a new file is created on the file system.
D. Only a new directory is created on the file system.
E. Both a new file and a new directory are created on the file system.

Answer: B
Section: All

Explanation/Reference:

QUESTION 2
Given:

 NumberFormat nf = NumberFormat.getInstance();
 nf.setMaximumFractionDigits(4);
 nf.setMinimumFractionDigits(2);
 String a = nf.format(3.1415926);
 String b = nf.format(2);

Which two statements are true about the result if the default locale is Locale.US? (Choose two.)

A. The value of b is 2.
B. The value of a is 3.14.
C. The value of b is 2.00.
D. The value of a is 3.141.
E. The value of a is 3.1415.
F. The value of a is 3.1416.
G. The value of b is 2.0000.

Answer: CF
Section: All

Explanation/Reference:

QUESTION 3
Which three statements concerning the use of the java.io.Serializable interface are true? (Choose three.)

A. Objects from classes that use aggregation cannot be serialized.
B. An object serialized on one JVM can be successfully deserialized on a different JVM.
C. The values in fields with the volatile modifier will NOT survive serialization and deserialization.
D. The values in fields with the transient modifier will NOT survive serialization and deserialization.
E. It is legal to serialize an object of a type that has a supertype that does NOT implement java.io.
   Serializable.
 
Answer: BDE
Section: All

Explanation/Reference:

QUESTION 4
Given:
12. String csv = "Sue,5,true,3";
13. Scanner scanner = new Scanner( csv );
14. scanner.useDelimiter(",");
15. int age = scanner.nextInt();

What is the result?

A. Compilation fails.
B. After line 15, the value of age is 5.
C. After line 15, the value of age is 3.
D. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 5
Given that c is a reference to a valid java.io.Console object, which two code fragments read a line of text from the console? (Choose two.)

A. String s = c.readLine();
B. char[] c = c.readLine();
C. String s = c.readConsole();
D. char[] c = c.readConsole();
E. String s = c.readLine("%s", "name ");
F. char[] c = c.readLine("%s", "name ");

Answer: AE
Section: All

Explanation/Reference:

QUESTION 6
Given:

11. String test = "a1b2c3";
12. String[] tokens = test.split("\\d");
13. for(String s: tokens) System.out.print(s + " ");

What is the result?

A. abc
B. 123
C. a1b2c3
D. a1 b2 c3
E. Compilation fails.
F. The code runs with no output.
G. An exception is thrown at runtime.

Answer: A
Section: All

Explanation/Reference:

QUESTION 7
Given:

33. Date d = new Date(0);
34. String ds = "December 15, 2004";
35. // insert code here
36. try {
37. d = df.parse(ds);
38. }
39. catch(ParseException e) {
40. System.out.println("Unable to parse " + ds);
41. }
42. // insert code here too

What creates the appropriate DateFormat object and adds a day to the Date object?

A. 35. DateFormat df = DateFormat.getDateFormat();
     42. d.setTime( (60 * 60 * 24) + d.getTime());
B. 35. DateFormat df = DateFormat.getDateInstance();
     42. d.setTime( (1000 * 60 * 60 * 24) + d.getTime());
C. 35. DateFormat df = DateFormat.getDateFormat();
     42. d.setLocalTime( (1000*60*60*24) + d.getLocalTime());
D. 35. DateFormat df = DateFormat.getDateInstance();
     42. d.setLocalTime( (60 * 60 * 24) + d.getLocalTime());
 
Answer: B
Section: All

Explanation/Reference:

QUESTION 8
Given:
1. public class KungFu {
2. public static void main(String[] args) {
3. Integer x = 400;
4. Integer y = x;
5. x++;
6. StringBuilder sb1 = new StringBuilder("123");
7. StringBuilder sb2 = sb1;
8. sb1.append("5");
9. System.out.println((x == y) + " " + (sb1 == sb2));
10. }
11. }
What is the result?

A. true true
B. false true
C. true false
D. false false
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: B
Section: All

Explanation/Reference:

QUESTION 9
Given:
class Converter {
     public static void main(String[] args) {
          Integer i = args[0];
          int j = 12;
          System.out.println("It is " + (j == i) + " that j==i.");
     }
}

What is the result when the programmer attempts to compile the code and run it with the command java Converter 12?

A. It is true that j==i.
B. It is false that j==i.
C. An exception is thrown at runtime.
D. Compilation fails because of an error in line 13.

Answer: D
Section: All

Explanation/Reference:
 Integer i = args[0]; Type mismatch: cannot convert from String to Integer


QUESTION 10

Given:
class Foo {
     static void alpha() {
          /* more code here */
     }
   
     void beta() {
          /* more code here */
     }
}
Which two statements are true? (Choose two.)

A. Foo.beta() is a valid invocation of beta().
B. Foo.alpha() is a valid invocation of alpha().
C. Method beta() can directly call method alpha().
D. Method alpha() can directly call method beta().

Answer: BC
Section: All

Explanation/Reference:

QUESTION 11
Click the Exhibit button.
1. public class A {
2. public String doit(int x, int y){
3. return "a";
4. }
5.
6. public String doit(int... vals){
7. return "b";
8. }
9. }

Given:
      25. A a = new A();
      26. System.out.println(a.doit(4, 5));
   
What is the result?

A. Line 26 prints "a" to System.out.
B. Line 26 prints "b" to System.out.
C. An exception is thrown at line 26 at runtime.
D. Compilation of class A will fail due to an error in line 6.

Answer: A
Section: All

Explanation/Reference:

QUESTION 12
Which two code fragments correctly create and initialize a static array of int elements? (Choose two.)

A. static final int[] a = { 100,200 };
B. static final int[] a;
     static { a=new int[2]; a[0]=100; a[1]=200; }
C. static final int[] a = new int[2]{ 100,200 };
D. static final int[] a;
     static void init() { a = new int[3]; a[0]=100; a[1]=200; }
 
Answer: AB
Section: All

Explanation/Reference:

QUESTION 13
Given:
1. public class Plant {
2. private String name;
3.
4. public Plant(String name) {
5. this.name = name;
6. }
7.
8. public String getName() {
9. return name;
10. }
11. }

1. public class Tree extends Plant {
2. public void growFruit() {
3. }
4.
5. public void dropLeaves() {
6. }
7. }

Which statement is true?

A. The code will compile without changes.
B. The code will compile if public Tree() { Plant(); } is added to the Tree class.
C. The code will compile if public Plant() { Tree(); } is added to the Plant class.
D. The code will compile if public Plant() { this("fern"); } is added to the Plant class.
E. The code will compile if public Plant() { Plant("fern"); } is added to the Plant class.

Answer: D
Section: All

Explanation/Reference:

QUESTION 14
Click the Exhibit button.

1. public class GoTest {
2. public static void main(String[] args) {
3. Sente a = new Sente(); a.go();
4. Goban b = new Goban(); b.go();
5. Stone c = new Stone(); c.go();
6. }
7. }
8.
9. class Sente implements Go {
10. public void go(){
11. System.out.println("go in Sente");
12. }
13. }
14.
15. class Goban extends Sente {
16. public void go(){
17. System.out.println("go in Goban");
18. }
19.
20. }
21. class Stone extends Goban implements Go{
22. }
23.
24. interface Go { public void go(); }

What is the result?

A. go in Goban go in Sente go in Sente
B. go in Sente go in Sente go in Goban
C. go in Sente go in Goban go in Goban
D. go in Goban go in Goban go in Sente
E. Compilation fails because of an error in line 17.

Answer: C
Section: All

Explanation/Reference:

QUESTION 15
Which two classes correctly implement both the java.lang.Runnable and the java.lang.
Cloneable interfaces? (Choose two.)

A. public class Session implements Runnable, Cloneable {
        public void run();    
        public Object clone();
   }
B. public class Session extends Runnable, Cloneable {
        public void run() { /* do something */ }
        public Object clone() { /* make a copy */ }
   }
C. public class Session implements Runnable, Cloneable {
        public void run() { /* do something */ }
        public Object clone() { /* make a copy */ }
   }
D. public abstract class Session implements Runnable, Cloneable {
        public void run() { /* do something */ }
        public Object clone() { /*make a copy */ }
   }
E. public class Session implements Runnable, implements Cloneable {
        public void run() { /* do something */ }
        public Object clone() { /* make a copy */ }
   }
 
Answer: CD
Section: All

Explanation/Reference:

QUESTION 16
Given:

public interface A111 {
     String s = "yo";
     public void method1();
}
interface B {
}
interface C extends A111, B {
     public void method1();   
     public void method1(int x);
}

What is the result?

A. Compilation succeeds.
B. Compilation fails due to multiple errors.
C. Compilation fails due to an error only on line 20.
D. Compilation fails due to an error only on line 21.
E. Compilation fails due to an error only on line 22.
F. Compilation fails due to an error only on line 12.

Answer: A
Section: All

Explanation/Reference:

QUESTION 17
Click the Exhibit button.

1.
2.
3.
4.
5.
6.
7.
8.
9.
10. interface Foo{
11. int bar();
12. }
13.
14. public class Beta {
15.
16. class A implements Foo {
17. public int bar(){ return 1; }
18. }
19.
20. public int fubar(Foo foo){ return foo.bar(); }
21.
22. public void testFoo(){
23.
24. class A implements Foo{
25. public int bar(){return 2;}
26. }
27.
28. System.out.println(fubar(new A()));
29. }
30.
31. public static void main(String[] args) {
32. new Beta().testFoo();
33. }
34. }

Which three statements are true? (Choose three.)

A. Compilation fails.
B. The code compiles and the output is 2.
C. If lines 16, 17 and 18 were removed, compilation would fail.
D. If lines 24, 25 and 26 were removed, compilation would fail.
E. If lines 16, 17 and 18 were removed, the code would compile and the output would be 2.
F. If lines 24, 25 and 26 were removed, the code would compile and the output would be 1.

Answer: BEF
Section: All

Explanation/Reference:

QUESTION 18
Given:
class Alpha {
     public void foo() { System.out.print("Afoo "); }
}
public class Beta extends Alpha {
     public void foo() { System.out.print("Bfoo "); }
     public static void main(String[] args) {
          Alpha a = new Beta();
          Beta b = (Beta)a;
          a.foo();
          b.foo();
     }
}
What is the result?

A. Afoo Afoo
B. Afoo Bfoo
C. Bfoo Afoo
D. Bfoo Bfoo
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 19
Given:
1. public class TestOne {
2. public static void main (String[] args) throws Exception {
3. Thread.sleep(3000);
4. System.out.println("sleep");
5. }
6. }
What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. The code executes normally and prints "sleep".
D. The code executes normally, but nothing is printed.

Answer: C
Section: All

Explanation/Reference:

QUESTION 20
Given:
1. public class Threads3 implements Runnable {
2. public void run() {
3. System.out.print("running");
4. }
5. public static void main(String[] args) {
6. Thread t = new Thread(new Threads3());
7. t.run();
8. t.run();
9. t.start();
10. }
11. }
What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. The code executes and prints "running".
D. The code executes and prints "runningrunning".
E. The code executes and prints "runningrunningrunning".

Answer: E
Section: All

Explanation/Reference:

QUESTION 21
Given:

public class NamedCounter {
     private final String name;
     private int count;
   
     public NamedCounter(String name) {
          this.name = name;
     }
   
     public String getName() {
          return name;
     }
   
     public void increment() {
          count++;
     }
   
     public int getCount() {
          return count;
     }
   
     public void reset() {
          count = 0;
     }
}

Which three changes should be made to adapt this class to be used safely by multiple threads? (Choose three.)

A. declare reset() using the synchronized keyword
B. declare getName() using the synchronized keyword
C. declare getCount() using the synchronized keyword
D. declare the constructor using the synchronized keyword
E. declare increment() using the synchronized keyword

Answer: ACE
Section: All

Explanation/Reference:

QUESTION 22
Given that Triangle implements Runnable, and:

     void go() throws Exception {
          Thread t = new Thread(new Triangle());
          t.start();
          for(int x = 1; x < 100000; x++) {
              //insert code here Linea 35
               if(x%100 == 0) System.out.print("g");
          }
     }
      public void run() {
          try {
               for(int x = 1; x < 100000; x++) {
                   // insert the same code here Linea 41
                    if(x%100 == 0) System.out.print("t");
              }
          } catch (Exception e) {
       
          }
     }
   
Which two statements, inserted independently at both lines 35 and 41, tend to allow both threads to
temporarily pause and allow the other thread to execute? (Choose two.)

A. Thread.wait();
B. Thread.join();
C. Thread.yield();
D. Thread.sleep(1);
E. Thread.notify();

Answer: CD
Section: All

Explanation/Reference:

QUESTION 23
Given:

1. public class TestSeven extends Thread {
2. private static int x;
3. public synchronized void doThings() {
4. int current = x;
5. current++;
6. x = current;
7. }
8. public void run() {
9. doThings();
10. }
11. }

Which statement is true?

A. Compilation fails.
B. An exception is thrown at runtime.
C. Synchronizing the run() method would make the class thread-safe.
D. The data in variable "x" are protected from concurrent access problems.
E. Declaring the doThings() method as static would make the class thread-safe.
F. Wrapping the statements within doThings() in a synchronized(new Object()) { } block would make the class thread-safe.
 
Answer: E
Section: All

Explanation/Reference:

QUESTION 24
Given:
public class Yikes {
     public static void go(Long n) {
          System.out.print("Long ");
     }   
     public static void go(Short n) {
          System.out.print("Short ");
     }   
     public static void go(int n) {
          System.out.print("int ");
     }   
     public static void main(String[] args) {
          short y = 6;
          long z = 7;
          go(y);
          go(z);
     }
}
What is the result?

A. int Long
B. Short Long
C. Compilation fails.
D. An exception is thrown at runtime.

Answer: A
Section: All

Explanation/Reference:

QUESTION 25
Given:

     12. Date date = new Date();
     13. df.setLocale(Locale.ITALY);
     14. String s = df.format(date);
   
The variable df is an object of type DateFormat that has been initialized in line 11.
What is the result if this code is run on December 14, 2000?

A. The value of s is 14-dic-2000.
B. The value of s is Dec 14, 2000.
C. An exception is thrown at runtime.
D. Compilation fails because of an error in line 13.

Answer: D
Section: All

Explanation/Reference:
 The method setLocale(Locale) is undefined for the type DateFormat

QUESTION 26
Which two scenarios are NOT safe to replace a StringBuffer object with a StringBuilder object? (Choose two.)

A. When using versions of Java technology earlier than 5.0.
B. When sharing a StringBuffer among multiple threads.
C. When using the java.io class StringBufferInputStream.
D. When you plan to reuse the StringBuffer to build more than one string.

Answer: AB
Section: All

Explanation/Reference:

QUESTION 27
Given that c is a reference to a valid java.io.Console object, and:

          11. String pw = c.readPassword("%s", "pw: ");
          12. System.out.println("got " + pw);
          13. String name = c.readLine("%s", "name: ");
          14. System.out.println(" got ", name);

If the user types fido when prompted for a password, and then responds bob when prompted for a name, what is the result?

A. pw: got fido name: bob got bob
B. pw: fido got fido name: bob got bob
C. pw: got fido name: bob got bob
D. pw: fido got fido name: bob got bob
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: E
Section: All

Explanation/Reference:
The method println(String) in the type PrintStream is not applicable for the arguments
(String, String)

QUESTION 28
Given:
          11. String test = "This is a test";
          12. String[] tokens = test.split("\s");
          13. System.out.println(tokens.length);
       
What is the result?

A. 0
B. 1
C. 4
D. Compilation fails.
E. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:
Invalid escape sequence (valid ones are \b \t \n \f \r \" \' \\ )

QUESTION 29
Given:
import java.io.*;
class Animal {
     Animal() {
          System.out.print("a");
     }
}
class Dog extends Animal implements Serializable {
     Dog() {
          System.out.print("d");
     }
}
public class Beagle extends Dog {
}

If an instance of class Beagle is created, then Serialized, then deSerialized, what is the result?

A. ad
B. ada
C. add
D. adad
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: B
Section: All

Explanation/Reference:

QUESTION 30
Given:
          11. double input = 314159.26;
          12. NumberFormat nf = NumberFormat.getInstance(Locale.ITALIAN);
          13. String b;
          14. //insert code here
       
Which code, inserted at line 14, sets the value of b to 314.159,26?

A. b = nf.parse( input );
B. b = nf.format( input );
C. b = nf.equals( input );
D. b = nf.parseObject( input );

Answer: B
Section: All

Explanation/Reference:

QUESTION 31
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


QUESTION 32
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
