EXAM F

QUESTION 1
Which two code fragments will execute the method doStuff() in a separate thread? (Choose two.)

A. new Thread() {
        public void run() { doStuff(); }
   };
B. new Thread() {
        public void start() { doStuff(); }
   };
C. new Thread() {
        public void start() { doStuff(); }
   }.run();
D. new Thread() {
        public void run() { doStuff(); }
   }.start();
E. new Thread(new Runnable() {
        public void run() { doStuff(); }
   }).run();
F. new Thread(new Runnable() {
        public void run() { doStuff(); }
   }).start();
 
Answer: DF
Section: All

Explanation/Reference:

QUESTION 2
Given:

public class Person {
     private String name;
     public Person(String name) {
          this.name = name;
     }
     public boolean equals(Object o) {
          if ( ! ( o instanceof Person) ) return false;
          Person p = (Person) o;
          return p.name.equals(this.name);
     }
}

Which statement is true?

A. Compilation fails because the hashCode method is not overridden.
B. A HashSet could contain multiple Person objects with the same name.
C. All Person objects will have the same hash code because the hashCode method is not overridden.
D. If a HashSet contains more than one Person object with name="Fred", then removing another Person,  also with name="Fred", will remove them all.
 
Answer: B
Section: All

Explanation/Reference:

QUESTION 3
Given:

import java.util.*;
public class SortOf {
     public static void main(String[] args) {
          ArrayList<Integer> a = new ArrayList<Integer>();
          a.add(1); a.add(5); a.add(3);
          Collections.sort(a);
          a.add(2);
          Collections.reverse(a);
          System.out.println(a);
     }
}

What is the result?

A. [1, 2, 3, 5]
B. [2, 1, 3, 5]
C. [2, 5, 3, 1]
D. [5, 3, 2, 1]
E. [1, 3, 5, 2]
F. Compilation fails.
G. An exception is thrown at runtime.

Answer: C
Section: All

Explanation/Reference:

QUESTION 4
Given:
public class Person {
     private name;
     public Person(String name) {
          this.name = name;
     }
     public int hashCode() {
          return 420;
     }
}
Which statement is true?

A. The time to find the value from HashMap with a Person key depends on the size of the map.
B. Deleting a Person key from a HashMap will delete all map entries for all keys of type Person.
C. Inserting a second Person object into a HashSet will cause the first Person object to be removed as a  duplicate.
D. The time to determine whether a Person object is contained in a HashSet is constant and does NOT depend on the size of the map.
 
Answer: A
Section: All

Explanation/Reference:

QUESTION 5
Given:

import java.util.TreeSet;
public class Explorer2 {
     public static void main(String[] args) {
          TreeSet<Integer> s = new TreeSet<Integer>();
          TreeSet<Integer> subs = new TreeSet<Integer>();
          for(int i = 606; i < 613; i++)
               if(i%2 == 0) s.add(i);
          subs = (TreeSet)s.subSet(608, true, 611, true);
          s.add(629);
          System.out.println(s + " " + subs);
     }
}

What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. [608, 610, 612, 629] [608, 610]
D. [608, 610, 612, 629] [608, 610, 629]
E. [606, 608, 610, 612, 629] [608, 610]
F. [606, 608, 610, 612, 629] [608, 610, 629]

Answer: E
Section: All

Explanation/Reference:

QUESTION 6
Given:

public class Drink implements Comparable {
     public String name;
     public int compareTo(Object o) {
          return 0;
     }
}

and:

Drink one = new Drink();
Drink two = new Drink();
one.name= "Coffee";
two.name= "Tea";
TreeSet set = new TreeSet();
set.add(one);
set.add(two);

A programmer iterates over the TreeSet and prints the name of each Drink object.
What is the result?

A. Tea
B. Coffee
C. Coffee Tea
D. Compilation fails.
E. The code runs with no output.
F. An exception is thrown at runtime.

Answer: B
Section: All

Explanation/Reference:

QUESTION 7
A programmer must create a generic class MinMax and the type parameter of MinMax must implement
Comparable.
Which implementation of MinMax will compile?

A. class MinMax<E extends Comparable<E>> {
        E min = null;
        E max = null;
        public MinMax() {}
        public void put(E value) { /* store min or max */ }
B. class MinMax<E implements Comparable<E>> {
        E min = null;
        E max = null;
        public MinMax() {}
        public void put(E value) { /* store min or max */ }
C. class MinMax<E extends Comparable<E>> {
        <E> E min = null;
        <E> E max = null;
        public MinMax() {}
        public <E> void put(E value) { /* store min or max */ }
D. class MinMax<E implements Comparable<E>> {
        <E> E min = null;
        <E> E max = null;
        public MinMax() {}
        public <E> void put(E value) { /* store min or max */ }
     
Answer: A
Section: All

Explanation/Reference:

QUESTION 8
Given:
1. import java.util.*;
2. public class Example {
3. public static void main(String[] args) {
4. // insert code here
5. set.add(new Integer(2));
6. set.add(new Integer(1));
7. System.out.println(set);
8. }
9. }
Which code, inserted at line 4, guarantees that this program will output [1, 2]?

A. Set set = new TreeSet();
B. Set set = new HashSet();
C. Set set = new SortedSet();
D. List set = new SortedList();
E. Set set = new LinkedHashSet();

Answer: AB
Section: All

Explanation/Reference:

QUESTION 9
Given:
1.
2.
3.
4.
5. class A {
6. void foo() throws Exception { throw new Exception(); }
7. }
8. class SubB2 extends A {
9. void foo() { System.out.println("B "); }
10. }
11. class Tester {
12. public static void main(String[] args) {
13. A a = new SubB2();
14. a.foo();
15. }
16. }
What is the result?

A. B
B. B, followed by an Exception.
C. Compilation fails due to an error on line 9.
D. Compilation fails due to an error on line 14.
E. An Exception is thrown with no other output.

Answer: D
Section: All

Explanation/Reference:

QUESTION 10
Given:
try {
     ResourceConnection con = resourceFactory.getConnection();
     Results r = con.query("GET INFO FROM CUSTOMER"); // Linea 86
     info = r.getData(); 88. con.close();
} catch (ResourceException re) {
     errorLog.write(re.getMessage());
}
return info;
Which statement is true if a ResourceException is thrown on line 86?

A. Line 92 will not execute.
B. The connection will not be retrieved in line 85.
C. The resource connection will not be closed on line 88.
D. The enclosing method will throw an exception to its caller.

Answer: C
Section: All

Explanation/Reference:

QUESTION 11
Given:

public class Breaker {
     static String o = "";
     public static void main(String[] args) {
          z: o = o + 2;
          for (int x = 3; x < 8; x++) {
               if (x == 4)
                    break;
               if (x == 6)
                    break z;
              o = o + x;
          }
          System.out.println(o);
     }
}

What is the result?

A. 23
B. 234
C. 235
D. 2345
E. 2357
F. 23457
G. Compilation fails.

Answer: G
Section: All

Explanation/Reference:

QUESTION 12
Given:
     public void go(int x) {
          assert (x > 0); //Line 12
          switch(x) {
          case 2: ;
          default: assert false; //Line 15
          }
     }
     private void go2(int x) { assert (x < 0); } //Line 18   
   
Which statement is true?

A. All of the assert statements are used appropriately.
B. Only the assert statement on line 12 is used appropriately.
C. Only the assert statement on line 15 is used appropriately.
D. Only the assert statement on line 18 is used appropriately.
E. Only the assert statements on lines 12 and 15 are used appropriately.
F. Only the assert statements on lines 12 and 18 are used appropriately.
G. Only the assert statements on lines 15 and 18 are used appropriately.

Answer: G
Section: All

Explanation/Reference:

QUESTION 13
Given:
     public static void main(String[] args) {
          try {
              args = null;
              args[0] = "test";
              System.out.println(args[0]);
          } catch (Exception ex) {
              System.out.println("Exception");
          } catch (NullPointerException npe) {
              System.out.println("NullPointerException");
          }
     }
What is the result?

A. test
B. Exception
C. Compilation fails.
D. NullPointerException

Answer: C
Section: All

Explanation/Reference:

QUESTION 14
Given:
     public static void main(String[] args) {
          for (int i = 0; i <= 10; i++) {
               if (i > 6) break;
          }
          System.out.println(i);
     }
What is the result?

A. 6
B. 7
C. 10
D. 11
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: E
Section: All

Explanation/Reference:

QUESTION 15
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
11. class X { public void foo() { System.out.print("X "); } }
12.
13. public class SubB extends X {
14. public void foo() throws RuntimeException {
15. super.foo();
16. if (true) throw new RuntimeException();
17. System.out.print("B ");
18. }
19. public static void main(String[] args) {
20. new SubB().foo();
21. }
22. }

What is the result?

A. X, followed by an Exception.
B. No output, and an Exception is thrown.
C. Compilation fails due to an error on line 14.
D. Compilation fails due to an error on line 16.
E. Compilation fails due to an error on line 17.
F. X, followed by an Exception, followed by B.

Answer: A
Section: All

Explanation/Reference:
 X Exception in thread "main" java.lang.RuntimeException
     at SubB.foo(SubB.java:5)
     at SubB.main(SubB.java:9)
   
QUESTION 16
Given:

public void testIfA() {
     if (testIfB("True")) { //Linea 12
          System.out.println("True");
     } else {
          System.out.println("Not true");
     }
}
public Boolean testIfB(String str) {
     return Boolean.valueOf(str); //Linea 19
}

What is the result when method testIfA is invoked?

A. True
B. Not true
C. An exception is thrown at runtime.
D. Compilation fails because of an error at line 12.
E. Compilation fails because of an error at line 19.

Answer: A
Section: All

Explanation/Reference:

QUESTION 17
Which can appropriately be thrown by a programmer using Java SE technology to create a desktop application?

A. ClassCastException
B. NullPointerException
C. NoClassDefFoundError
D. NumberFormatException
E. ArrayIndexOutOfBoundsException

Answer: D
Section: All

Explanation/Reference:

QUESTION 18
Which two code fragments are most likely to cause a StackOverflowError? (Choose two.)

A. int []x = {1,2,3,4,5};
   for(int y = 0; y < 6; y++)
        System.out.println(x[y]);
B. static int[] x = {7,6,5,4};
   static { x[1] = 8;
   x[4] = 3; }
C. for(int y = 10; y < 10; y++)
        doStuff(y);
D. void doOne(int x) { doTwo(x); }
   void doTwo(int y) { doThree(y); }
   void doThree(int z) { doTwo(z); }
E. for(int x = 0; x < 1000000000; x++)
        doStuff(x);
F. void counter(int i) { counter(++i); }

Answer: DF
Section: All

Explanation/Reference:

QUESTION 19
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

QUESTION 20
Given:

public class Tahiti {
     Tahiti t;   
     public static void main(String[] args) {
          Tahiti t = new Tahiti();
          Tahiti t2 = t.go(t);
          t2 = null;
          // more code here 11
     }   
     Tahiti go(Tahiti t) {
          Tahiti t1 = new Tahiti();
          Tahiti t2 = new Tahiti();
          t1.t = t2;
          t2.t = t1;
          t.t = t2;
          return t1;
     }
}

When line 11 is reached, how many objects are eligible for garbage collection?

A. 0
B. 1
C. 2
D. 3
E. Compilation fails.

Answer: A
Section: All

Explanation/Reference:

QUESTION 21
Given:

interface Animal {
     void makeNoise();
}
class Horse implements Animal {
     Long weight = 1200L;   
     public void makeNoise() {
          System.out.println("whinny");
     }
}
public class Icelandic extends Horse {
     public void makeNoise() {
          System.out.println("vinny");
     }   
     public static void main(String[] args) {
          Icelandic i1 = new Icelandic();
          Icelandic i2 = new Icelandic();
          Icelandic i3 = new Icelandic();
          i3 = i1;
          i1 = i2;
          i2 = null;
          i3 = i1;
     } //Linea 14
}

When line 14 is reached, how many objects are eligible for the garbage collector?

A. 0
B. 1
C. 2
D. 3
E. 4
F. 6

Answer: E
Section: All

Explanation/Reference:

QUESTION 22
Given:

public class Commander {
     public static void main(String[] args) {
          String myProp = /* insert code here Linea 13 */
          System.out.println(myProp);
     }
}

and the command line: java -Dprop.custom=gobstopper Commander
Which two, placed on line 13, will produce the output gobstopper? (Choose two.)

A. System.load("prop.custom");
B. System.getenv("prop.custom");
C. System.property("prop.custom");
D. System.getProperty("prop.custom");
E. System.getProperties().getProperty("prop.custom");

Answer: DE
Section: All

Explanation/Reference:

QUESTION 23
Given:
public class ItemTest {
     private final int id;
   
     public ItemTest(int id) {
          this.id = id;
     }
   
     public void updateId(int newId) {
          id = newId;
     }
   
     public static void main(String[] args) {
          ItemTest fa = new ItemTest(42);
          fa.updateId(69);
          System.out.println(fa.id);
     }
}
What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. The attribute id in the ItemTest object remains unchanged.
D. The attribute id in the ItemTest object is modified to the new value.
E. A new ItemTest object is created with the preferred value in the id attribute.

Answer: A
Section: All

Explanation/Reference:
The final field ItemTest.id cannot be assigned

QUESTION 24
A developer is creating a class Book, that needs to access class Paper.
The Paper class is deployed in a JAR named myLib.jar.
Which three, taken independently, will allow the developer to use the Paper class while compiling the Book class? (Choose three.)

A. The JAR file is located at $JAVA_HOME/jre/classes/myLib.jar.
B. The JAR file is located at $JAVA_HOME/jre/lib/ext/myLib.jar..
C. The JAR file is located at /foo/myLib.jar and a classpath environment variable is set that includes /foo/myLib.jar/Paper.class.
D. The JAR file is located at /foo/myLib.jar and a classpath environment variable is set that includes /foo/myLib.jar.
E. The JAR file is located at /foo/myLib.jar and the Book class is compiled using javac - cp /foo/myLib.jar/Paper Book.java.
F. The JAR file is located at /foo/myLib.jar and the Book class is compiled using javac -d /foo/myLib.jar Book.java
G. The JAR file is located at /foo/myLib.jar and the Book class is compiled using javac - classpath /foo/myLib.jar Book.java
 
Answer: BDG
Section: All

Explanation/Reference:

QUESTION 25
Given:

public class Yippee {
     public static void main(String[] args) {
          for (int x = 1; x < args.length; x++) {
              System.out.print(args[x] + " ");
          }
     }
}
and two separate command line invocations: java Yippee java Yippee 1 2 3 4

What is the result?

A. No output is produced. 1 2 3
B. No output is produced. 2 3 4
C. No output is produced. 1 2 3 4
D. An exception is thrown at runtime. 1 2 3
E. An exception is thrown at runtime. 2 3 4
F. An exception is thrown at runtime. 1 2 3 4

Answer: B
Section: All

Explanation/Reference:

QUESTION 26
Click the Exhibit button.

class Foo {
     private int x;
     public Foo( int x ){ this.x = x;}
     public void setX( int x ) { this.x = x; }
     public int getX(){ return x;}
}
public class Gamma {
     static Foo fooBar(Foo foo) {
          foo = new Foo(100);
          return foo;
     }   
     public static void main(String[] args) {
          Foo foo = new Foo( 300 );
          System.out.println( foo.getX() + "-");
       
          Foo fooFoo = fooBar(foo);
          System.out.println(foo.getX() + "-");
          System.out.println(fooFoo.getX() + "-");       
          foo = fooBar( fooFoo);
          System.out.println( foo.getX() + "-");
          System.out.println(fooFoo.getX());
     }
}

What is the output of the program shown in the exhibit?

A. 300-100-100-100-100
B. 300-300-100-100-100
C. 300-300-300-100-100
D. 300-300-300-300-100

Answer: B
Section: All

Explanation/Reference:

QUESTION 27
Given classes defined in two different files:

1. package packageA;
2. public class Message {
3. String getText() {
4. return "text";
5. }
6. }

And:

1. package packageB;
2.
3. public class XMLMessage extends packageA.Message {
4. String getText() {
5. return "<msg>text</msg>";
6. }
7.
8. public static void main(String[] args) {
9. System.out.println(new XMLMessage().getText());
10. }
11. }

What is the result of executing XMLMessage.main?

A. text
B. Compilation fails.
C. <msg>text</msg>
D. An exception is thrown at runtime.

Answer: C
Section: All

Explanation/Reference:

QUESTION 28
Given:
interface Fish {
}
class Perch implements Fish {
}
class Walleye extends Perch {
}
class Bluegill {
}
public class Fisherman {
     public static void main(String[] args) {
          Fish f = new Walleye();
          Walleye w = new Walleye();
          Bluegill b = new Bluegill();
          if (f instanceof Perch)
              System.out.print("f-p ");
          if (w instanceof Fish)
              System.out.print("w-f ");
          if (b instanceof Fish)
              System.out.print("b-f ");
     }
}
What is the result?

A. w-f
B. f-p w-f
C. w-f b-f
D. f-p w-f b-f
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: B
Section: All

Explanation/Reference:

QUESTION 29
Given:

1. package com.company.application;
2.
3. public class MainClass {
4. public static void main(String[] args) {
5. }
6. }

And MainClass exists in the /apps/com/company/application directory.
Assume the CLASSPATH environment variable is set to "." (current directory).
Which two java commands entered at the command line will run MainClass? (Choose two.)

A. java MainClass if run from the /apps directory
B. java com.company.application.MainClass if run from the /apps directory
C. java -classpath /apps com.company.application.MainClass if run from any directory
D. java -classpath . MainClass if run from the /apps/com/company/application directory
E. java -classpath /apps/com/company/application:. MainClass if run from the /apps directory
F. java com.company.application.MainClass if run from the /apps/com/company/application directory

Answer: BC
Section: All

Explanation/Reference:

QUESTION 30
Given
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

QUESTION 31
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
