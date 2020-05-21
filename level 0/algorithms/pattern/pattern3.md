## How to print Floyd's Triangle


     public static void printFloydTriangle(int rows) {
                int number = 1;
                
         
                for (int i = 1; i <= rows; i++) {
                    
                    for (int j = 1; j <= i; j++) {
                        System.out.print(number + " ");
                        number++;
                    }
         
                    System.out.println();
                }
            }

 
**Output**

    Enter the number of rows of Floyd's triangle, you want to display
    5
    Floyd's triangle of 5 rows is :
    1
    2 3
    4 5 6
    7 8 9 10
    11 12 13 14 15

 

