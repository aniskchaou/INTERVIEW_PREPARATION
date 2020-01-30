## Palindrome number


**Input:**  329

**Output:**  not palindrome number

**Input:**  12321

**Output:**  palindrome number

**Algorithm**

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
     
     public static boolean isPalindrome(int n)
     {
         if (n==reverse(n)) {
             return true;
         }else
         {
             return false;
         }
     }
