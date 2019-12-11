QUESTION 1
Given:

2. public class Threads2 implements Runnable {
3.
4.    public void run() {
5.    System.out.println("run.");
6.    throw new RuntimeException("Problem");
7.    }
8.    public static void main(String[] args) {
9.    Thread t = new Thread(new Threads2());
10.    t.start();
11.    System.out.println("End of method.");
12.    }
13. }

Which two can be results? (Choose two.)

A. java.lang.RuntimeException: Problem
B. run.
java.lang.RuntimeException: Problem
C. End of method.
java.lang.RuntimeException: Problem
D. End of method.
run.
java.lang.RuntimeException: Problem
E. run.
java.lang.RuntimeException: Problem
End of method.

Answer: DE
Section: All

Explanation/Reference:
End of method.
run.
Exception in thread "Thread-0" java.lang.RuntimeException: Problem
at Threads2.run(Threads2.java:5)
at java.lang.Thread.run(Unknown Source)

QUESTION 2
Which two statements are true? (Choose two.)

A. It is possible for more than two threads to deadlock at once.
B. The JVM implementation guarantees that multiple threads cannot enter into a deadlocked state.
C. Deadlocked threads release once their sleep() method's sleep duration has expired.
D. Deadlocking can occur only when the wait(), notify(), and notifyAll() methods are used incorrectly.
E. It is possible for a single-threaded application to deadlock if synchronized blocks are used incorrectly.
F. If a piece of code is capable of deadlocking, you cannot eliminate the possibility of deadlocking by
inserting
invocations of Thread.yield().

Answer: AF
Section: All

Explanation/Reference:

QUESTION 3
Given:
void waitForSignal() {
Object obj = new Object();
synchronized (Thread.currentThread()) {
obj.wait();
obj.notify();
}
}
Which statement is true?

A. This code can throw an InterruptedException.
B. This code can throw an IllegalMonitorStateException.
C. This code can throw a TimeoutException after ten minutes.
D. Reversing the order of obj.wait() and obj.notify() might cause this method to complete normally.
E. A call to notify() or notifyAll() from another thread might cause this method to complete normally.
F. This code does NOT compile unless "obj.wait()" is replaced with "((Thread) obj).wait()".

Answer: B
Section: All

Explanation/Reference:
Threads2.java:15: unreported exception java.lang.InterruptedException; must be caught or declared to be thrown.
obj.wait();
^
1 error

The answer appears before the correction was "This code can throw an
IllegalMonitorStateException. "But exceptions are used IllegalMonitorStateException

QUESTION 4
Click the Exhibit button.
What is the output if the main() method is run?

1. public class Starter extends Thread {
2.    private int x = 2;
3.    public static void main(String[] args) throws Exception {
4.    new Starter().makeItSo();
5.    }
6.    public Starter(){
7.    x = 5;
8.    start();
9.    }
10.    public void makeItSo() throws Exception {
11.    join();
12.    x = x - 1;
13.    System.out.println(x);
14.    }
15.    public void run() { x *= 2; }
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



QUESTION 5
Given:
1. class PingPong2 {
2.    synchronized void hit(long n) {
3.    for(int i = 1; i < 3; i++)
4.    System.out.print(n + "-" + i + " ");
5.    }
6. }

1. public class Tester implements Runnable {
2.    static PingPong2 pp2 = new PingPong2();
3.    public static void main(String[] args) {
4.    new Thread(new Tester()).start();
5.    new Thread(new Tester()).start();
6.    }
7.    public void run() { pp2.hit(Thread.currentThread().getId()); }
8. }

Which statement is true?

A. The output could be 5-1 6-1 6-2 5-2
B. The output could be 6-1 6-2 5-1 5-2
C. The output could be 6-1 5-2 6-2 5-1
D. The output could be 6-1 6-2 5-1 7-1

Answer: B
Section: All

Explanation/Reference:
The answer you get is second sequence number n-1 n-2 n-1 n-2

QUESTION 6
Given:
1. public class Threads4 {
2.    public static void main (String[] args) {
3.    new Threads4().go();
4.    }
5.    public void go() {
6.    Runnable r = new Runnable() {
7.    public void run() {
8.    System.out.print("foo");
9.    }
10.    };
11.    Thread t = new Thread(r);
12.    t.start();
13.    t.start();
14.    }
15. }

What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. The code executes normally and prints "foo".
D. The code executes normally, but nothing is printed.

Answer: B
Section: All

Explanation/Reference:

fooException in thread "main" java.lang.IllegalThreadStateException
at java.lang.Thread.start(Unknown Source)
at p6.Threads4.go(Threads4.java:15)
at p6.Threads4.main(Threads4.java:5)

QUESTION 7
Given:
1. public abstract class Shape {
2.    private int x;
3.    private int y;
4.    public abstract void draw();
5.    public void setAnchor(int x, int y) {
6.    this.x = x;
7.    this.y = y;
8.    }
9. }

Which two classes use the Shape class correctly? (Choose two.)

A. public class Circle implements Shape {
private int radius;
}
B. public abstract class Circle extends Shape {
private int radius;
}
C. public class Circle extends Shape {
private int radius;
public void draw();
}
D. public abstract class Circle implements Shape {
private int radius;
public void draw();
}
E. public class Circle extends Shape {
private int radius;
public void draw() {/* code here */}
}
F. public abstract class Circle implements Shape {
private int radius;
public void draw() {/* code here */}
}

Answer: BE
Section: All

Explanation/Reference:

QUESTION 8
Given:
1. public class Barn {
2.    public static void main(String[] args) {
3.    new Barn().go("hi", 1);
4.    new Barn().go("hi", "world", 2);
5.    }
6.    public void go(String... y, int x) {
7.    System.out.print(y[y.length - 1] + " ");
8.    }
9. }

What is the result?

A. hi hi
B. hi world
C. world world
D. Compilation fails.
E. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:
The method go(String[], int) in the type Barn is not applicable for the arguments (String, int)
The variable argument type String of the method go must be the last parameter

QUESTION 9
Given:
1. class Nav{
2.    public enum Direction { NORTH, SOUTH, EAST, WEST }
3. }

1. public class Sprite{
2.    //    insert code here
3. }

Which code, inserted at line 14, allows the Sprite class to compile?

A. Direction d = NORTH;
B. Nav.Direction d = NORTH;
C. Direction d = Direction.NORTH;
D. Nav.Direction d = Nav.Direction.NORTH;

Answer: D
Section: All

Explanation/Reference:

QUESTION 10
Click the Exhibit button.
Which statement is true about the classes and interfaces in the exhibit?

1. public interface A {
2.    public void doSomething(String thing);
3. }

1. public class AImpl implements A {
2.    public void doSomething(String msg) {}
3. }

1. public class B {
2.    public A doit(){
3.    //more code here
4.    }
5.    public String execute(){
6.    //more code here
7.    }
8. }

1. public class C extends B {
2.    public AImpl doit(){
3.    //more code here
4.    }
5.
6.    public Object execute() {
7.    //more code here
8.    }
9. }

A. Compilation will succeed for all classes and interfaces.
B. Compilation of class C will fail because of an error in line 2.
C. Compilation of class C will fail because of an error in line 6.
D. Compilation of class AImpl will fail because of an error in line 2.

Answer: C
Section: All

Explanation/Reference:
The return type is incompatible with B.execute()

QUESTION 11
Click the Exhibit button.
What is the result?

11. public class Person {
12.    String name = "No name";
13.    public Person(String nm) { name = nm; }
14. }
15.
16. public class Employee extends Person {
17.    String empID = "0000";
18.    public Employee(String id) { empID = id; }
19. }
20.
21. public class EmployeeTest {
22.    public static void main(String[] args){
23.    Employee e = new Employee("4321");
24.    System.out.println(e.empID);
25.    }
26. }


A. 4321
B. 0000
C. An exception is thrown at runtime.
D. Compilation fails because of an error in line 18.

Answer: D
Section: All

Explanation/Reference:
Implicit super constructor Person() is undefined. Must explicitly invoke another constructor


QUESTION 12
Given:
1. public class Rainbow {
2.    public enum MyColor {
3.    RED(0xff0000), GREEN(0x00ff00), BLUE(0x0000ff);
4.    private final int rgb;
5.    MyColor(int rgb) { this.rgb = rgb; }
6.    public int getRGB() { return rgb; }
7.    };
8.    public static void main(String[] args) {
9.    //insert code here
10.    }
11. }

Which code fragment, inserted at line 19, allows the Rainbow class to compile?

A. MyColor skyColor = BLUE;
B. MyColor treeColor = MyColor.GREEN;
C. if(RED.getRGB() < BLUE.getRGB()) { }
D. Compilation fails due to other error(s) in the code.
E. MyColor purple = new MyColor(0xff00ff);
F. MyColor purple = MyColor.BLUE + MyColor.RED;

Answer: B
Section: All

Explanation/Reference:

QUESTION 13
Given:
1. public class Mud {
2.    //insert code here
3.    System.out.println("hi");
4.    }
5. }

And the following five fragments:
public static void main(String...a) {
public static void main(String.* a) {
public static void main(String... a) {
public static void main(String[]... a) {
public static void main(String...[] a) {

How many of the code fragments, inserted independently at line 2, compile?

A. 0
B. 1
C. 2
D. 3
E. 4
F. 5

Answer: D
Section: All

Explanation/Reference:
public static void main(String...a) {
public static void main(String... a) {
public static void main(String[]... a) {


QUESTION 14
Given:
1. class Atom {
2.    Atom() { System.out.print("atom "); }
3. }
4. class Rock extends Atom {
5.    Rock(String type) { System.out.print(type); }
6. }
7. public class Mountain extends Rock {
8.    Mountain() {
9.    super("granite ");
10.    new Rock("granite ");
11.    }
12.    public static void main(String[] a) { new Mountain(); }
13. }

What is the result?

A. Compilation fails.
B. atom granite
C. granite granite
D. atom granite granite
E. An exception is thrown at runtime.
F. atom granite atom granite

Answer: F
Section: All

Explanation/Reference:

QUESTION 15
Given:
interface TestA { String toString(); }
public class Test {
public static void main(String[] args) {
System.out.println(new TestA() {
public String toString() { return "test"; }
});
}
}

What is the result?

A. test
B. null
C. An exception is thrown at runtime.
D. Compilation fails because of an error in line 1.
E. Compilation fails because of an error in line 4.
F. Compilation fails because of an error in line 5.

Answer: A
Section: All

Explanation/Reference:

QUESTION 16
Given:
1.    public static void parse(String str) {
2.    try {
3.    float f = Float.parseFloat(str);
4.    } catch (NumberFormatException nfe) {
5.    f = 0;
6.    } finally {
7.    System.out.println(f);
8.    }
9.    }
10.    public static void main(String[] args) {
11.    parse("invalid");
12.    }

What is the result?

A. 0.0
B. Compilation fails.
C. A ParseException is thrown by the parse method at runtime.
D. A NumberFormatException is thrown by the parse method at runtime.

Answer: B
Section: All

Explanation/Reference:
f cannot be resolved en la linea 5 y 7

QUESTION 17
Given:
1. public class Blip {
2.    protected int blipvert(int x) { return 0; }
3. }
4. class Vert extends Blip {
5.    //    insert code here
6. }

Which five methods, inserted independently at line 5, will compile? (Choose five.)

A. public int blipvert(int x) { return 0; }
B. private int blipvert(int x) { return 0; }
C. private int blipvert(long x) { return 0; }
D. protected long blipvert(int x) { return 0; }
E. protected int blipvert(long x) { return 0; }
F. protected long blipvert(long x) { return 0; }
G. protected long blipvert(int x, int y) { return 0; }

Answer: ACEFG
Section: All

Explanation/Reference:
private int blipvert(int x) { return 0; }
Cannot reduce the visibility of the inherited method from Blip
protected long blipvert(int x) { return 0; }
The return type is incompatible with Blip.blipvert(int)

QUESTION 18
Given:
1. class Super {
2.    private int a;
3.    protected Super(int a) { this.a = a; }
4. }

11. class Sub extends Super {
12.    public Sub(int a) { super(a); }
13.    public Sub() { this.a = 5; }
14. }

Which two, independently, will allow Sub to compile? (Choose two.)

A. Change line 2 to:
public int a;
B. Change line 2 to:
protected int a;
C. Change line 13 to:
public Sub() { this(5); }
D. Change line 13 to:
public Sub() { super(5); }
E. Change line 13 to:
public Sub() { super(a); }

Answer: CD
Section: All

Explanation/Reference:

QUESTION 19
Which Man class properly represents the relationship "Man has a best friend who is a Dog"?

A. class Man extends Dog { }
B. class Man implements Dog { }
C. class Man { private BestFriend dog; }
D. class Man { private Dog bestFriend; }
E. class Man { private Dog<bestFriend>; }
F. class Man { private BestFriend<dog>; }

Answer: D
Section: All

Explanation/Reference:

QUESTION 20
Given:
1. package test;
2.
3. class Target {
4.    public String name = "hello";
5. }
What can directly access and change the value of the variable name?

A. any class
B. only the Target class
C. any class in the test package
D. any class that extends Target

Answer: C
Section: All

Explanation/Reference:

QUESTION 21
Given:
11. abstract class Vehicle { public int speed() { return 0; }
12. class Car extends Vehicle { public int speed() { return 60; }
13. class RaceCar extends Car { public int speed() { return 150; }
 ...
21.    RaceCar racer = new RaceCar();
22.    Car car = new RaceCar();
23    Vehicle vehicle = new RaceCar();
24    System.out.println(racer.speed() + ", " + car.speed() + ", " + vehicle.
speed());

What is the result?

A. 0, 0, 0
B. 150, 60, 0
C. Compilation fails.
D. 150, 150, 150
E. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 22
Given:
5. class Building { }
6. public class Barn extends Building {
7.    public static void main(String[] args) {
8.    Building build1 = new Building();
9.    Barn barn1 = new Barn();
10.    Barn barn2 = (Barn) build1;
11.    Object obj1 = (Object) build1;
12.    String str1 = (String) build1;
13.    Building build2 = (Building) barn1;
14.    }
15. }

Which is true?

A. If line 10 is removed, the compilation succeeds.
B. If line 11 is removed, the compilation succeeds.
C. If line 12 is removed, the compilation succeeds.
D. If line 13 is removed, the compilation succeeds.
E. More than one line must be removed for compilation to succeed.

Answer: C
Section: All

Explanation/Reference:
Cannot cast from Building to String

QUESTION 23
A team of programmers is reviewing a proposed API for a new utility class. After some discussion, they realize that they can reduce the number of methods in the API without losing any functionality. If they implement the new design, which two OO principles will they be promoting?

A. Looser coupling
B. Tighter coupling
C. Lower cohesion
D. Higher cohesion
E. Weaker encapsulation
F. Stronger encapsulation

Answer: A
Section: All

Explanation/Reference:

QUESTION 24
Given:
21. class Money {
22.    private String country = "Canada";
23.    public String getC() { return country; }
24. }
25. class Yen extends Money {
26.    public String getC() { return super.country; }
27. }
28. public class Euro extends Money {
29.    public String getC(int x) { return super.getC(); }
30.    public static void main(String[] args) {
31.    System.out.print(new Yen().getC() + " " + new Euro().getC());
32.    }
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

QUESTION 25
Assuming that the serializeBanana() and the deserializeBanana() methods will correctly use Java serialization and given:

13. import java.io.*;
14. class Food implements Serializable {int good = 3;}
15. class Fruit extends Food {int juice = 5;}
16. public class Banana extends Fruit {
17.    int yellow = 4;
18.    public static void main(String [] args) {
19.    Banana b = new Banana(); Banana b2 = new Banana();
20.    b.serializeBanana(b); // assume correct serialization
21.    b2 = b.deserializeBanana(); // assume correct
22.    System.out.println("restore "+b2.yellow+ b2.juice+b2.good);
24.    }
25. //    more Banana methods go here
50. }

What is the result?

A. restore 400
B. restore 403
C. restore 453
D. Compilation fails.
E. An exception is thrown at runtime.

Answer: C
Section: All

Explanation/Reference:

QUESTION 26
Given a valid DateFormat object named df, and

16. Date d = new Date(0L);
17. String ds = "December 15, 2004";
18. //insert code here

What updates d's value with the date represented by ds?

A. 18. d = df.parse(ds);
B. 18. d = df.getDate(ds);
C. 18. try {
19. d = df.parse(ds);
20. } catch(ParseException e) { };
D. 18. try {
19. d = df.getDate(ds);
20. } catch(ParseException e) { };

Answer: C
Section: All

Explanation/Reference:

QUESTION 27
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

QUESTION 28
Given:
1. public class TestString1 {
2.    public static void main(String[] args) {
3.    String str = "420";
4.    str += 42;
5.    System.out.print(str);
6.    }
7. }

What is the output?

A. 42
B. 420
C. 462
D. 42042
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 29
Which capability exists only in java.io.FileWriter?

A. Closing an open stream.
B. Flushing an open stream.
C. Writing to an open stream.
D. Writing a line separator to an open stream.

Answer: D
Section: All

Explanation/Reference:

QUESTION 30
Given that the current directory is empty, and that the user has read and write permissions, and the following:
1. import java.io.*;
2. public class DOS {
3.    public static void main(String[] args) {
4.    File dir = new File("dir");
5.    dir.mkdir();
6.    File f1 = new File(dir, "f1.txt");
7.    try {
8.    f1.createNewFile();
9.    } catch (IOException e) { ; }
10.    File newDir = new File("newDir");
11.    dir.renameTo(newDir);
12.    }
13. }

Which statement is true?

A. Compilation fails.
B. The file system has a new empty directory named dir.
C. The file system has a new empty directory named newDir.
D. The file system has a directory named dir, containing a file f1.txt.
E. The file system has a directory named newDir, containing a file f1.txt.

Answer: E
Section: All

Explanation/Reference:

QUESTION 31
Given:
static void test() throws RuntimeException {
try {
System.out.print("test ");
throw new RuntimeException();
}
catch (Exception ex) { System.out.print("exception "); }
}
public static void main(String[] args) {
try { test(); }
catch (RuntimeException ex) { System.out.print("runtime "); }
System.out.print("end ");
}

What is the result?

A. test end
B. Compilation fails.
C. test runtime end
D. test exception end
E. A Throwable is thrown by main at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 32
Given:
1. public class Score implements Comparable<Score> {
2.    private int wins, losses;
3.    public Score(int w, int l) { wins = w; losses = l; }
4.    public int getWins() { return wins; }
5.    public int getLosses() { return losses; }
6.    public String toString() {
7.    return "<" + wins + "," + losses + ">";
8.    }
9. //    insert code here
10. }
11.

Which method will complete this class?

A. public int compareTo(Object o){/*more code here*/}
B. public int compareTo(Score other){/*more code here*/}
C. public int compare(Score s1,Score s2){/*more code here*/}
D. public int compare(Object o1,Object o2){/*more code here*/}

Answer: B
Section: All
