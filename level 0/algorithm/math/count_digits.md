## Count Number of Digits

    public static int numberDigits(int n)
    {
        int count=0;
        while (n!=0) {        
            count++;
            n/=10;
        }
        
        return count;
    }

## Sum Of Digits

    public static int sumDigits(int n)
    {
        int sum=0;
        int rest=0;
        while (n!=0) {        
            rest=n%10;
            sum+=rest;
            n/=10;
        }
        
        return sum;
    }



## Harshad number

A number is said to be the Harshad number if it is divisible by the sum of its digit.

**Input:**

num = 156

**Output:**

156 is a Harshad number

    public static void isHarshad(int n)
    {
        if(n%sumDigits(n)==0)
            System.err.println("Harshad Number");
         else
            System.err.println("Not Harshad Number");
    }

