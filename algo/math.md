math
nombre inverse

    public class ReverseNumberLoop {
    
        static void reverse(int N){
    
            System.out.println("Given Number: " +  N);
            int reverseNumber = 0;
    
            while(N>0){
                reverseNumber *= 10;
                reverseNumber += N%10;
                N = N/10;
            }
            System.out.println("Reversed Number: " + reverseNumber);
        }
    
        public static void main(String[] args) {
            int N = 1234;
            reverse(N);
            N = 1020;
            reverse(N);
        }
    }

nombre premier

    static void naiveMethod(int n){
        System.out.print("O(N) Solution : ");
        boolean isPrime = true;
        for (int i = 2; i <n ; i++) {
            if(n%i==0) {
                System.out.println("Number " + n +" is not a prime no");
                isPrime = false;
                break;
            }
        }
        if(isPrime)
            System.out.println("Number " + n +" is a prime no");
    
        //Time Complexity: O(N)
    }

nombre de nombres premier

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
factoriel

    public class Factorial {
    
        public static void main(String[] args) {
    
            int num = 10;
            long factorial = 1;
            for(int i = 1; i <= num; ++i)
            {
                // factorial = factorial * i;
                factorial *= i;
            }
            System.out.printf("Factorial of %d = %d", num, factorial);
        }
        
        
        //recursive function
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
    }
series de fibinacci

    public class FibonacciSeries {
    
        public static int printFibonacci(int n){
            if (n < 2) return(n);
          return( printFibonacci(n-2) + printFibonacci(n-1) );
            }
        
    
        public static void main(String[] args) {
            int n = 3;
             int N =printFibonacci(n);
          System.out.println(N);
        }
    }
nombre pair impair

    public class PairImpair {
        public static void main(String[] args) {
            int x=44;
            if (x%2==0) {
                System.err.println("pair");
            } else {
                System.err.println("impair");
            }
        }
       
    }
ugly number

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
        
        public static void main(String[] args) {
            System.err.println(""+isUgly(30));
        }
    }
