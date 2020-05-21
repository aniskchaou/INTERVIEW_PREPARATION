
## Factorial
**recurisive version:**


  

      int f(int a1)    
        {
           if (a1 <= 1)               
              return 1;                
           else                      
              return a1 * f(a1 - 1);  
        }

**Non-recursive version:**


    int fact(int n)
    {
     int i;
     int prod = 1;
     
     for (int i = 1; i <= n; i++) 
      prod *= i; 
      
       return prod; 
    }

## HeadingHeading Write a program to print all permutations of a given string


    Below are the permutations of string ABC.  
    ABC ACB BAC BCA CBA CAB
    
        // Java program to print all permutations of a 
        // given string. 
        public class Permutation 
        { 
            public static void main(String[] args) 
            { 
                String str = "ABC"; 
                int n = str.length(); 
                Permutation permutation = new Permutation(); 
                permutation.permute(str, 0, n-1); 
            } 
          
          
            private void permute(String str, int l, int r) 
            { 
                if (l == r) 
                    System.out.println(str); 
                else
                { 
                    for (int i = l; i <= r; i++) 
                    { 
                        str = swap(str,l,i); 
                        permute(str, l+1, r); 
                        str = swap(str,l,i); 
                    } 
                } 
            } 
          
           
            public String swap(String a, int i, int j) 
            { 
                char temp; 
                char[] charArray = a.toCharArray(); 
                temp = charArray[i] ; 
                charArray[i] = charArray[j]; 
                charArray[j] = temp; 
                return String.valueOf(charArray); 
            } 
          
        }

 

## Greatest Common Divisor



      int gcd(int a, int b)    
        {   
           int remainder = a % b;   
           if (remaider == 0)  
              return b; 
           else 
              return gcd(b, remainder); 
        }



## How to Find Square Root of a Number in Java

 

       public static float root(int number) {
            float root = 0.0f;
            float square = root;
            while (square < number) {
              root++;
              square = root * root;
            }
            return root;
          }

Output

    4
    square root: 2.0
    9
    square root: 3.0
    16
    square root: 4.0
    25
    square root: 5.0
    26
    square root: 6.0

  
  

## HeadingJava Program to print Prime numbers in Java

   

      public class PrimeNumberExample {
        
            public static void main(String args[]) {
        
                int limit = 100;
        
                for (int number = 2; number <= limit; number++) {
                    if (isPrime(number)) {
                        System.out.println(number);
                    }
                }
        
            }
        
            public static boolean isPrime(int number) {
                for (int i = 2; i < number; i++) {
                    if (number % i == 0) {
                        return false;  //number is divisible so its not prime_  
                    }
                }
                return true;  //number is prime now_  
            }
        }

  
**Output:**  

    Enter the number till which prime number to be printed:  
    20  
    Printing prime number from  1  to  20  
    2  
    3  
    5  
    7  
    11  
    13  
    17  
    19

## How to print Floyd's Triangle


     public static void printFloydTriangle(int rows) {
                int number = 1;
                
         
                for (int i = 1; i <= rows; i++) {
                    
                    for (int j = 1; j <= i; j++) {
                        System.out.print(number + " ");
                        number++;
                    }
         
                    System.out.println();
                }
            }

 
**Output**

    Enter the number of rows of Floyd's triangle, you want to display
    5
    Floyd's triangle of 5 rows is :
    1
    2 3
    4 5 6
    7 8 9 10
    11 12 13 14 15

 



# How to print Pascal Triangle in Java

    public static void printPascalTriangle(int rows) {
                
                for (int i = 0; i < rows; i++) {
                    int number = 1;
                    System.out.printf("%" + (rows - i) * 2 + "s", "");
                    
                    for (int j = 0; j <= i; j++) {
                        System.out.printf("%4d", number);
                        number = number * (i - j) / (j + 1);
        
                    }
                    
                    System.out.println();
                }
            }

Output

   
               1
             1   1
           1   2   1
         1   3   3   1
    
    



## Heading How to Print Pyramid Pattern in Java?


    public static void drawPyramidPattern(int rows) {
    
            for (int i = 0; i < rows; i++) {
               
                // '  '
                int nombreespace = rows - i;
                for (int j = 0; j < nombreespace; j++) {
                    System.out.print(" ");
                }
    
                // *
                for (int k = 0; k <= i; k++) {
                    System.out.print("* ");
                }
    
                System.out.println();
            }




## Count Number of Digits in an Integer using while loop


  

    public static void main(String[] args) {
    
            int count = 0, num = 3452;
    
            while (num != 0) {
                num /= 10;
                ++count;
            }
    
            System.out.println("Number of digits: " + count);
    
        }

When you run the program, the output will be:

    Number of digits: 4


## permutation

     public static void main(String []args){
        permutation("123");
     }
     
    public static void permutation(String str) { 
    permutation("", str); 
     }

    private static void permutation(String prefix, String str) {
    int n = str.length();

     if (n == 0) 
     System.out.println(prefix);
     else {
        for (int i = 0; i < n; i++)
            permutation(prefix + str.charAt(i), 
            str.substring(0, i) + str.substring(i+1, n));
      }
    }




