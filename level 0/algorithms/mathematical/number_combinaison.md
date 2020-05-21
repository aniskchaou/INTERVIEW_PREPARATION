## Number of combinaisons
**Formula**

    n!  /( (n-2)! x  2!  )

**Algorithm**

      public static int factorial(int n)
         {
             int res=1;
             for (int i = 1; i <=n; i++) {
                 res=res*i;
             }
             return res;
         }
       
        public static int numberCombinaison(int n)
        {
            return  factorial(n)/(factorial(n-2)*factorial(2));
        }

## Big Integer

     public static int numberCombinaison(int n)
        {
            return ((factorial(n)).divide((factorial(n-2)).multiply(factorial(2)))).intValue();
        }
    
         public static BigInteger factorial(int n)
         {
             BigInteger res=new BigInteger("1");
            
             for (int i = 1; i <=n; i++) {
                 res=res.multiply(BigInteger.valueOf(i));
             }
             return res;
         }
