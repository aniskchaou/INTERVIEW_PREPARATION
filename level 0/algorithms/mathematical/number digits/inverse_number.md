
## Reverse Number
**example**

    123-->321
    30+3=3
    30+2=32
    320+1=321

**algorithm**

 `` 
  public static int reverse(int n)
     {
         int rest=0;
         int reverse=0;
         while (n!=0) {         
         rest=n%10;   
         reverse=(reverse*10)+rest;
         n/=10;
         }
         
         return reverse;
     }

