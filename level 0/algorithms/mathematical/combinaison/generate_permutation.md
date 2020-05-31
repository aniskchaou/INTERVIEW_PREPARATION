

## print the permutation (nPr) 

**Formula**

   
    nPr = n! / (n-r)! 

**Algorithm**

     public static int nbrPermutation(int n, int r)
        {
            return factorial(n)/factorial(n-r);
        }
        
         public static int factorial(int n)
         {
             int res=1;
             for (int i = 1; i <=n; i++) {
                 res=res*i;
             }
             return res;
         }






