EXAM I

QUESTION 1
Given:

1. public class Pass2 {
2. public void main(String[] args) {
3. int x = 6;
4. Pass2 p = new Pass2();
5. p.doStuff(x);
6. System.out.print(" main x = " + x);
7. }
8.
9. void doStuff(int x) {
10. System.out.print(" doStuff x = " + x++);
11. }
12. }

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
 Exception in thread "main" java.lang.NoSuchMethodError: main

QUESTION 2
Given:
1. interface DeclareStuff {
2. public static final int EASY = 3;
3.
4. void doStuff(int t);
5. }
6.
7. public class TestDeclare implements DeclareStuff {
8. public static void main(String[] args) {
9. int x = 5;
10. new TestDeclare().doStuff(++x);
11. }
12.
13. void doStuff(int s) {
14. s += EASY + ++s;
15. System.out.println("s " + s);
16. }
17. }

What is the result?

A. s 14
B. s 16
C. s 10
D. Compilation fails.
E. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:

Cannot reduce the visibility of the inherited method from DeclareStuff

QUESTION 3
A class games.cards.Poker is correctly defined in the jar file Poker.jar.
A user wants to execute the main method of Poker on a UNIX system using the command:

java games.cards.Poker
What allows the user to do this?

A. put Poker.jar in directory /stuff/java, and set the CLASSPATH to include /stuff/java
B. put Poker.jar in directory /stuff/java, and set the CLASSPATH to include /stuff/java/*.jar
C. put Poker.jar in directory /stuff/java, and set the CLASSPATH to include /stuff/java/Poker.jar
D. put Poker.jar in directory /stuff/java/games/cards, and set the CLASSPATH to include /stuff/java
E. put Poker.jar in directory /stuff/java/games/cards, and set the CLASSPATH to include /stuff/java/*.jar
F. put Poker.jar in directory /stuff/java/games/cards, and set the CLASSPATH to include /stuff/java/Poker.jar
 
Answer: C
Section: All

Explanation/Reference:

QUESTION 4
Given a correctly compiled class whose source code is:

1. package com.sun.sjcp;
2.
3. public class Commander {
4. public static void main(String[] args) {
5. // more code here
6. }
7. }

Assume that the class file is located in /foo/com/sun/sjcp/, the current directory is /foo/, and that the
classpath contains "." (current directory). Which command line correctly runs Commander?

A. java Commander
B. java com.sun.sjcp.Commander
C. java com/sun/sjcp/Commander
D. java -cp com.sun.sjcp Commander
E. java -cp com/sun/sjcp Commander

Answer: B
Section: All

Explanation/Reference:

QUESTION 5
Given:

interface DoStuff2 {
     float getRange(int low, int high);
}

interface DoMore {
     float getAvg(int a, int b, int c);
}

abstract class DoAbstract implements DoStuff2, DoMore {
}

class DoStuff implements DoStuff2 {
     public float getRange(int x, int y) {
          return 3.14f;
     }
}

interface DoAll extends DoMore {
     float getAvg(int a, int b, int c, int d);
}

What is the result?

A. The file will compile without error.
B. Compilation fails. Only line 7 contains an error.
C. Compilation fails. Only line 12 contains an error.
D. Compilation fails. Only line 13 contains an error.
E. Compilation fails. Only lines 7 and 12 contain errors.
F. Compilation fails. Only lines 7 and 13 contain errors.
G. Compilation fails. Lines 7, 12, and 13 contain errors.

Answer: A
Section: All

Explanation/Reference:

QUESTION 6
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

Explanation/Reference:

QUESTION 7
Given:

class Payload {
     private int weight;
   
     public Payload() {
   
     }
   
     public Payload(int w) {
          weight = w;
     }
   
     public void setWeight(int w) {
          weight = w;
     }
   
     public String toString() {
          return Integer.toString(weight);
     }
}

public class TestPayload {
     static void changePayload(Payload p) {
          /* insert code */
     }
   
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

QUESTION 8
Click the Task button.

class A {
     String name = "A";
   
     String getName() {
          return name;
     }
   
     String greeting() {
          return "class A";
     }
}

class B extends A {
     String name = "B";
   
     String greeting() {
          return "class B";
     }
}

public class Client {
     public static void main(String[] args) {
          A a = new A();
          A b = new B();
          System.out.println(a.greeting() + " has name " + a.getName());
          System.out.println(b.greeting() + " has name " + b.getName());
     }
}

A.
B.
C.
D.

Answer: A
Section: All

Explanation/Reference:
class A has name A
class B has name A


QUESTION 9
Click the Exhibit button.
What is the result?




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