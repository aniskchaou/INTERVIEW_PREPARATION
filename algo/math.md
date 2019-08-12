## nombre inverse

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
    


## nombre premier

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

## factoriel
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

## nombre pair impair

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
