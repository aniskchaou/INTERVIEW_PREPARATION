

## Fibonacci series
![enter image description here](https://www.codesdope.com/staticroot/images/algorithm/dynamic1.png)
## Top Down

      public static void main(String[] args) {
            int n=9;
            int[] memorize=new int[n+1];
            System.out.println(fibonacciTopDown(n, memorize));
        }
        
        static int fibonacciTopDown(int n,int[] memorize){
            if (n <= 1) 
           return n;
            
            if(memorize[n]==0)
               return fibonacciTopDown(n-1, memorize)+fibonacciTopDown(n-2, memorize);
            
            return memorize[n];
        }

## Bottom Up

     public static void main(String[] args) {
            int n=5;
            System.out.println(fibonacciBottomUp(9));
        }
        
        static int fibonacciBottomUp(int n)
        {
           if (n<=1) return 1;
           
           int[] memorize=new int[n+1];
           
           memorize[0]=0;
           memorize[1]=1;
           
            for (int i = 2; i <=n; i++) {
                memorize[i]=(memorize[i-1]+memorize[i-2]);
            }
            
            return memorize[n];
           
        }
