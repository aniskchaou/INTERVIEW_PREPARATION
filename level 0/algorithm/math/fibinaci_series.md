## series de fibinacci
**input**

    8

**Output**

    8
    6
    4
    2
    3
    2
    5
    3
    2
    4
    2
    3
    2
    7
    5
    3
    2
    4
    2
    3
    2
    6
    4
    2
    3
    2
    5
    3
    2
    4
    2
    3
    2
    21

**Algorithm**
  

     public static int printFibonacci(int n) {
            if (n < 2) {
                return (n);
            }
            return (printFibonacci(n - 2) + printFibonacci(n - 1));
        }

