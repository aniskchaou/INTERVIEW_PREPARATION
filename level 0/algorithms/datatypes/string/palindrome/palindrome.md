## palindrome


    public static boolean isPalindrome(String s) {
        
                int start = 0;
                int end = s.length() - 1;
        
                while (start < end) {
                    if (s.charAt(i) != s.charAt(j)) {
                        return false;
                    }
        
                    start++;
                    end--;
                }
                return true;
            }
