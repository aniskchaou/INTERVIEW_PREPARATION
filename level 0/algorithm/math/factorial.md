## Factoriel
**non recursive**
    
            int num = 10;
            long factorial = 1;
            for(int i = 1; i <= num; ++i)
            {
                // factorial = factorial * i;
                factorial *= i;
            }
    
 **recursive** 
   

     public int factorial(int num)
            {
                /* local variable declaration */
                int result;
                if (num == 1)
                {
                    return 1;
                }
                else
                {
                    result = factorial(num - 1) * num;
                    return result;
                }
            }

  
class Krishnamurthy {
    static int fact(int n) {
        int i, p = 1;
        for (i = n; i >= 1; i--)
            p = p * i;
        return p;
    }

    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        int a, b, s = 0;
        System.out.print("Enter the number : ");
        a = sc.nextInt();
        int n = a;
        while (a > 0) {
            b = a % 10;
            s = s + fact(b);
            a = a / 10;
        }
        if (s == n)
            System.out.print(n + " is a krishnamurthy number");
        else
            System.out.print(n + " is not a krishnamurthy number");
        sc.close();
    }
}


public class Armstrong {
    static Scanner scan;

    public static void main(String[] args) {
        scan = new Scanner(System.in);
        int n = inputInt("please enter the number");
        boolean isArmstrong = checkIfANumberIsAmstrongOrNot(n);
        if (isArmstrong) {
            System.out.println("the number is armstrong");
        } else {
            System.out.println("the number is not armstrong");
        }
    }

    /**
     * Checks whether a given number is an armstrong number or not. Armstrong
     * number is a number that is equal to the sum of cubes of its digits for
     * example 0, 1, 153, 370, 371, 407 etc.
     *
     * @param number
     * @return boolean
     */
    public static boolean checkIfANumberIsAmstrongOrNot(int number) {
        int remainder, sum = 0, temp = 0;
        temp = number;
        while (number > 0) {
            remainder = number % 10;
            sum = sum + (remainder * remainder * remainder);
            number = number / 10;
        }
        return sum == temp;
    }

    private static int inputInt(String string) {
        System.out.print(string);
        return Integer.parseInt(scan.nextLine());
    }
}

class Abecedarian {

    public static boolean isAbecedarian(String s) {
        int index = s.length() - 1;

        for (int i = 0; i < index; i++) {

            if (s.charAt(i) <= s.charAt(i + 1)) {
            } //Need to check if each letter for the whole word is less than the one before it

            else {
                return false;
            }
        }
        return true;
    }
}