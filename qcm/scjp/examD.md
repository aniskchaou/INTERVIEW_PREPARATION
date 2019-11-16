EXAM D

QUESTION 1
Given:
interface Foo { int bar(); }
public class Sprite {
     public int fubar( Foo foo ) { return foo.bar(); }
     public void testFoo() {
          fubar(
            //insert code here 15
          );
     }
}
Which code, inserted at line 15, allows the class Sprite to compile?

A. Foo { public int bar() { return 1; }
B. new Foo { public int bar() { return 1; }
C. new Foo() { public int bar() { return 1; }
D. new class Foo { public int bar() { return 1; }

Answer: C
Section: All

Explanation/Reference:

QUESTION 2
Given:
11. public enum Title {
12. MR("Mr."), MRS("Mrs."), MS("Ms.");
13. private final String title;
14. private Title(String t) { title = t; }
15. public String format(String last, String first) {
16. return title + " " + first + " " + last;
17. }
18. }

     public static void main(String[] args) {
          System.out.println(Title.MR.format("Doe", "John"));
     }
   
What is the result?

A. Mr. John Doe
B. An exception is thrown at runtime.
C. Compilation fails because of an error in line 12.
D. Compilation fails because of an error in line 15.
E. Compilation fails because of an error in line 20.

Answer: A
Section: All

Explanation/Reference:

QUESTION 3
Given the following six method names:

   addListener
   addMouseListener
   setMouseListener
   deleteMouseListener
   removeMouseListener
   registerMouseListener
 
How many of these method names follow JavaBean Listener naming rules?

A. 1
B. 2
C. 3
D. 4
E. 5

Answer: B
Section: All

Explanation/Reference:

QUESTION 4
Given:
class Line {
     public static class Point {}
}
class Triangle {
     public Triangle(){
        //  insert code here
     }
}
Which code, inserted at line 15, creates an instance of the Point class defined in Line?

A. Point p = new Point();
B. Line.Point p = new Line.Point();
C. The Point class cannot be instatiated at line 15.
D. Line l = new Line() ; l.Point p = new l.Point();

Answer: B
Section: All

Explanation/Reference:

QUESTION 5
Given:
11. public interface Status {
12. /* insert code here */ int MY_VALUE = 10;
13. }
Which three are valid on line 12? (Choose three.)

A. final
B. static
C. native
D. public
E. private
F. abstract
G. protected

Answer: ABD
Section: All

Explanation/Reference:

QUESTION 6
Click the Exhibit button.
Given this code from Class B:

  25. A a1 = new A();
  26. A a2 = new A();
  27. A a3 = new A();
  28. System.out.println(A.getInstanceCount());

What is the result?

1. public class A{
2.
3. private int counter = 0;
4.
5. public static int getInstanceCount() {
6. return counter;
7. }
8.
9. public A() {
10. counter++;
11. }
12.
13. }


A. Compilation of class A fails.
B. Line 28 prints the value 3 to System.out.
C. Line 28 prints the value 1 to System.out.
D. A runtime error occurs when line 25 executes.
E. Compilation fails because of an error on line 28.

Answer: A
Section: All

Explanation/Reference:

QUESTION 7
Given classes defined in two different files:
1. package util;
2. public class BitUtils {
3. public static void process(byte[] b) { /* more code here */ }
4. }

1. package app;
2. public class SomeApp {
3. public static void main(String[] args) {
4. byte[] bytes = new byte[256];
5. // insert code here
6. }
7. }
What is required at line 5 in class SomeApp to use the process method of BitUtils?

A. process(bytes);
B. BitUtils.process(bytes);
C. util.BitUtils.process(bytes);
D. SomeApp cannot use methods in BitUtils.
E. import util.BitUtils.*; process(bytes);

Answer: C
Section: All

Explanation/Reference:

QUESTION 8
Click the Exhibit button.
Which three code fragments, added individually at line 29, produce the output 100? (Choose three.)

class Inner {
     private int x;
     public void setX( int x ){ this.x = x; }
     public int getX(){ return x;}
}

class Outer {
     private Inner y;
     public void setY( Inner y ){ this.y = y; }
     public Inner getY() { return y; }
}

public class Gamma {
     public static void main(String[] args) {
          Outer o = new Outer();
          Inner i = new Inner();
          int n = 10;
          i.setX(n);
          o.setY(i);
          // insert code here 29
          System.out.println(o.getY().getX());
       
     }
}

A. n = 100;
B. i.setX( 100 );
C. o.getY().setX( 100 );
D. i = new Inner(); i.setX( 100 );
E. o.setY( i ); i = new Inner(); i.setX( 100 );
F. i = new Inner(); i.setX( 100 ); o.setY( i );

Answer: BCF
Section: All

Explanation/Reference:

QUESTION 9
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

QUESTION 10
Which statement is true?

A. A class's finalize() method CANNOT be invoked explicitly.
B. super.finalize() is called implicitly by any overriding finalize() method.
C. The finalize() method for a given object is called no more than once by the garbage collector.
D. The order in which finalize() is called on two objects is based on the order in which the two objects  became finalizable.
 
Answer: C
Section: All

Explanation/Reference:

QUESTION 11
Given:
class Snoochy {
     Boochy booch;   
     public Snoochy() { booch = new Boochy(this); }
}
class Boochy {
     Snoochy snooch;
     public Boochy(Snoochy s) { snooch = s; }
}
And the statements:
public static void main(String[] args) {
     Snoochy snoog = new Snoochy();
     snoog = null; //Línea 23
    // more code here
}

Which statement is true about the objects referenced by snoog, snooch, and booch immediately after line 23 executes?

A. None of these objects are eligible for garbage collection.
B. Only the object referenced by booch is eligible for garbage collection.
C. Only the object referenced by snoog is eligible for garbage collection.
D. Only the object referenced by snooch is eligible for garbage collection.
E. The objects referenced by snooch and booch are eligible for garbage collection.

Answer: E
Section: All

Explanation/Reference:

QUESTION 12
Given:
3. interface Animal { void makeNoise(); }
4. class Horse implements Animal {
5. Long weight = 1200L;
6. public void makeNoise() { System.out.println("whinny"); }
7. }
8. public class Icelandic extends Horse {
9. public void makeNoise() { System.out.println("vinny"); }
10. public static void main(String[] args) {
11. Icelandic i1 = new Icelandic();
12. Icelandic i2 = new Icelandic();
13. Icelandic i3 = new Icelandic();
14. i3 = i1; i1 = i2; i2 = null; i3 = i1;
15. }
16. }   
   
When line 15 is reached, how many objects are eligible for the garbage collector?

A. 0
B. 1
C. 2
D. 3
E. 4
F. 6

Answer: E
Section: All

Explanation/Reference:

QUESTION 13
Given:
class Payload {
     private int weight;
     public Payload (int w) { weight = w; }
     public void setWeight(int w) { weight = w; }
     public String toString() { return Integer.toString(weight); }
}
public class TestPayload {
     static void changePayload(Payload p) { /* insert code */ } //Línea 12
     public static void main(String[] args) {
          Payload p = new Payload(200);
          p.setWeight(1024);
          changePayload(p);
          System.out.println("p is " + p);
     } 
}   
   
Which code fragment, inserted at the end of line 12, produces the output p is 420?

A. p.setWeight(420);
B. p.changePayload(420);
C. p = new Payload(420);
D. Payload.setWeight(420);
E. p = Payload.setWeight(420);

Answer: A
Section: All

Explanation/Reference:

QUESTION 14
Given:
public static void test(String str) {
     int check = 4;
     if (check = str.length()) {
          System.out.print(str.charAt(check -= 1) +", ");
     } else {
          System.out.print(str.charAt(0) + ", ");
     }
}
and the invocation:

test("four");
test("tee");
test("to");

What is the result?

A. r, t, t,
B. r, e, o,
C. Compilation fails.
D. An exception is thrown at runtime.

Answer: C
Section: All

Explanation/Reference:

QUESTION 15
A UNIX user named Bob wants to replace his chess program with a new one, but he is not sure where the old one is installed. Bob is currently able to run a Java chess program starting from his home directory /home/bob using the
command:
     java -classpath /test:/home/bob/downloads/*.jar games.
Chess Bob's CLASSPATH is set (at login time) to:
    /usr/lib:/home/bob/classes:/opt/java/lib:/opt/java/lib/*.jar

What is a possible location for the Chess.class file?

A. /test/Chess.class
B. /home/bob/Chess.class
C. /test/games/Chess.class
D. /usr/lib/games/Chess.class
E. /home/bob/games/Chess.class
F. inside jarfile /opt/java/lib/Games.jar (with a correct manifest)
G. inside jarfile /home/bob/downloads/Games.jar (with a correct manifest)

Answer: C
Section: All

Explanation/Reference:

QUESTION 16
Given classes defined in two different files:

package util;
public class BitUtils {
     private static void process(byte[] b) {}
}
package app;
public class SomeApp {
     public static void main(String[] args) {
          byte[] bytes = new byte[256];
// insert code here Linea 5
     }
}

What is required at line 5 in class SomeApp to use the process method of BitUtils?

A. process(bytes);
B. BitUtils.process(bytes);
C. app.BitUtils.process(bytes);
D. util.BitUtils.process(bytes);
E. import util.BitUtils.*; process(bytes);
F. SomeApp cannot use the process method in BitUtils.

Answer: F
Section: All

Explanation/Reference:

QUESTION 17
Given:
public class Pass2 {
     public void main(String [] args) {
          int x = 6;
          Pass2 p = new Pass2();
          p.doStuff(x);
          System.out.print(" main x = " + x);
     }
   
     void doStuff(int x) {
          System.out.print(" doStuff x = " + x++);
     }
}

And the command-line invocations:
  javac Pass2.java
  java Pass2 5

What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. doStuff x = 6 main x = 6
D. doStuff x = 6 main x = 7
E. doStuff x = 7 main x = 6
F. doStuff x = 7 main x = 7

Answer: B
Section: All

Explanation/Reference:

QUESTION 18
Given:
public class Test {
     public enum Dogs {collie, harrier};
     public static void main(String [] args) {
          Dogs myDog = Dogs.collie;
          switch (myDog) {
          case collie:
              System.out.print("collie ");
          case harrier:
              System.out.print("harrier ");
          }
     }
}

What is the result?

A. collie
B. harrier
C. Compilation fails.
D. collie harrier
E. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 19
Given:
public class Donkey {
     public static void main(String[] args) {
          boolean assertsOn = false;
          assert (assertsOn) : assertsOn = true;
          if(assertsOn) {
              System.out.println("assert is on");
          }
     }
}
If class Donkey is invoked twice, the first time without assertions enabled, and the second time with
assertions enabled, what are the results?

A. no output
B. no output  assert is on
C. assert is on
D. no output  An AssertionError is thrown.
E. assert is on  An AssertionError is thrown.
 
Answer: D
Section: All

Explanation/Reference:

QUESTION 20
Given:
static void test() {
     try {
          String x = null;
          System.out.print(x.toString() + " ");
     }
     finally { System.out.print("finally "); }
}
public static void main(String[] args) {
     try { test(); }
     catch (Exception ex) { System.out.print("exception "); }
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

QUESTION 21
Given:
static void test() throws Error {
     if (true) throw new AssertionError();
     System.out.print("test ");
}
public static void main(String[] args) {
     try { test(); }
     catch (Exception ex) { System.out.print("exception "); }
     System.out.print("end ");
}}
What is the result?

A. end
B. Compilation fails.
C. exception end
D. exception test end
E. A Throwable is thrown by main.
F. An Exception is thrown by main.

Answer: E
Section: All

Explanation/Reference:

QUESTION 22
Given:
class TestException extends Exception { }
class A {
     public String sayHello(String name) throws TestException {
          if(name == null) throw new TestException();
          return "Hello " + name;
     }
}
public class TestA {
     public static void main(String[] args) {
          new A().sayHello("Aiko");
     }
}

Which statement is true?

A. Compilation succeeds.
B. Class A does not compile.
C. The method declared on line 9 cannot be modified to throw TestException.
D. TestA compiles if line 10 is enclosed in a try/catch block that catches TestException.

Answer: D
Section: All

Explanation/Reference:

QUESTION 23
Given:
public static Collection get() {
     Collection sorted = new LinkedList();
     sorted.add("B"); sorted.add("C"); sorted.add("A");
     return sorted;
}
public static void main(String[] args) {
     for (Object obj: get()) {
          System.out.print(obj + ", ");
     }
}

What is the result?

A. A, B, C,
B. B, C, A,
C. Compilation fails.
D. The code runs with no output.
E. An exception is thrown at runtime.

Answer: B
Section: All

Explanation/Reference:

QUESTION 24
Given:
static class A {
     void process() throws Exception { throw new Exception(); }
}
static class B extends A {
     void process() { System.out.println("B"); }
}
public static void main(String[] args) {
     new B().process();
}
What is the result?

A. B
B. The code runs with no output.
C. Compilation fails because of an error in line 12.
D. Compilation fails because of an error in line 15.
E. Compilation fails because of an error in line 18.

Answer: A
Section: All

Explanation/Reference:

QUESTION 25
Given:
public class Foo {
     static int[] a;
     static { a[0]=2; }
     public static void main( String[] args ) {}
}
Which exception or error will be thrown when a programmer attempts to run this code?

A. java.lang.StackOverflowError
B. java.lang.IllegalStateException
C. java.lang.ExceptionInInitializerError
D. java.lang.ArrayIndexOutOfBoundsException

Answer: C
Section: All

Explanation/Reference:

QUESTION 26
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

Explanation/Reference:

QUESTION 27
Given:
public static void main(String[] args) {
     Integer i = new Integer(1) + new Integer(2);
     switch(i) {
     case 3: System.out.println("three"); break;
     default: System.out.println("other"); break;
     }
}

What is the result?

A. three
B. other
C. An exception is thrown at runtime.
D. Compilation fails because of an error on line 12.
E. Compilation fails because of an error on line 13.
F. Compilation fails because of an error on line 15.

Answer: A
Section: All

Explanation/Reference:

QUESTION 28
Given:
public static Iterator reverse(List list) {
     Collections.reverse(list);
     return list.iterator();
}
public static void main(String[] args) {
     List list = new ArrayList();
     list.add("1"); list.add("2"); list.add("3");
     for (Object obj: reverse(list))
          System.out.print(obj + ", ");
}

What is the result?

A. 3, 2, 1,
B. 1, 2, 3,
C. Compilation fails.
D. The code runs with no output.
E. An exception is thrown at runtime.

Answer: C
Section: All

Explanation/Reference:

QUESTION 29
Given:

1. public class TestString3 {
2. public static void main(String[] args) {
3. // insert code here
4.
5. System.out.println(s);
6. }
7. }

Which two code fragments, inserted independently at line 3, generate the output 4247? (Choose two.)

A. String s = "123456789";  s = (s-"123").replace(1,3,"24") - "89";
B. StringBuffer s = new StringBuffer("123456789");
C. s.delete(0,3).replace(1,3,"24").delete(4,6);
D. StringBuffer s = new StringBuffer("123456789");
E. substring(3,6).delete(1,3).insert(1, "24");
F. StringBuilder s = new StringBuilder("123456789");
G. substring(3,6).delete(1,2).insert(1, "24");
H. StringBuilder s = new StringBuilder("123456789");
I.  delete(0,3).delete(1,3).delete(2,5).insert(1, "24");

Answer: BC
Section: All

Explanation/Reference:

QUESTION 30
Given:

1. d is a valid, non-null Date object
2. df is a valid, non-null DateFormat object set to the current locale

What outputs the current locale's country name and the appropriate version of d's date?

A. Locale loc = Locale.getLocale();
   System.out.println(loc.getDisplayCountry() + " " + df.format(d));
B. Locale loc = Locale.getDefault();
   System.out.println(loc.getDisplayCountry() + " " + df.format(d));
C. Locale loc = Locale.getLocale();
   System.out.println(loc.getDisplayCountry() + " " + df.setDateFormat(d));
D. Locale loc = Locale.getDefault();
   System.out.println(loc.getDisplayCountry() + " " + df.setDateFormat(d));

Answer: B
Section: All

Explanation/Reference:

QUESTION 31
Click the Exhibit button.
What is the output if the main() method is run?

1. public class Starter extends Thread {
2. private int x = 2;
3. public static void main(String[] args) throws Exception {
4. new Starter().makeItSo();
5. }
6. public Starter(){
7. x = 5;
8. start();
9. }
10. public void makeItSo() throws Exception {
11. join();
12. x = x - 1;
13. System.out.println(x);
14. }
15. public void run() { x *= 2; }
16. }

A. 4
B. 5
C. 8
D. 9
E. Compilation fails.
F. An exception is thrown at runtime.
G. It is impossible to determine for certain.

Answer: D
Section: All

Explanation/Reference:

QUESTION 32
Given:

21. class Money {
22. private String country = "Canada";
23. public String getC() { return country; }
24. }
25. class Yen extends Money {
26. public String getC() { return super.country; }
27. }
28. public class Euro extends Money {
29. public String getC(int x) { return super.getC(); }
30. public static void main(String[] args) {
31. System.out.print(new Yen().getC() + " " + new Euro().getC());
32. }
33. }

What is the result?

A. Canada
B. null Canada
C. Canada null
D. Canada Canada
E. Compilation fails due to an error on line 26.
F. Compilation fails due to an error on line 29.

Answer: E
Section: All

Explanation/Reference:
The field Money.country is not visible