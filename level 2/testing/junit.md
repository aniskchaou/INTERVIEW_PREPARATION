## 2) What is JUnit?

JUnit is the testing framework, it is used for unit testing of Java code.

1.  JUnit = Java + Unit Testing


## 3) What is unit testing?

The process of testing individual functionality (known as a unit) of the application is called unit testing.


## 4) What is the difference between manual testing and automated testing?

Manual testing is performed by Human, so it is time-consuming and costly. Automated testing is performed by testing tools or programs, so it is fast and less costly.

## 5) Give some disadvantages of manual testing.

Following are some disadvantages of manual testing:

-   The testing is very time consuming and is very tiring.
-   The testing demands a very big investment in the human resources.
-   The testing is less reliable
-   The testing cannot be programmed.

----------


## 7) Is it necessary to write the test case for every logic?

No, we should write the test case only for that logic that can be reasonably broken.

----------

## 8) What are the useful JUnit extensions?

-   JWebUnit
-   XMLUnit
-   Cactus
-   MockObject

----------

## 9) What are the features of JUnit?

-   Opensource
-   Annotation support for test cases
-   Assertion support for checking the expected result
-   Test runner support to execute the test case

## 10) How is the testing of the 'protected' method done?

To test the protected method, the test class is declared in the same package as the target class.

----------


## 12) If the JUnit method's return type is 'string', what will happen?

JUnit test methods are designed to return 'void'. So the execution will fail.

----------

## 13) Is the use of 'main' method possible for unit testing?

Yes

----------

## 14) Is it necessary to write the test class to test every class?

No



## 18) What is the Unit Test Case?

A Unit Test Case is the combination of **input data and expected output result.** It is defined to test the functionality of a unit.

----------

## 19) What is the use of @Test annotation?

The @Test annotation is used to mark the method as the test method.

----------

## 20) What is the test suit?

The test suit allows us to group multiple test cases so that it can be run together. TestSuit is the container class under junit.framework.TestSuite package.


## 22) What are the important JUnit annotations?

The test runner is used to execute the test cases.

-   @Test
-   @BeforeClass
-   @Before
-   @After
-   @AfterClass


## 23) What does Assert class?

Assert class provides methods to test the test cases.


#### Annotations for Junit testing

The Junit 4.x framework is annotation based, so let's see the annotations that can be used while writing the test cases.

**@Test**  annotation specifies that method is the test method.

**@Test(timeout=1000)**  annotation specifies that method will be failed if it takes longer than 1000 milliseconds (1 second).

**@BeforeClass**  annotation specifies that method will be invoked only once, before starting all the tests.

**@Before**  annotation specifies that method will be invoked before each test.

**@After**  annotation specifies that method will be invoked after each test.

**@AfterClass**  annotation specifies that method will be invoked only once, after finishing all the tests.

#### Write the program logic

Let's write the logic to find the maximum number for an array.

    
      public  class Calculation {
    
      public  static  int findMax(int arr[]){
      int max=0;
      for(int i=1;i<arr.length;i++){
      if(max<arr[i])
      max=arr[i];
     }
      return max;
     }

    }

----------

#### Write the test case

Here, we are using JUnit 4, so there is no need to inherit TestCase class. The main testing code is written in the testFindMax() method. But we can also perform some task before and after each test, as you can see in the given program.

  
     public  class TestLogic {
    
      @Test
      public  void testFindMax(){
     assertEquals(4,Calculation.findMax(new  int[]{1,3,4,2}));
     assertEquals(-1,Calculation.findMax(new  int[]{-12,-1,-3,-4,-2}));
     }
     
    }
## Another example of Junit framework
Write the program code

    public class Calculation {  
        //method that returns maximum number  
        public static int findMax(int arr[]){  
            int max=0;  
            for(int i=1;i<arr.length;i++){  
                if(max<arr[i])  
                    max=arr[i];  
            }  
            return max;  
        }  
        //method that returns cube of the given number  
        public static int cube(int n){  
            return n*n*n;  
        }  
        //method that returns reverse words   
        public static String reverseWord(String str){  
      
            StringBuilder result=new StringBuilder();  
            StringTokenizer tokenizer=new StringTokenizer(str," ");  
      
            while(tokenizer.hasMoreTokens()){  
            StringBuilder sb=new StringBuilder();  
            sb.append(tokenizer.nextToken());  
            sb.reverse();  
      
            result.append(sb);  
            result.append(" ");  
            }  
            return result.toString();  
        }  
    }  

Write the test case


    public class TestCase2 {  
      
        @BeforeClass  
        public static void setUpBeforeClass() throws Exception {  
            System.out.println("before class");  
        }  
        @Before  
        public void setUp() throws Exception {  
            System.out.println("before");  
        }  
      
        @Test  
        public void testFindMax(){  
            System.out.println("test case find max");  
            assertEquals(4,Calculation.findMax(new int[]{1,3,4,2}));  
            assertEquals(-2,Calculation.findMax(new int[]{-12,-3,-4,-2}));  
        }  
        @Test  
        public void testCube(){  
            System.out.println("test case cube");  
            assertEquals(27,Calculation.cube(3));  
        }  
        @Test  
        public void testReverseWord(){  
            System.out.println("test case reverse word");  
            assertEquals("ym eman si nahk",Calculation.reverseWord("my name is khan");  
        }  
        @After  
        public void tearDown() throws Exception {  
            System.out.println("after");  
        }  
      
        @AfterClass  
        public static void tearDownAfterClass() throws Exception {  
            System.out.println("after class");  
        }  
      
    }  
