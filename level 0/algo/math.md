
## Nombre inverse

**idea**

    nombre=123
    nombre_inverse=0
    
    tant que (nombre>0)
         nombre_inverse = nombre_inverse*10
         nombre_inverse = nombre % 10
         nombre = nombre / 10

**algo** 

    static void reverse(int N){

        int reverseNumber = 0;
        while(N>0){
            reverseNumber *= 10;
            reverseNumber += N%10;
            N = N/10;
        }
        System.out.println(reverseNumber);
    }



## Nombre premier

**idea**

    est_premier=1
    pour i=2 jusqua n
         si n mod i = 0 alors
             est_premier=0
             sortir
    
    si est_premier==1 alors
      afficher(n)

**algo**
   

     static void naiveMethod(int n){
           
            boolean isPrime = true;
            for (int i = 2; i <n ; i++) {
                if(n%i==0) {
                    isPrime = false;
                    break;
                }
            }
            if(isPrime)
                System.out.println(n);
        
        }

## nombre de nombres premier

    public class FirstNPrimeNumbers {
    
        static void printPrimeNos(int N){
    
            int number = 2;
            int primeCount = 0;
    
            while(primeCount< N){
                if(isPrime(number)){
                    System.out.print(number + " ");
                    primeCount++;
                }
                number++;
            }
             System.out.print("prime count "+primeCount);
            
        }
    
        static boolean isPrime(int n){
            for (int i = 2; i <=Math.sqrt(n) ; i++) {
                if(n%i==0)
                    return false;
            }
            return true;
        }
    
        public static void main(String[] args) {
            int N = 2;
            printPrimeNos(N);
        }
    }

## Factoriel
**non recursive**
    
            int num = 10;
            long factorial = 1;
            for(int i = 1; i <= num; ++i)
            {
                // factorial = factorial * i;
                factorial *= i;
            }
    
 **recursive** 
   

     public int factorial(int num)
            {
                /* local variable declaration */
                int result;
                if (num == 1)
                {
                    return 1;
                }
                else
                {
                    result = factorial(num - 1) * num;
                    return result;
                }
            }

  

## series de fibinacci
**idea**

    fonction fib(nombre)
     si n<2 lors
       retourner nombre
     sinon 
     retourner fib(nombre-2) + fib(nombre-1)  

**algo**
  

     public static int printFibonacci(int n) {
            if (n < 2) {
                return (n);
            }
            return (printFibonacci(n - 2) + printFibonacci(n - 1));
        }

## Nombre pair impair

**idea**

    si x mod 2 =0 alors
    affiche(pair)
    sinon
    affiche(impair)

**algo**

            int x=44;
            if (x%2==0) {
                System.err.println("pair");
            } else {
                System.err.println("impair");
            }

## ugly number

**algo**
 

       public class UglyNumber {
            public static boolean isUgly(int num) {
           
            if(num==0) return false;
            if(num==1) return true;
         
            if(num%2==0){
                num=num/2;
                return isUgly(num);
            }
         
            if(num%3==0){
                num=num/3;
                return isUgly(num);
            }
         
            if(num%5==0){
                num=num/5;
                return isUgly(num);
            }
         
            return false;
        }
            
           
        }

## Disarium number

**Input:**

num = 175

**Output:**

11 + 72 + 53 = 1 + 49 + 125 = 175
175 is a disarium number

    public  static  void main(String[] args) {
    
    int a=175;
    int x=String.valueOf(a).length();;
    int reverseNumber=0;
    int sum=0;
    
    while(a>0)
    {
    reverseNumber = a%10; 
    a = a/10;  
    sum+=Math.pow(reverseNumber, x); 
    x--; 
    } 
    System.out.print(sum); 
    }

## Happy number

**Input:**

num = 82

**Output:**

82 + 22 = 68
62 + 82 = 100
12 + 02 + 02 = 1
82 is a happy number number

    1.  public  static  int isHappyNumber(int num){
    2.  int rem = 0, sum = 0;
    
    4.  //Calculates the sum of squares of digits
    5.  while(num > 0){
    6.  rem = num%10;
    7.  sum = sum + (rem*rem);
    8.  num = num/10;
    9.  }
    10.  return sum;
    11.  }
    
    13.  public  static  void main(String[] args) {
    14.  int num = 82;
    15.  int result = num;
    
    17.  while(result != 1 && result != 4){
    18.  result = isHappyNumber(result);
    19.  }
    
    21.  //Happy number always ends with 1
    22.  if(result == 1)
    23.  System.out.println(num + " is a happy number");
    24.  //Unhappy number ends in a cycle of repeating numbers which contains 4
    25.  else  if(result == 4)
    26.  System.out.println(num + " is not a happy number");
    27.  }

## Harshad number

A number is said to be the Harshad number if it is divisible by the sum of its digit.

**Input:**

num = 156

**Output:**

156 is a Harshad number

    1.  public  static  void main(String[] args) {
    2.  int num = 156;
    3.  int rem = 0, sum = 0, n;
    
    5.  //Make a copy of num and store it in variable n
    6.  n = num;
    
    8.  //Calculates sum of digits
    9.  while(num > 0){
    10.  rem = num%10;
    11.  sum = sum + rem;
    12.  num = num/10;
    13.  }
    
    15.  //Checks whether number is divisible by sum of digits
    16.  if(n%sum == 0)
    17.  System.out.println(n + " is a harshad number");
    18.  else
    19.  System.out.println(n + " is not a harshad number");
    20.  }

## Pronic number

A number is said to be pronic number if it is a product of two consecutive numbers.

For examples:

6 = 2 x 3  
72 = 8 x 9

**Input:**

range(1, 101)

**Output:**

Pronic numbers between 1 and 100: 2 6 12 20 30 42 56 72 90

    1.  public  static  boolean isPronicNumber(int num){
    2.  boolean flag = false;
    
    4.  for(int j = 1; j <= num; j++){
    5.  //Checks for pronic number by multiplying consecutive numbers
    6.  if((j*(j+1)) == num){
    7.  flag = true;
    8.  break;
    9.  }
    10.  }
    11.  return flag;
    12.  }


## Program to determine whether a given number is a Deficient number

The deficient number can be defined as the number for which the sum of the proper divisors is lesser than the number itself.

For example, the number 21 with its proper divisors (1, 3 and 7) has sum (11) lesser than itself.

    1.  static  int divsum(int n)
    2.  {
    3.  int sum = 0;
    4.  for (int i = 1; i <= (Math.sqrt(n)); i++) {
    5.  if (n % i == 0) {
    
    7.  if (n / i == i) {
    8.  sum = sum + i;
    9.  }
    10.  else
    11.  {
    12.  sum = sum + i;
    13.  sum = sum + (n / i);
    14.  }
    15.  }
    16.  }
    
    18.  return sum;
    19.  }
    
    22.  static  boolean isDef(int n)
    23.  {
    24.  return (divsum(n) < (2 * n));
    25.  }
    
    27.  public  static  void main(String args[])
    28.  {
    29.  System.out.println("Enter the number?");
    30.  Scanner sc = new Scanner(System.in);
    31.  int n = sc.nextInt();
    32.  if (isDef(n))
    33.  System.out.println("The number is deficient.");
    34.  else
    35.  System.out.println("The number is not deficient");
    36.  }

## Program to determine whether a given number is an abundant number

The abundant number can be called as an excessive number and defined as the number for which the sum of its proper divisors is greater than the number itself.

A first abundant number is the integer 12 having the sum (16) of its proper divisors (1, 2, 3, 4, 6) which is greater than itself (12).

**Examples:**  12, 18, 20, 24, 30, 36


    1.  public  int getSum(int n)
    2.  {
    3.  int sum = 0;
    4.  for (int i=1; i<=Math.sqrt(n); i++)
    5.  {
    6.  if (n%i==0)
    7.  {
    8.  if (n/i == i)
    9.  sum = sum + i;
    10.  else
    11.  {
    12.  sum = sum + i;
    13.  sum = sum + (n / i);
    14.  }
    15.  }
    16.  }
    17.  sum = sum - n;
    18.  return sum;
    19.  }
    20.  public  boolean checkAbundant(int n)
    21.  {
    22.  return (getSum(n) > n);
    23.  }

## Program to print all Kaprekar numbers between 1 to 100



**Examples:**

45 =  (45)2 = 2025 =20 + 25 -45
1 = 12 = 01 = 0 + 1 = 1
## Program to print the average of n numbers

The average is the outcome from the sum of the numbers divided by the count of the numbers being averaged.

**For example:**  1,2,3,4,5

Number of all elements = 5

Sum of all elements = 1+2+3+4+5 =15

Average = Sum of all elements / number of all elements = 15/5 =3

Average =3

    1.  public  static  void main(String[] args)
    2.  {
    3.  int n, count = 1;
    4.  float xF, averageF, sumF = 0;
    5.  Scanner sc = new Scanner(System.in);
    6.  System.out.println("Enter the value of n");
    7.  n = sc.nextInt();
    8.  while (count <= n)
    9.  {
    10.  System.out.println("Enter the "+count+" number?");
    11.  xF = sc.nextInt();
    12.  sumF += xF;
    13.  ++count;
    14.  }
    15.  averageF = sumF/n;
    16.  System.out.println("The Average is"+averageF);
    17.  }

## Program to print the permutation (nPr) of the given number

### Permutation

It is an ordered-arrangement/combination of a set of things or collection of objects.

For example, we have a set of letters A, B, and C.....describing permutations as n distinct objects taken r at a time.

**Permutation of a list of n elements:**

1.  n!= n (n-1)(n-2)(n-3)....3.2.1
2.  nPr = n!/ (n-r)! =n(n-1) (n-2)(n-3).....(n-r+1)
**implementation**

   

     1.  public  static  void main(String[] args)
        2.  {
        3.  int n, r, per, fact1, fact2;
        4.  Scanner sc = new Scanner(System.in);
        5.  System.out.println("Enter the Value of n and r?");
        6.  n = sc.nextInt();
        7.  r = sc.nextInt();
        8.  fact1 = n;
        9.  for (int i = n - 1; i >= 1; i--)
        10.  {
        11.  fact1 = fact1 * i;
        12.  }
        13.  int number;
        14.  number = n - r;
        15.  fact2 = number;
        16.  for (int i = number - 1; i >= 1; i--)
        17.  {
        18.  fact2 = fact2 * i;
        19.  }
        20.  per = fact1 / fact2;
        21.  System.out.println("nPr = "+per);
        22.  }

## Program to swap two numbers

This program is to swap/exchange two numbers by using a variable.

    1.  public  static  void main(String[] args) {
    2.  int x, y, t;// x and y are to swap
    3.  Scanner sc = new Scanner(System.in);
    4.  System.out.println("Enter the value of X and Y");
    5.  x = sc.nextInt();
    6.  y = sc.nextInt();
    7.  System.out.println("before swapping numbers: "+x +" "+ y);
    8.  /*swapping */
    9.  t = x;
    10.  x = y;
    11.  y = t;
    12.  System.out.println("After swapping: "+x +" " + y);
    13.  System.out.println( );
    14.  }

## Program to swap two numbers without using the third variable

This program is to swap/exchange two numbers without using the third number in the way as given below:

**Example:**  Suppose, there are two numbers 25 and 23.

Let

**X= 25** (First number), **Y= 23** (second number)
Swapping Logic:
X = X + Y = 25 +23 = 48
Y = X - Y = 48 - 23 = 25
X = X -Y = 48 - 25 = 23
and the numbers are swapped as X =23 and Y =25. 

    1.  public  static  void main(String a[])
    2.  {
    3.  System.out.println("Enter the value of x and y");
    4.  Scanner sc = new Scanner(System.in);
    5.  /*Define variables*/
    6.  int x = sc.nextInt();
    7.  int y = sc.nextInt();
    8.  System.out.println("before swapping numbers: "+x +" "+ y);
    9.  /*Swapping*/
    10.  x = x + y;
    11.  y = x - y;
    12.  x = x - y;
    13.  System.out.println("After swapping: "+x +" " + y);
    14.  }

## Palindrome number
Write a java program to check palindrome number.

**Input:**  329

**Output:**  not palindrome number

**Input:**  12321

**Output:**  palindrome number

    1.  public  static  void main(String args[]){
    2.  int r,sum=0,temp;
    3.  int n=454;//It is the number variable to be checked for palindrome
    
    5.  temp=n;
    6.  while(n>0){
    7.  r=n%10; //getting remainder
    8.  sum=(sum*10)+r;
    9.  n=n/10;
    10.  }
    11.  if(temp==sum)
    12.  System.out.println("palindrome number ");
    13.  else
    14.  System.out.println("not palindrome");
    15.  }

## Armstrong number

Write a java program to check Armstrong number.

**Input:**  153

**Output:**  Armstrong number

**Input:**  22

**Output:**  not Armstrong number

    1.  public  static  void main(String[] args) {
    2.  int c=0,a,temp;
    3.  int n=153;//It is the number to check armstrong
    4.  temp=n;
    5.  while(n>0)
    6.  {
    7.  a=n%10;
    8.  n=n/10;
    9.  c=c+(a*a*a);
    10.  }
    11.  if(temp==c)
    12.  System.out.println("armstrong number");
    13.  else
    14.  System.out.println("Not armstrong number");
    15.  }
