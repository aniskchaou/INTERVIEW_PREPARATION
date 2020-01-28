
## print the following pattern triangle
**output**

    *
     * *
     * * *
     * * * *
     * * * * *
     * * * * * *

**program**

    public class Pattern1 {
    
        public static void main(String[] args) {
            int i, j, n = 7;
            System.out.println("Right angle triangle");
            for (i = 1; i < n; i++) {
                for (j = 1; j <= i; j++) {
                    System.out.print(" *");
                }
                System.out.println("");
            }
        }
    }

## pattern 2
**output**

        *
       ***
      *****
     *******
    *********

**program**

    public class Pattern8 {
    
        public static void main(String[] args) {
            int size = 0;
            Character c;
            System.out.println();
            size = 5;
            int i, j, k;
            for (i = 0; i < size + 1; i++) {
                for (j = size; j > i; j--) {
                    System.out.print(" ");
                }
                for (k = 0; k < (2 * i - 1); k++) {
                    System.out.print("*");
                }
                System.out.println();
            }
        }
    }

## pattern 3
**output**

    1
    12
    123
    1234
    12345

**program**

    public class Pattern4 {
    
        public static void main(String[] args) {
            int n = 5;
            for (int i = 0; i <= n; i++) {
                for (int j = 0; j < i; j++) {
                    System.out.print(j + 1);
                }
                System.out.println("");
            }
        }
    }

## pattern 3

**output**

     1
     2 3
     4 5 6
     7 8 9 10

**program**

    public class pattern13 {
    
        public static void main(String[] args) {
            int n = 1;
            for (int i = 0; i < 6; i++) {
                for (int j = 1; j < i; j++) {
                    System.out.print(" " + n);
                    n++;
                }
                System.out.println("");
            }
        }
    }

## patern 4

**output**

    ******
    *****
    ****
    ***
    **
    *

**program**

    public class Pattern6 {
    
        public static void main(String[] args) {
            int i, j;
            int n = 6;
            for (i = n; i > 0; i--) {
                for (j = 0; j < i; j++) {
                    System.out.print("*");
                }
                System.out.println("");
            }
        }
    }

## pattern 5

**output**

            1
           1   1
          1   2   1
         1   3   3   1
        1   4   6   4   1
       1   5  10  10   5   1

**program**

    public class Pattern11 {
    
        public static void main(String[] args) {
    
            int coe = 1, rows = 6;
    
            for (int i = 0; i < rows; i++) {
    
                for (int space = 1; space < rows - i; ++space) {
    
                    System.out.print(" ");
    
                }
    
                for (int j = 0; j <= i; j++) {
    
                    if (j == 0 || i == 0) {
                        coe = 1;
                    } else {
                        coe = coe * (i - j + 1) / j;
                    }
    
                    System.out.printf("%4d", coe);
    
                }
    
                System.out.println();
    
            }
    
        }
    
    }

## pattern 6
**output**

    12345
    1234
    123
    12
    1

**program**

    public class Pattern7 {
    
        public static void main(String[] args) {
            int i, j;
            int n = 5;
            for (i = n; i > 0; i--) {
                for (j = 1; j <= i; j++) {
                    System.out.print(j);
                }
                System.out.println("");
            }
        }
    }

## pattern 7
**output**

     1 1 1 1 1 1 1 1 1 1
     1         1
     1         1
     1         1
     1         1
     1         1
     1         1
     1         1
     1         1
     1 1 1 1 1 1 1 1 1 1

**program**

    public class PatternBox {
    
        public static void main(String[] args) {
            for (int i = 1; i <= 10; i++) {
                for (int j = 1; j <= 10; j++) {
                    if (i == 1 || i == 10 || j == 1 || j == 10) {
                        System.out.print(" 1");
                    } else {
                        System.out.print(" ");
                    }
                }
                System.out.println();
            }
        }
    }

## pattern 8

**output**

    1 
    2 4 
    3 6 9 
    4 8 12 16 
    5 10 15 20 25 
    6 12 18 24 30 36 
    7 14 21 28 35 42 49 
    8 16 24 32 40 48 56 64 
    9 18 27 36 45 54 63 72 81 
    10 20 30 40 50 60 70 80 90 100

**program**

    public class pattern {
    
        public static void main(String[] args) {
    
            int lines = 10;
    
            int i = 1;
    
            int j;
    
            for (i = 1; i <= lines; i++) {// this loop is used to print the lines
    
                for (j = 1; j <= i; j++) {// this loop is used to print lines
    
                    System.out.print(i * j + " ");
    
                }
    
                System.out.println("");
    
            }
    
        }
    
    }

## pattern 9
**output**

    5432*
    543*1
    54*21
    5*321
    *4321

**program**

        public static void main(String[] args) {
            int i, j, lines = 5;
            for (i = 1; i <= lines; i++) {// this loop is used to print the lines
                for (j = lines; j >= 1; j--) {// this loop is used to print numbers in a line
                    if (j != i) {
                        System.out.print(j);
                    } else {
                        System.out.print("*");
                    }
                }
                System.out.println("");
            }
        }
    }



