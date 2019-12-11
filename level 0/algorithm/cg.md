

## HeadingMove all zeroes


**Example:**

    Input :  arr[] = {1, 2, 0, 4, 3, 0, 5, 0};
    Output : arr[] = {1, 2, 4, 3, 5, 0, 0};
    
    Input : arr[]  = {1, 2, 0, 0, 0, 3, 6};
    Output : arr[] = {1, 2, 3, 6, 0, 0, 0};

**algo**

       static void pushZerosToEnd(int arr[], int n) {
        int count = 0;
    
        for (int i = 0; i < n; i++) {
            if (arr[i] != 0) {
                arr[count++] = arr[i];
            }
        }
    
        while (count < n) {
            arr[count++] = 0;
        }
    }

## Reshape string


        public static String reshape(int n, String str) {
    
            //replace each space with empty string
            str = str.replace(" ", "");
    
            //insert a '\n' character each n characters
            String res = "";
    
            for (int i = 0; i < str.length(); i++) {
    
                if (i % n == 0 && i != 0) {
                    res = res + '\n' + str.charAt(i);
                } else {
                    res += str.charAt(i);
                }
    
            }
    
            return res;
    
        }

## Approximation pi

    import java.util.Scanner;
    
    import java.text.DecimalFormat;
    

    * 1 - 1/3 + 1/5 - 1/7 + 1/9 - ... = π/4
    
    
    public class Pi {
    
    public static void main(String[] args) {
    
    int n = getInput();
    
    double piValue = calculatePi(n);
    
    printResult(piValue);
    
    }
    
    private static double calculatePi(double n) {
    
    double pi = 0;
    
    for (int i = 1; i < n; i++) {
    
    pi += Math.pow(-1,i+1) / (2*i - 1);
    
    }
    
    return 4 * pi;
    
    }
    
    private static int getInput() {
    
    int n = 0;
    
    Scanner input = new Scanner(System.in);
    
    System.out.println("How many calculations should be run for the approximation?");
    
    try {
    
    n = Integer.parseInt(input.nextLine());
    
    } /** Handle input greater than Java's MAX_INT. **/
    
    catch (NumberFormatException e) {
    
    System.out.println("n is too large. Setting n to be the largest possible int value.");
    
    n = Integer.MAX_VALUE;
    
    }
    
    input.close();
    
    return n;
    
    }
    
    private static double calculateError(double piValue) {
    
    return Math.abs(1 - piValue / Math.PI) * 100;
    
    }
    
    private static void printResult(double piValue) {
    
    DecimalFormat df = new DecimalFormat("#.##");
    
    System.out.println("The value of pi is approximately " + piValue + ".");
    
    System.out.println("The calculated value is off by approximately " + df.format(calculateError(piValue)) + "%.");
    
    }
    
    }
    

## Range sum

        public class RangeSum
        {
        
           public static void main(String[] args)
           {
              int[] numbers = {1, 2, 3, 4, 5, 6, 7, 8, 9};
              
              System.out.print("The sum of elements 2 through " +
                               "5 is "+ rangeSum(numbers, 3, 5));
           }
           
      public static int rangeSum(int[] array, int start, int end)
       {
          if (start > end)
             return 0;
          else
             return array[start] +
                        rangeSum(array, start + 1, end);
       }
    }

   
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

    static int divSum(int n) 
            { 
               
                int result = 0; 
                for (int i = 2; i <= Math.sqrt(n); i++) 
                { 
                    
                    if (n % i == 0) 
                    { 
                     
                        if (i == (n / i)) 
                            result += i; 
                        else
                            result += (i + n / i); 
                    } 
                } 
              
                return (result + n + 1); 
                  
            } 

## Twin Prime Numbers



    Examples :
    
    Input : n1 = 11, n2 = 13
    Output : Twin Prime
    
    Input : n1 = 23, n2 = 37
    Output : Not Twin Prime

algo 

    
           
            static boolean isPrime(int n)  
            { 
                
                if (n <= 1) return false; 
                if (n <= 3) return true; 
          
               
                if (n % 2 == 0 || n % 3 == 0)  
                    return false; 
          
                for (int i = 5; i * i <= n; i = i + 6) 
                    if (n % i == 0 || n % (i + 2) == 0) 
                        return false; 
          
                return true; 
            } 
          
           
            static boolean twinPrime(int n1, int n2)  
            { 
                return (isPrime(n1) && isPrime(n2) && 
                             Math.abs(n1 - n2) == 2); 
            } 
       
        

## Print all possible combinations of r elements in a given array of size n

Given an array of size n, generate and print all possible combinations of r elements in array. For example, if input array is {1, 2, 3, 4} and r is 2, then output should be {1, 2}, {1, 3}, {1, 4}, {2, 3}, {2, 4} and {3, 4}.

    static void combinationUtil(int arr[], int data[], int start, 
                                            int end, int index, int r) 
                { 
                    
                    if (index == r) 
                    { 
                        for (int j=0; j<r; j++) 
                            System.out.print(data[j]+" "); 
                        System.out.println(""); 
                        return; 
                    } 
              
                   
                    for (int i=start; i<=end && end-i+1 >= r-index; i++) 
                    { 
                        data[index] = arr[i]; 
                        combinationUtil(arr, data, i+1, end, index+1, r); 
                    } 
                } 
     
      