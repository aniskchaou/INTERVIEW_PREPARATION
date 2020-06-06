#sum based on factor

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
