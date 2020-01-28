## Palindrome number
Write a java program to check palindrome number.

**Input:**  329

**Output:**  not palindrome number

**Input:**  12321

**Output:**  palindrome number

      int r, sum = 0, temp;
            int n = 454;
    
            temp = n;
            while (n > 0) {
                r = n % 10; 
                sum = (sum * 10) + r;
                n = n / 10;
            }
            if (temp == sum) {
                System.out.println("palindrome number ");
            } else {
                System.out.println("not palindrome");
            }
