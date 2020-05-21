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
