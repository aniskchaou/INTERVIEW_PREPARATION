## Power
**input** 

    2 exp 3 = 2 * 2 *2 = 8

**Output**

    8

**Algorithm**

    public static long pow(int num, int exp) {
            long result = 1;
            for (int i = 1; i <= exp; i++) {
                result *= num;
            }
            return result;
        }
