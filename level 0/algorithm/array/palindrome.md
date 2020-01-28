## Palindrome

     public static boolean isPalindrome(int[] a)
        {
            int j=a.length-1;
            boolean palindrome=true;
            for (int i = 0; i < a.length && j>=0 ; i++) {
                
                    if (a[i]!=a[j] ) {
                        System.err.println("i "+i+" "+j);
                        palindrome=false;
                        break;
                    }
                j--;
            }
            
            return palindrome;
        }
