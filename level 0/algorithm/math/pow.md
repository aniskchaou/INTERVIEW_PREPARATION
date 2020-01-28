## Power
input : 2
2 exp 3 = 2 * 2 *2 = 8

    public static long pow(int a, int b) {
            long result = 1;
            for (int i = 1; i <= b; i++) {
                result *= a;
            }
            return result;
        }