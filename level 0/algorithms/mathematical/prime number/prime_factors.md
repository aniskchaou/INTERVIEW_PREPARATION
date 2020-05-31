## Prime factors

       public static void main(String[] args) {
           int number = 100;
        for (int i = 1; i <= number; i++) {
            if (number%i==0) {
                if(isPrime(i))
                {
                    System.out.println(i);
                }
            }
        }
        }
    
        
         public static boolean isPrime(int n)
       {
           boolean isprime=true;
           for (int i = 2; i <n; i++) {
               if(n%i==0)
               {
                   isprime=false;
                   break;
               }
           }
           
           return isprime;
       }

