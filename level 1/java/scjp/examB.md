QUESTION 1
Given:
22. StringBuilder sb1 = new StringBuilder("123");
23. String s1 = "123";
24. // insert code here
25. System.out.println(sb1 + " " + s1);
Which code fragment, inserted at line 24, outputs "123abc 123abc"?

A. sb1.append("abc"); s1.append("abc");
B. sb1.append("abc"); s1.concat("abc");
C. sb1.concat("abc"); s1.append("abc");
D. sb1.concat("abc"); s1.concat("abc");
E. sb1.append("abc"); s1 = s1.concat("abc");
F. sb1.concat("abc"); s1 = s1.concat("abc");
G. sb1.append("abc"); s1 = s1 + s1.concat("abc");
H. sb1.concat("abc"); s1 = s1 + s1.concat("abc");

Answer: E
Section: All

Explanation/Reference:

QUESTION 2
Click the Exhibit button.
Which code, inserted at line 14, will allow this class to correctly serialize and deserialize?

1. import java.io.*;
2. public class Foo implements Serializable {
3. public int x, y;
4. public Foo(int x, int y){
5. this.x = x; this.y = y;
6. }
7.
8. private void writeObject(ObjectOutputStream s)
9. throws IOException{
10. s.writeInt(x); s.writeInt(y);
11. }
12.
13. private void readObject(ObjectInputStream s)
14. throws IOException, ClassNotFoundException {
15. //insert code here
16. }
17. }

A. s.defaultReadObject();
B. this = s.defaultReadObject();
C. y = s.readInt(); x = s.readInt();
D. x = s.readInt(); y = s.readInt();

Answer: D
Section: All

Explanation/Reference:

QUESTION 3
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

QUESTION 4
Given:
11. public class Test {
12. public static void main(String [] args) {
13. int x = 5;
14. boolean b1 = true;
15. boolean b2 = false;
16.
17. if ((x == 4) && !b2 )
18. System.out.print("1 ");
19. System.out.print("2 ");
20. if ((b2 = true) && b1 )
21. System.out.print("3 ");
22. }
23. }

What is the result?

A. 2
B. 3
C. 12
D. 23
E. 123
F. Compilation fails.
G. An exception is thrown at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 5
Given:
interface Foo {}
class Alpha implements Foo {}
class Beta extends Alpha {}
class Delta extends Beta {
     public static void main( String[] args ) {
          Beta x = new Beta();
16. //insert code here 16
     }
}

Which code, inserted at line 16, will cause a java.lang.ClassCastException?

A. Alpha a = x;
B. Foo f = (Delta)x;
C. Foo f = (Alpha)x;
D. Beta b = (Beta)(Alpha)x;

Answer: B
Section: All

Explanation/Reference:

QUESTION 6
Given:
     public void go() {
          String o = "";
          z:
               for(int x = 0; x < 3; x++) {
                    for(int y = 0; y < 2; y++) {
                          if(x==1) break;
                          if(x==2 && y==1) break z;
                        o = o + x + y;
                   }
              }
          System.out.println(o);
     }

What is the result when the go() method is invoked?

A. 00
B. 0001
C. 000120
D. 00012021
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: C
Section: All

Explanation/Reference:

QUESTION 7
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

QUESTION 8
Given:
try {
 //some code here line 34
} catch (NullPointerException e1) {
     System.out.print("a");
} catch (Exception e2) {
     System.out.print("b");
} finally {
     System.out.print("c");
}

If some sort of exception is thrown at line 34, which output is possible?

A. a
B. b
C. c
D. ac
E. abc

Answer: D
Section: All

Explanation/Reference:

QUESTION 9
Given:
 //some code here line 31
try {
 //some code here line 33
} catch (NullPointerException e1) {
 //some code here line 35
} finally {
 //some code here line 37
}

Under which three circumstances will the code on line 37 be executed? (Choose three.)

A. The instance gets garbage collected.
B. The code on line 33 throws an exception.
C. The code on line 35 throws an exception.
D. The code on line 31 throws an exception.
E. The code on line 33 executes successfully.

Answer: BCE
Section: All

Explanation/Reference:

QUESTION 10
Given:
int x = 0;
int y = 10;
do {
     y--;
     ++x;
} while (x < 5);
System.out.print(x + "," + y);

What is the result?

A. 5,6
B. 5,5
C. 6,5
D. 6,6

Answer: B
Section: All

Explanation/Reference:

QUESTION 11
Given:
public class Donkey2 {
     public static void main(String[] args) {
          boolean assertsOn = true;
          assert (assertsOn) : assertsOn = true;
          if(assertsOn) {
              System.out.println("assert is on");
          }
     }
}

If class Donkey is invoked twice, the first time without assertions enabled, and the second time with assertions enabled, what are the results?

A. no output
B. no output assert is on
C. assert is on
D. no output An AssertionError is thrown.
E. assert is on An AssertionError is thrown.
 
Answer: C
Section: All

Explanation/Reference:

QUESTION 12
Click the Exhibit button.
Given:
public void method() {
     A a = new A();
     a.method1();
}

Which statement is true if a TestException is thrown on line 3 of class B?

1. public class A{
2. public void method1() {
3. try {
4. B b = new B();
5. b.method2();
6. //more code here
7. } catch (TestException te){
8. throw new RuntimeException(te);
9. }
10. }
11. }

1. public class B{
2. public void method2() throws TestException {
3. //more code here
4. }
5. }

1. class TestException extends Exception {
2. }

A. Line 33 must be called within a try block.
B. The exception thrown by method1 in class A is not required to be caught.
C. The method declared on line 31 must be declared to throw a RuntimeException.
D. On line 5 of class A, the call to method2 of class B does not need to be placed in a try/catch block.

Answer: B
Section: All

Explanation/Reference:

QUESTION 13
Given:
Float pi = new Float(3.14f);
if (pi > 3) {
     System.out.print("pi is bigger than 3. ");
}
else {
     System.out.print("pi is not bigger than 3. ");
}
finally {
     System.out.println("Have a nice day.");
}

What is the result?

A. Compilation fails.
B. pi is bigger than 3.
C. An exception occurs at runtime.
D. pi is bigger than 3. Have a nice day.
E. pi is not bigger than 3. Have a nice day.

Answer: A
Section: All

Explanation/Reference:

QUESTION 14
Given:
1. public class Boxer1{
2. Integer i;
3. int x;
4. public Boxer1(int y) {
5. x = i+y;
6. System.out.println(x);
7. }
8. public static void main(String[] args) {
9. new Boxer1(new Integer(4));
10. }
11. }

What is the result?

A. The value "4" is printed at the command line.
B. Compilation fails because of an error in line 5.
C. Compilation fails because of an error in line 9.
D. A NullPointerException occurs at runtime.
E. A NumberFormatException occurs at runtime.
F. An IllegalStateException occurs at runtime.

Answer: D
Section: All

Explanation/Reference:

QUESTION 15
Given:
1. public class Person {
2. private String name;
3. public Person(String name) { this.name = name; }
4. public boolean equals(Person p) {
5. return p.name.equals(this.name);
6. }
7. }

Which statement is true?

A. The equals method does NOT properly override the Object.equals method.
B. Compilation fails because the private attribute p.name cannot be accessed in line 5.
C. To work correctly with hash-based data structures, this class must also implement the hashCode
   method.
D. When adding Person objects to a java.util.Set collection, the equals method in line 4 will prevent
   duplicates.
 
Answer: A
Section: All

Explanation/Reference:

QUESTION 16
Which two statements are true about the hashCode method? (Choose two.)

A. The hashCode method for a given class can be used to test for object equality and object inequality for that class.
B. The hashCode method is used by the java.util.SortedSet collection class to order the elements within  that set.
C. The hashCode method for a given class can be used to test for object inequality, but NOT object
   equality, for that class.
D. The only important characteristic of the values returned by a hashCode method is that the distribution of  values must follow a Gaussian distribution.
E. The hashCode method is used by the java.util.HashSet collection class to group the elements within  that set into hash buckets for swift retrieval.
 
Answer: CE
Section: All

Explanation/Reference:

QUESTION 17
Given:
1. public class Score implements Comparable<Score> {
2. private int wins, losses;
3. public Score(int w, int l) { wins = w; losses = l; }
4. public int getWins() { return wins; }
5. public int getLosses() { return losses; }
6. public String toString() {
7. return "<" + wins + "," + losses + ">";
8. }
9. // insert code here
10. }
11.

Which method will complete this class?

A. public int compareTo(Object o){/*more code here*/}
B. public int compareTo(Score other){/*more code here*/}
C. public int compare(Score s1,Score s2){/*more code here*/}
D. public int compare(Object o1,Object o2){/*more code here*/}

Answer: B
Section: All

Explanation/Reference:

QUESTION 18
Given a pre-generics implementation of a method:
11. public static int sum(List list) {
12. int sum = 0;
13. for ( Iterator iter = list.iterator(); iter.hasNext(); ) {
14. int i = ((Integer)iter.next()).intValue();
15. sum += i;
16. }
17. return sum;
18. }

What three changes allow the class to be used with generics and avoid an unchecked warning? (Choose three.)

A. Remove line 14.
B. Replace line 14 with "int i = iter.next();".
C. Replace line 13 with "for (int i : intList) {".
D. Replace line 13 with "for (Iterator iter : intList) {".
E. Replace the method declaration with "sum(List<int> intList)".
F. Replace the method declaration with "sum(List<Integer> intList)".

Answer: ACF
Section: All

Explanation/Reference:

QUESTION 19
Given:
23. Object [] myObjects = {
24. new Integer(12),
25. new String("foo"),
26. new Integer(5),
27. new Boolean(true)
28. };
29. Arrays.sort(myObjects);
30. for(int i=0; i<myObjects.length; i++) {
31. System.out.print(myObjects[i].toString());
32. System.out.print(" ");
33. }

What is the result?

A. Compilation fails due to an error in line 23.
B. Compilation fails due to an error in line 29.
C. A ClassCastException occurs in line 29.
D. A ClassCastException occurs in line 31.
E. The value of all four objects prints in natural order.

Answer: C
Section: All

Explanation/Reference:

QUESTION 20
Given a class Repetition:
1. package utils;
2.
3. public class Repetition {
4. public static String twice(String s) { return s + s; }
5. }
and given another class Demo:
1. public class Demo {
2. public static void main(String[] args) {
3. System.out.println(twice("pizza"));
4. }
5. }

Which code should be inserted at line 1 of Demo.java to compile and run Demo to print "pizzapizza"?

A. import utils.*;
B. static import utils.*;
C. import utils.Repetition.*;
D. static import utils.Repetition.*;
E. import utils.Repetition.twice();
F. import static utils.Repetition.twice;
G. static import utils.Repetition.twice;

Answer: F
Section: All

Explanation/Reference:

QUESTION 21
A UNIX user named Bob wants to replace his chess program with a new one, but he is not sure where the old one is installed. Bob is currently able to run a Java chess program starting from his home directory / home/bob using the command:

   java -classpath /test:/home/bob/downloads/*.jar games.Chess
 
Bob's CLASSPATH is set (at login time) to:

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

QUESTION 22
Given the following directory structure:
   bigProject
   |--source
   | |--Utils.java
   |
   |--classes
   |--
And the following command line invocation:
   javac -d classes source/Utils.java
Assume the current directory is bigProject, what is the result?

A. If the compile is successful, Utils.class is added to the source directory.
B. The compiler returns an invalid flag error.
C. If the compile is successful, Utils.class is added to the classes directory.
D. If the compile is successful, Utils.class is added to the bigProject directory.

Answer: C
Section: All

Explanation/Reference:

QUESTION 23
Given:
1. package com.company.application;
2.
3. public class MainClass {
4. public static void main(String[] args) {}
5. }
And MainClass exists in the /apps/com/company/application directory. Assume the CLASSPATH environment variable is set to "." (current directory).

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

QUESTION 24
Which statement is true?

A. A class's finalize() method CANNOT be invoked explicitly.
B. super.finalize() is called implicitly by any overriding finalize() method.
C. The finalize() method for a given object is called no more than once by the garbage collector.
D. The order in which finalize() is called on two objects is based on the order in which the two objects became finalizable.
 
Answer: C
Section: All

Explanation/Reference:

QUESTION 25
Given:
1. public class Batman {
2. int squares = 81;
3. public static void main(String[] args) {
4. new Batman().go();
5. }
6. void go() {
7. incr(++squares);
8. System.out.println(squares);
9. }
10. void incr(int squares) { squares += 10; }
11. }

What is the result?

A. 81
B. 82
C. 91
D. 92
E. Compilation fails.
F. An exception is thrown at runtime.

Answer: B
Section: All

Explanation/Reference:

QUESTION 26
Given:
public class Yippee {
     public static void main(String [] args) {
          for(int x = 1; x < args.length; x++) {
              System.out.print(args[x] + " ");
          }
     }
}
and two separate command line invocations:
  java Yippee
  java Yippee 1 2 3 4

What is the result?

A. No output is produced.  123
B. No output is produced.  234
C. No output is produced.  1234
D. An exception is thrown at runtime.  123
E. An exception is thrown at runtime.  234
F. An exception is thrown at runtime.  1234
 
Answer: B
Section: All

Explanation/Reference:

QUESTION 27
Given:
1. public class Pass {
2. public static void main(String [] args) {
3. int x = 5;
4. Pass p = new Pass();
5. p.doStuff(x);
6. System.out.print(" main x = " + x);
7. }
8.
9. void doStuff(int x) {
10. System.out.print(" doStuff x = " + x++);
11. }
12. }

What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. doStuff x = 6 main x = 6
D. doStuff x = 5 main x = 5
E. doStuff x = 5 main x = 6
F. doStuff x = 6 main x = 5

Answer: D
Section: All

Explanation/Reference:

QUESTION 28
Given:
1. interface Animal { void makeNoise(); }
2. class Horse implements Animal {
3. Long weight = 1200L;
4. public void makeNoise() { System.out.println("whinny"); }
5. }
6.
7. public class Icelandic extends Horse {
8. public void makeNoise() { System.out.println("vinny"); }
9. public static void main(String[] args) {
10. Icelandic i1 = new Icelandic();
11. Icelandic i2 = new Icelandic();
12. Icelandic i3 = new Icelandic();
13. i3 = i1; i1 = i2; i2 = null; i3 = i1;
14. }
15. }

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

QUESTION 29
Given two files, GrizzlyBear.java and Salmon.java:
1. package animals.mammals;
2.
3. public class GrizzlyBear extends Bear {
4. void hunt() {
5. Salmon s = findSalmon();
6. s.consume();
7. }
8. }

1. package animals.fish;
2.
3. public class Salmon extends Fish {
4. public void consume() { /* do stuff */ }
5. }
If both classes are in the correct directories for their packages, and the Mammal class correctly defines the findSalmon() method, which change allows this code to compile?

A. add import animals.mammals.*; at line 2 in Salmon.java
B. add import animals.fish.*; at line 2 in GrizzlyBear.java
C. add import animals.fish.Salmon.*; at line 2 in GrizzlyBear.java
D. add import animals.mammals.GrizzlyBear.*; at line 2 in Salmon.java B

Answer: B
Section: All

Explanation/Reference:

QUESTION 30
Given:

String[] elements = { "for", "tea", "too" };
String first = (elements.length > 0) ? elements[0] : null;

What is the result?

A. Compilation fails.
B. An exception is thrown at runtime.
C. The variable first is set to null.
D. The variable first is set to elements[0].

Answer: D
Section: All

Explanation/Reference:

QUESTION 31



Answer:



Section: All

Explanation/Reference:
Compilation of the first statement succeeds, but compilation fails due to an error in the second statement.
Compilation fails due to an error in the first statement
Compilation succeds.
Compilation succeds.

QUESTION 32



Answer:


Section: All

Explanation/Reference:

