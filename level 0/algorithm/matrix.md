## Program to calculate the addition of 2 matrices


**Input:**

    Matrix a = [1, 0, 1]
               [4, 5, 6]
               [1, 2, 3]

 

    matrix b = [1, 1, 1]
               [2, 3, 1]
               [1, 5, 1]

**Output:**

    Addition of two matrices: [2 1 2]
                              [6 8 7]
                              [2 7 4]

 **programs**                         
  

      1.  public  class SumMatrix
        2.  {
        3.  public  static  void main(String[] args) {
        4.  int rows, cols;
        
        5.  //Initialize matrix a
        6.  int a[][] = {
        7.  {1, 0, 1},
        8.  {4, 5, 6},
        9.  {1, 2, 3}
        10.  };
        
        11.  //Initialize matrix b
        12.  int b[][] = {
        13.  {1, 1, 1},
        14.  {2, 3, 1},
        15.  {1, 5, 1}
        16.  };
        
        17.  //Calculates number of rows and columns present in given matrix
        18.  rows = a.length;
        19.  cols = a[0].length;
        
        20.  //Array sum will hold the result
        21.  int sum[][] = new  int[rows][cols];
        
        22.  //Performs addition of matrices a and b. Store the result in matrix sum
        23.  for(int i = 0; i < rows; i++){
        24.  for(int j = 0; j < cols; j++){
        25.  sum[i][j] = a[i][j] + b[i][j];
        26.  }
        27.  }
        
        28.  System.out.println("Addition of two matrices: ");
        29.  for(int i = 0; i < rows; i++){
        30.  for(int j = 0; j < cols; j++){
        31.  System.out.print(sum[i][j] + " ");
        32.  }
        33.  System.out.println();
        34.  }
        35.  }
        36.  }

## Program to calculate the subtraction of 2 matrices

**Input:**

    Matrix a = [4, 5, 6]
               [3, 4, 1]
               [1, 2, 3]
    
    Matrix b = [2, 0, 3]
               [2, 3, 1]
               [1, 1, 1]

**Output:**

    Subtraction of two matrices: [2 5 3]
                                 [1 1 0]
                                 [0 1 2]

  **programs**

    1.  public  class SubMatrix
    2.  {
    3.  public  static  void main(String[] args) {
    4.  int rows, cols;
    
    5.  //Initialize matrix a
    6.  int a[][] = {
    7.  {4, 5, 6},
    8.  {3, 4, 1},
    9.  {1, 2, 3}
    10.  };
    
    11.  //Initialize matrix b
    12.  int b[][] = {
    13.  {2, 0, 3},
    14.  {2, 3, 1},
    15.  {1, 1, 1}
    16.  };
    
    17.  //Calculates number of rows and columns present in given matrix
    18.  rows = a.length;
    19.  cols = a[0].length;
    
    20.  //Array diff will hold the result
    21.  int diff[][] = new  int[rows][cols];
    
    22.  //Performs subtraction of matrices a and b. Store the result in matrix diff
    23.  for(int i = 0; i < rows; i++){
    24.  for(int j = 0; j < cols; j++){
    25.  diff[i][j] = a[i][j] - b[i][j];
    26.  }
    27.  }
    
    28.  System.out.println("Subtraction of two matrices: ");
    29.  for(int i = 0; i < rows; i++){
    30.  for(int j = 0; j < cols; j++){
    31.  System.out.print(diff[i][j] + " ");
    32.  }
    33.  System.out.println();
    34.  }
    35.  }
    36.  }


## determine whether a given matrix is an identity matrix

**Input:**

    Matrix a =[1, 0, 0]
              [0, 1, 0]
              [0, 0, 1]

**Output:**

Given matrix is an identity matrix

    public class IdentityMatrix {
    
        public static void main(String[] args) {
            int rows, cols;
            boolean flag = true;
    
            //Initialize matrix a
            int a[][] = {
                {1, 0, 0},
                {0, 1, 0},
                {0, 0, 1}
            };
    
            //Calculates the number of rows and columns present in the given matrix
            rows = a.length;
            cols = a[0].length;
    
            //Checks whether given matrix is a square matrix or not
            if (rows != cols) {
                System.out.println("Matrix should be a square matrix");
            } else {
                //Checks if diagonal elements are equal to 1 and rest of elements are 0
                for (int i = 0; i < rows; i++) {
                    for (int j = 0; j < cols; j++) {
                        if (i == j && a[i][j] != 1) {
                            flag = false;
                            break;
                        }
                        if (i != j && a[i][j] != 0) {
                            flag = false;
                            break;
                        }
                    }
                }
    
                if (flag) {
                    System.out.println("Given matrix is an identity matrix");
                } else {
                    System.out.println("Given matrix is not an identity matrix");
                }
            }
        }
    }

## find the product of two matrices

    public class ProdMatrix {
    
        public static void main(String[] args) {
            int row1, col1, row2, col2;
    
            //Initialize matrix a
            int a[][] = {
                {1, 3, 2},
                {3, 1, 1},
                {1, 2, 2}
            };
    
            //Initialize matrix b
            int b[][] = {
                {2, 1, 1},
                {1, 0, 1},
                {1, 3, 1}
            };
    
            //Calculates number of rows and columns present in first matrix
            row1 = a.length;
            col1 = a[0].length;
    
            //Calculates the number of rows and columns present in the second matrix
            row2 = b.length;
            col2 = b[0].length;
    
            //For two matrices to be multiplied,
            //number of columns in first matrix must be equal to number of rows in second matrix
            if (col1 != row2) {
                System.out.println("Matrices cannot be multiplied");
            } else {
                //Array prod will hold the result
                int prod[][] = new int[row1][col2];
    
                //Performs product of matrices a and b. Store the result in matrix prod
                for (int i = 0; i < row1; i++) {
                    for (int j = 0; j < col2; j++) {
                        for (int k = 0; k < row2; k++) {
                            prod[i][j] = prod[i][j] + a[i][k] * b[k][j];
                        }
                    }
                }
    
                System.out.println("Product of two matrices: ");
                for (int i = 0; i < row1; i++) {
                    for (int j = 0; j < col2; j++) {
                        System.out.print(prod[i][j] + " ");
                    }
                    System.out.println();
                }
            }
        }
    }

## find the sum of each row and each column of a matrix


    public class SumofRowColumn {
    
        public static void main(String[] args) {
            int rows, cols, sumRow, sumCol;
    
            //Initialize matrix a
            int a[][] = {
                {1, 2, 3},
                {4, 5, 6},
                {7, 8, 9}
            };
    
            //Calculates number of rows and columns present in given matrix
            rows = a.length;
            cols = a[0].length;
    
            //Calculates sum of each row of given matrix
            for (int i = 0; i < rows; i++) {
                sumRow = 0;
                for (int j = 0; j < cols; j++) {
                    sumRow = sumRow + a[i][j];
                }
                System.out.println("Sum of " + (i + 1) + " row: " + sumRow);
            }
    
            //Calculates sum of each column of given matrix
            for (int i = 0; i < cols; i++) {
                sumCol = 0;
                for (int j = 0; j < rows; j++) {
                    sumCol = sumCol + a[j][i];
                }
                System.out.println("Sum of " + (i + 1) + " column: " + sumCol);
            }
        }
    }


## find the transpose of a given matrix

    public class Transpose {
    
        public static void main(String[] args) {
            int rows, cols;
    
            //Initialize matrix a
            int a[][] = {
                {1, 2, 3},
                {4, 5, 6},
                {7, 8, 9}
            };
    
            //Calculates number of rows and columns present in given matrix
            rows = a.length;
            cols = a[0].length;
    
            //Declare array t with reverse dimensions
            int t[][] = new int[cols][rows];
    
            //Calculates transpose of given matrix
            for (int i = 0; i < cols; i++) {
                for (int j = 0; j < rows; j++) {
                    //Converts the row of original matrix into column of transposed matrix
                    t[i][j] = a[j][i];
                }
            }
    
            System.out.println("Transpose of given matrix: ");
            for (int i = 0; i < cols; i++) {
                for (int j = 0; j < rows; j++) {
                    System.out.print(t[i][j] + " ");
                }
                System.out.println();
            }
        }
    }



