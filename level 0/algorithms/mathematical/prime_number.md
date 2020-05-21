## List Of prime numbers
**input**

    [1,100]

**output**

    1
    2
    3
    5
    7
    11
    13
    17
    19
    23
    29
    31
    37
    41
    43
    47
    53
    59
    61
    67
    71
    73
    79
    83
    89
    97

**algorithm**

      public static void primeNumber(int begin,int end)
       {
           
           for (int i = begin; i <=end; i++) {
               if (isPrime(i)) {
                   System.out.println(""+i);
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
