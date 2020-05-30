## Program to calculate value of nCr

## Examples :

    Input :  n = 5, r = 2
    Output : 30
    The value of 5C2 is 10
    
    Input : n = 3, r = 1
    Output : 3

## idea

    The idea is simply based on below formula.
    
    nCr = (n!) / (r! * (n-r)!)



  

## solution

    static int nCr(int n, int r) 
    { 
        return fact(n) / (fact(r) * fact(n - r)); 
    } 
      
    // Returns factorial of n 
    static int fact(int n) 
    { 
        int res = 1; 
        for (int i = 2; i <= n; i++) 
            res = res * i; 
        return res; 
    } 
      
    // Driver code 
    public static void main(String[] args) 
    { 
        int n = 5, r = 3; 
        System.out.println(nCr(n, r)); 
    } 
 
