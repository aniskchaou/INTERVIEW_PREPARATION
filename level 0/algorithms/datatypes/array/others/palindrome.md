
## Palindrome
**input** 

    [4,5,6,5,4]

**output**

    true

**algorithm**

        public static boolean isPalindrome(int[] a)
    {
        boolean ispalindrome=true;
        int k=0;
        for (int i = a.length-1; i >=0; i--) {
            if (a[i]!=a[k]) {
               ispalindrome=false;
               break;
               
            }
            k++;
        }
        
        return ispalindrome;
    }
