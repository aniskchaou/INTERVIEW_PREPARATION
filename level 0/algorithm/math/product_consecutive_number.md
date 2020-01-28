## Pronic number

A number is said to be pronic number if it is a product of two consecutive numbers.

For examples:

    6 = 2 x 3  
    72 = 8 x 9

**Input:**

range(1, 101)

**Output:**

Pronic numbers between 1 and 100: 2 6 12 20 30 42 56 72 90

     public static boolean isPronicNumber(int num) {
        boolean flag = false;

        for (int j = 1; j <= num; j++) {
           
            if ((j * (j + 1)) == num) {
                flag = true;
                break;
            }
        }
        return flag;
    }

