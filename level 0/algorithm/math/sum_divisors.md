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
Perfect Number 
In number theory, a perfect number is a positive integer that is equal to the sum of

* its positive divisors, excluding the number itself. For instance, 6 has divisors 1, 2 and 3

* (excluding itself), and 1 + 2 + 3 = 6, so 6 is a perfect number.
public static boolean isPerfectNumber(int number) {
        int sum = 0;  /* sum of its positive divisors */
        for (int i = 1; i < number; ++i) {
            if (number % i == 0) {
                sum += i;
            }
        }
        return sum == number;
    }


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





    