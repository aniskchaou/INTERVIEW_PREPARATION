EXAM E

QUESTION 1
Given:

import java.util.Date;
import java.text.DateFormat;
DateFormat df;
Date date = new Date();
//insert code here Linea 23
String s = df.format(date);

Which code fragment, inserted at line 23, allows the code to compile?

A. df = new DateFormat();
B. df = Date.getFormat();
C. df = date.getFormat();
D. df = DateFormat.getFormat();
E. df = DateFormat.getInstance();

Answer: E
Section: All

Explanation/Reference:

QUESTION 2
Given:

1. public class BuildStuff {
2. public static void main(String[] args) {
3. Boolean test = new Boolean(true);
4. Integer x = 343;
5. Integer y = new BuildStuff().go(test, x);
6. System.out.println(y);
7. }
8. int go(Boolean b, int i) {
9. if(b) return (i/7);
10. return (i/49);
11. }
12. }

What is the result?

A. 7
B. 49
C. 343
D. Compilation fails.
E. An exception is thrown at runtime.

Answer: B
Section: All

Explanation/Reference:

QUESTION 3
Given:

import java.io.*;
public class Forest implements Serializable {
     private Tree tree = new Tree();
     public static void main(String [] args) {
          Forest f = new Forest();
          try {
       
              FileOutputStream fs = new FileOutputStream("Forest.ser");
              ObjectOutputStream os = new ObjectOutputStream(fs);
              os.writeObject(f); os.close();
          } catch (Exception ex) { ex.printStackTrace(); }
     }
}
class Tree { }

What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. An instance of Forest is serialized.
D. An instance of Forest and an instance of Tree are both serialized.

Answer: B
Section: All

Explanation/Reference:

QUESTION 4
Which capability exists only in java.io.FileWriter?

A. Closing an open stream.
B. Flushing an open stream.
C. Writing to an open stream.
D. Writing a line separator to an open stream.

Answer: D
Section: All

Explanation/Reference:

QUESTION 5
Given:

1. import java.io.*;
2.
3.
4.
5.
6. public class Talk {
7. public static void main(String[] args) {
8. Console c = new Console();
9. String pw;
10. System.out.print("password: ");
11. pw = c.readLine();
12. System.out.println("got " + pw);
13. }
14. }

If the user types the password aiko when prompted, what is the result?

A. password:  got
B. password:  got aiko
C. password: aiko got aiko
D. An exception is thrown at runtime.
E. Compilation fails due to an error on line 8.

Answer: E
Section: All

Explanation/Reference:

QUESTION 6
Given:

1. public class LineUp {
2. public static void main(String[] args) {
3. double d = 12.345;
4. // insert code here
5. }
6. }

Which code fragment, inserted at line 4, produces the output | 12.345|?

A. System.out.printf("|%7d| \n", d);
B. System.out.printf("|%7f| \n", d);
C. System.out.printf("|%3.7d| \n", d);
D. System.out.printf("|%3.7f| \n", d);
E. System.out.printf("|%7.3d| \n", d);
F. System.out.printf("|%7.3f| \n", d);

Answer: F
Section: All

Explanation/Reference:

QUESTION 7
Given:

11. String test = "Test A. Test B. Test C.";
12. // insert code here
13. String[] result = test.split(regex);

Which regular expression, inserted at line 12, correctly splits test into "Test A", "Test B", and "Test C"?

A. String regex = "";
B. String regex = " ";
C. String regex = ".*";
D. String regex = "\\s";
E. String regex = "\\.\\s*";
F. String regex = "\\w[ \.] +";

Answer: E
Section: All

Explanation/Reference:

QUESTION 8
Given:
1. interface A { public void aMethod(); }
2. interface B { public void bMethod(); }
3. interface C extends A,B { public void cMethod(); }
4. class D implements B {
5. public void bMethod(){}
6. }
7. class E extends D implements C {
8. public void aMethod(){}
9. public void bMethod(){}
10. public void cMethod(){}
11. }
What is the result?

A. Compilation fails because of an error in line 3.
B. Compilation fails because of an error in line 7.
C. Compilation fails because of an error in line 9.
D. If you define D e = new E(), then e.bMethod() invokes the version of bMethod() defined in Line 5.
E. If you define D e = (D)(new E()), then e.bMethod() invokes the version of bMethod() defined in Line 5.
F. If you define D e = (D)(new E()), then e.bMethod() invokes the version of bMethod() defined in Line 9.

Answer: F
Section: All

Explanation/Reference:

QUESTION 9
Click the Exhibit button.
What is the result?


Add caption
A. Value is: 8
B. Compilation fails.
C. Value is: 12
D. Value is: -12
E. The code runs with no output.
F. An exception is thrown at runtime.

Answer: A
Section: All

Explanation/Reference:

QUESTION 10
Given:

public class Base {
     public static final String FOO = "foo";
   
     public static void main(String[] args) {
          Base b = new Base();
          Sub s = new Sub();
          System.out.print(Base.FOO);
          System.out.print(Sub.FOO);
          System.out.print(b.FOO);
          System.out.print(s.FOO);
          System.out.print(((Base) s).FOO);
     }
}
class Sub extends Base {
     public static final String FOO = "bar";
}

What is the result?

A. foofoofoofoofoo
B. foobarfoobarbar
C. foobarfoofoofoo
D. foobarfoobarfoo
E. barbarbarbarbar
F. foofoofoobarbar
G. foofoofoobarfoo

Answer: D
Section: All

Explanation/Reference:

QUESTION 11
Given:

1. class Mammal {
2. }
3.
4. class Raccoon extends Mammal {
5. Mammal m = new Mammal();
6. }
7.
8. class BabyRaccoon extends Mammal {
9. }
10.
Which four statements are true? (Choose four.)

A. Raccoon is-a Mammal.
B. Raccoon has-a Mammal.
C. BabyRaccoon is-a Mammal.
D. BabyRaccoon is-a Raccoon.
E. BabyRaccoon has-a Mammal.
F. BabyRaccoon is-a BabyRaccoon.

Answer: ABCF
Section: All

Explanation/Reference:

QUESTION 12
Given:

interface A { void x(); }
class B implements A { public void x() {} public void y() {} }
class C extends B { public void x() {} }

And:

java.util.List<A> list = new java.util.ArrayList<A>();
list.add(new B());
list.add(new C());
for (A a : list) {
     a.x();
     a.y(); //Linea 25
}

What is the result?

A. The code runs with no output.
B. An exception is thrown at runtime.
C. Compilation fails because of an error in line 20.
D. Compilation fails because of an error in line 21.
E. Compilation fails because of an error in line 23.
F. Compilation fails because of an error in line 25.

Answer: F
Section: All

Explanation/Reference:

QUESTION 13
Given:

1.
2. public class Hi {
3. void m1() { }
4. protected void() m2 { }
5. }
6. class Lois extends Hi {
7. // insert code here
8. }

Which four code fragments, inserted independently at line 7, will compile? (Choose four.)

A. public void m1() { }
B. protected void m1() { }
C. private void m1() { }
D. void m2() { }
E. public void m2() { }
F. protected void m2() { }
G. private void m2() { }

Answer: ABEF
Section: All

Explanation/Reference:

QUESTION 14
Which four statements are true? (Choose four.)

A. Has-a relationships should never be encapsulated.
B. Has-a relationships should be implemented using inheritance.
C. Has-a relationships can be implemented using instance variables.
D. Is-a relationships can be implemented using the extends keyword.
E. Is-a relationships can be implemented using the implements keyword.
F. The relationship between Movie and Actress is an example of an is-a relationship.
G. An array or a collection can be used to implement a one-to-many has-a relationship.

Answer: CDEG
Section: All

Explanation/Reference:

QUESTION 15
Given:

public class Hello {
     String title;
     int value;
   
     public Hello() {
          title += " World";
     }
   
     public Hello(int value) {
          this.value = value;
          title = "Hello";
          Hello();
     }
}

and:

Hello c = new Hello(5);
System.out.println(c.title);

What is the result?

A. Hello
B. Hello World
C. Compilation fails.
D. Hello World 5
E. The code runs with no output.
F. An exception is thrown at runtime.

Answer: C
Section: All

Explanation/Reference:

QUESTION 16
Given:
1. package geometry;
2.
3. public class Hypotenuse {
4. public InnerTriangle it = new InnerTriangle();
5.
6. class InnerTriangle {
7. public int base;
8. public int height;
9. }
10. }
Which statement is true about the class of an object that can reference the variable base?

A. It can be any class.
B. No class has access to base.
C. The class must belong to the geometry package.
D. The class must be a subclass of the class Hypotenuse.

Answer: C
Section: All

Explanation/Reference:

QUESTION 17
Click the Exhibit button.

1. public class A {
2.
3. private int counter = 0;
4.
5. public static int getInstanceCount(){
6. return counter;
7. }
8.
9. public A(){
10. counter++;
11. }
12. }
13.

Given this code from Class B:

A a1 = new A();
A a2 = new A();
A a3 = new A();
System.out.println(A.getInstanceCount());

What is the result?

A. Compilation of class A fails.
B. Line 28 prints the value 3 to System.out.
C. Line 28 prints the value 1 to System.out.
D. A runtime error occurs when line 25 executes.
E. Compilation fails because of an error on line 28.

Answer: A
Section: All

Explanation/Reference:

QUESTION 18
Given:

10. interface Data { public void load(); }
11. abstract class Info { public abstract void load(); }

Which class correctly uses the Data interface and Info class?

A. public class Employee extends Info implements Data { public void load() { /
   *do something*/ }
   }
B. public class Employee implements Info extends Data { public void load() { /
   *do something*/ }
   }
C. public class Employee extends Info implements Data public void load(){ /*do
   something*/ }
   public void Info.load(){ /*do something*/ }
   }
D. public class Employee implements Info extends Data { public void Data.load()
   { /*do something*/ }
   public void load(){ /*do something*/ }
   }
E. public class Employee implements Info extends Data { public void load(){ /
   *do something*/ }
   public void Info.load(){ /*do something*/ }
   }
F. public class Employee extends Info implements Data{ public void Data.load()
   { /*do something*/ }
   public void Info.load() { /*do something*/ }
   }
 
Answer: A
Section: All

Explanation/Reference:

QUESTION 19
Given:

1. class Alligator {
2. public static void main(String[] args) {
3. int[] x[] = { { 1, 2 }, { 3, 4, 5 }, { 6, 7, 8, 9 } };
4. int[][] y = x;
5. System.out.println(y[2][1]);
6. }
7. }

What is the result?

A. 2
B. 3
C. 4
D. 6
E. 7
F. Compilation fails.

Answer: E
Section: All

Explanation/Reference:

QUESTION 20
Given:

abstract class C1 {
public C1() { System.out.print(1); }
}
class C2 extends C1 {
public C2() { System.out.print(2); }
}
class C3 extends C2 {
public C3() { System.out.println(3); }
}
public class Ctest {
public static void main(String[] a) { new C3(); }
}

What is the result?

A. 3
B. 23
C. 32
D. 123
E. 321
F. Compilation fails.
G. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 21
Given:
class One {
     public One foo() {
          return this;
     }
}
class Two extends One {
     public One foo() {
          return this;
     }
}
class Three extends Two {
     // insert method here
}
Which two methods, inserted individually, correctly complete the Three class? (Choose two.)

A. public void foo() {}
B. public int foo() { return 3; }
C. public Two foo() { return this; }
D. public One foo() { return this; }
E. public Object foo() { return this; }

Answer: CD
Section: All

Explanation/Reference:

QUESTION 22
Which two classes correctly implement both the java.lang.Runnable and the java.lang.
Cloneable interfaces? (Choose two.)

A. public class Session implements Runnable, Cloneable {
        public void run();    
        public Object clone();
   }
B. public class Session   extends Runnable, Cloneable {
        public void run() { /* do something */ }
        public Object clone() { /* make a copy */ }
C. public class Session  implements Runnable, Cloneable {
        public void run() { /* do something */ }
        public Object clone() { /* make a copy */ }
D. public abstract class Session  implements Runnable, Cloneable {
        public void run() { /* do something */ }
        public Object clone() { /*make a copy */ }
E. public class Session  implements Runnable, implements Cloneable {
        public void run() { /* do something */ }
        public Object clone() { /* make a copy */ }
     
Answer: CD
Section: All

Explanation/Reference:

QUESTION 23
Given:

public interface A { public void m1(); }
class B implements A { }
class C implements A { public void m1() { } }
class D implements A { public void m1(int x) { } }
abstract class E implements A { }
abstract class F implements A { public void m1() { } }
abstract class G implements A { public void m1(int x) { } }

What is the result?

A. Compilation succeeds.
B. Exactly one class does NOT compile.
C. Exactly two classes do NOT compile.
D. Exactly four classes do NOT compile.
E. Exactly three classes do NOT compile.

Answer: C
Section: All

Explanation/Reference:

QUESTION 24
Given:

class Line {
     public class Point {
          public int x, y;
     }   
     public Point getPoint() {
          return new Point();
     }
}
class Triangle {
     public Triangle() {
          // insert code here
     }
}

Which code, inserted at line 16, correctly retrieves a local instance of a Point object?

A. Point p = Line.getPoint();
B. Line.Point p = Line.getPoint();
C. Point p = (new Line()).getPoint();
D. Line.Point p = (new Line()).getPoint();

Answer: D
Section: All

Explanation/Reference:

QUESTION 25
Given:

1. class TestA {
2. public void start() { System.out.println("TestA"); }
3. }
4. public class TestB extends TestA {
5. public void start() { System.out.println("TestB"); }
6. public static void main(String[] args) {
7. ((TestA)new TestB()).start();
8. }
9. }

What is the result?

A. TestA
B. TestB
C. Compilation fails.
D. An exception is thrown at runtime.

Answer: B
Section: All

Explanation/Reference:

QUESTION 26
Given:

11. public static void main(String[] args) {
12. Object obj = new int[] { 1, 2, 3 };
13. int[] someArray = (int[])obj;
14. for (int i : someArray) System.out.print(i + " ");
15. }

What is the result?

A. 123
B. Compilation fails because of an error in line 12.
C. Compilation fails because of an error in line 13.
D. Compilation fails because of an error in line 14.
E. A ClassCastException is thrown at runtime.

Answer: A
Section: All

Explanation/Reference:

QUESTION 27
Click the Exhibit button.

1. public class Threads1 {
2. int x = 0;
3. public class Runner implements Runnable {
4. public void run(){
5. int current = 0;
6. for(int i = 0; i<4; i++){
7. current = x;
8. System.out.println(current + ", ");
9. x = current + 2;
10. }
11. }
12. }
13.
14. public static void main(String[] args) {
15. new Threads1().go();
16. }
17.
18. public void go(){
19. Runnable r1 = new Runner();
20. new Thread(r1).start();
21. new Thread(r1).start();
22. }
23. }

Which two are possible results? (Choose two.)

A. 0, 2, 4, 4, 6, 8, 10, 6,
B. 0, 2, 4, 6, 8, 10, 2, 4,
C. 0, 2, 4, 6, 8, 10, 12, 14,
D. 0, 0, 2, 2, 4, 4, 6, 6, 8, 8, 10, 10, 12, 12, 14, 14,
E. 0, 2, 4, 6, 8, 10, 12, 14, 0, 2, 4, 6, 8, 10, 12, 14,

Answer: C
Section: All

Explanation/Reference:

QUESTION 28
Given:
foo and bar are public references available to many other threads. foo refers to a Thread and bar is an
Object.
The thread foo is currently executing bar.wait(). From another thread, what provides the most reliable way
to ensure that foo will stop executing wait()?

A. foo.notify();
B. bar.notify();
C. foo.notifyAll();
D. Thread.notify();
E. bar.notifyAll();
F. Object.notify();

Answer: E
Section: All

Explanation/Reference:

QUESTION 29
Given:
public class PingPong implements Runnable {
     synchronized void hit(long n) {
         for (int i = 1; i < 3; i++)
              System.out.print(n + "-" + i + " ");
     }   
     public static void main(String[] args) {
          new Thread(new PingPong()).start();
          new Thread(new PingPong()).start();
     }
     public void run() {
          hit(Thread.currentThread().getId());
     }
}
Which two statements are true? (Choose two.)

A. The output could be 8-1 7-2 8-2 7-1
B. The output could be 7-1 7-2 8-1 6-1
C. The output could be 8-1 7-1 7-2 8-2
D. The output could be 8-1 8-2 7-1 7-2

Answer: CD
Section: All

Explanation/Reference:

QUESTION 30
Click the Exhibit button.

class Computation extends Thread {
     private int num;
     private boolean isComplete;
     private int result;
     public Computation(int num){ this.num = num; }
     public synchronized void run() {
          result = num * 2;
          isComplete = true;
          notify();
     }   
     public synchronized int getResult() {
          while ( ! isComplete ){
               try {
                   wait();
              } catch (InterruptedException e) {
              }
          }
          return result;
     }   
     public static void main(String[] args) {
          Computation[] computations = new Computation[4];
          for (int i = 0; i < computations.length; i++) {
              computations[i] = new Computation(i);
              computations[i].start();
          }
          for (Computation c : computations) {
              System.out.println(c.getResult() + " ");
          }
     }
}

What is the result?

A. The code will deadlock.
B. The code may run with no output.
C. An exception is thrown at runtime.
D. The code may run with output "0 6".
E. The code may run with output "2 0 6 4".
F. The code may run with output "0 2 4 6".

Answer: F
Section: All
