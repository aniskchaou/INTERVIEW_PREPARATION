
# Sum of all the factors of a number

Given a number n, the task is to find the sum of all the divisors.

**Examples :**

    Input : n = 30
    Output : 72
    Dividers sum 1 + 2 + 3 + 5 + 6 + 
                 10 + 15 + 30 = 72 
    
    Input :  n = 15
    Output : 24
    Dividers sum 1 + 3 + 5 + 15 = 24

**implementation**

      static int sumFactor(int n)
    {
        int sum = 0;
        for (int i = 1; i <= n; i++) {
            if (n%i==0) {
                sum+=i;
            }
        }
        
        return sum;
    }




##  Deficient number

**The sum of the proper divisors is lesser than the number itself.**

For example, the number 21 with its proper divisors (1, 3 and 7) has sum (11) lesser than itself.


## Abundant number

**the sum of its proper divisors is greater than the number itself.**

A first abundant number is the integer 12 having the sum (16) of its proper divisors (1, 2, 3, 4, 6) which is greater than itself (12).

