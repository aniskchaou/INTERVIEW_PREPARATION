
## Nombre inverse




   
      int num=123;
      int rest=0;
      int inverse=0;
        while (num!=0) {            
           rest=num%10;
           inverse= (inverse*10)+rest;
            num=num/10;
        }
        System.err.println(""+inverse);



## Nombre premier


   

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

    int num = 156;
    int rem = 0, sum = 0, n;

    n = num;

    while (num > 0) {
        rem = num % 10;
        sum = sum + rem;
        num = num / 10;
    }

    if (n % sum == 0) {
        System.out.println(n + " is a harshad number");
    } else {
        System.out.println(n + " is not a harshad number");
    }

## Pronic number

A number is said to be pronic number if it is a product of two consecutive numbers.

For examples:

    6 = 2 x 3  
    72 = 8 x 9

**Input:**

range(1, 101)

**Output:**

Pronic numbers between 1 and 100: 2 6 12 20 30 42 56 72 90

     public static boolean isPronicNumber(int num) {
        boolean flag = false;

        for (int j = 1; j <= num; j++) {
           
            if ((j * (j + 1)) == num) {
                flag = true;
                break;
            }
        }
        return flag;
    }

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

     public  static  void main(String[] args) {
     int x, y, t;  
      t = x;
      x = y;
      y = t;
      System.out.println("After swapping: "+x +" " + y);
     
      }

## Program to swap two numbers without using the third variable



**X= 25** (First number), **Y= 23** (second number)
Swapping Logic:

    X = X + Y = 25 +23 = 48
    Y = X - Y = 48 - 23 = 25
    X = X -Y = 48 - 25 = 23

and the numbers are swapped as X =23 and Y =25. 

  

                int x = 25;
                int y = 23;
                x = x + y;
                y = x - y;
                x = x - y;
                System.out.println("After swapping: " + x + " " + y);

## Palindrome number
Write a java program to check palindrome number.

**Input:**  329

**Output:**  not palindrome number

**Input:**  12321

**Output:**  palindrome number

      int r, sum = 0, temp;
            int n = 454;
    
            temp = n;
            while (n > 0) {
                r = n % 10; 
                sum = (sum * 10) + r;
                n = n / 10;
            }
            if (temp == sum) {
                System.out.println("palindrome number ");
            } else {
                System.out.println("not palindrome");
            }

## Armstrong number



**Input:**  153

**Output:**  Armstrong number

**Input:**  22

**Output:**  not Armstrong number

      int c = 0, a;
    int n = 153;
    
    while (n > 0) {
        a = n % 10;
        n = n / 10;
        c = c + (a * a * a);
    }
    if (n == c) {
        System.out.println("armstrong number");
    } else {
        System.out.println("Not armstrong number");
    }


