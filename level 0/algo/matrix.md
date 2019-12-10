[Program to calculate the addition of 2 matrices](https://www.javatpoint.com/program-to-calculate-the-addition-of-two-matrices)

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
37. 
38. [2) Program to calculate the subtraction of 2 matrices](https://www.javatpoint.com/program-to-calculate-the-subtraction-of-two-matrices)

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
37. 
[determine whether a given matrix is an identity matrix](https://www.javatpoint.com/program-to-determine-whether-a-given-matrix-is-an-identity-matrix)

**Input:**

Matrix a =[1, 0, 0]
          [0, 1, 0]
          [0, 0, 1]

**Output:**

Given matrix is an identity matrix

1.  public  class IdentityMatrix
2.  {
3.  public  static  void main(String[] args) {
4.  int rows, cols;
5.  boolean flag = true;

6.  //Initialize matrix a
7.  int a[][] = {
8.  {1, 0, 0},
9.  {0, 1, 0},
10.  {0, 0, 1}
11.  };

12.  //Calculates the number of rows and columns present in the given matrix

13.  rows = a.length;
14.  cols = a[0].length;

15.  //Checks whether given matrix is a square matrix or not
16.  if(rows != cols){
17.  System.out.println("Matrix should be a square matrix");
18.  }
19.  else {
20.  //Checks if diagonal elements are equal to 1 and rest of elements are 0
21.  for(int i = 0; i < rows; i++){
22.  for(int j = 0; j < cols; j++){
23.  if(i == j && a[i][j] != 1){
24.  flag = false;
25.  break;
26.  }
27.  if(i != j && a[i][j] != 0){
28.  flag = false;
29.  break;
30.  }
31.  }
32.  }

33.  if(flag)
34.  System.out.println("Given matrix is an identity matrix");
35.  else
36.  System.out.println("Given matrix is not an identity matrix");
37.  }
38.  }
39.  }
40. 
## find the product of two matrices
1.  public  class ProdMatrix
2.  {
3.  public  static  void main(String[] args) {
4.  int row1, col1, row2, col2;

5.  //Initialize matrix a
6.  int a[][] = {
7.  {1, 3, 2},
8.  {3, 1, 1},
9.  {1, 2, 2}
10.  };

11.  //Initialize matrix b
12.  int b[][] = {
13.  {2, 1, 1},
14.  {1, 0, 1},
15.  {1, 3, 1}
16.  };

17.  //Calculates number of rows and columns present in first matrix
18.  row1 = a.length;
19.  col1 = a[0].length;

20.  //Calculates the number of rows and columns present in the second matrix

21.  row2 = b.length;
22.  col2 = b[0].length;

23.  //For two matrices to be multiplied,
24.  //number of columns in first matrix must be equal to number of rows in second matrix
25.  if(col1 != row2){
26.  System.out.println("Matrices cannot be multiplied");
27.  }
28.  else{
29.  //Array prod will hold the result
30.  int prod[][] = new  int[row1][col2];

31.  //Performs product of matrices a and b. Store the result in matrix prod
32.  for(int i = 0; i < row1; i++){
33.  for(int j = 0; j < col2; j++){
34.  for(int k = 0; k < row2; k++){
35.  prod[i][j] = prod[i][j] + a[i][k] * b[k][j];
36.  }
37.  }
38.  }

39.  System.out.println("Product of two matrices: ");
40.  for(int i = 0; i < row1; i++){
41.  for(int j = 0; j < col2; j++){
42.  System.out.print(prod[i][j] + " ");
43.  }
44.  System.out.println();
45.  }
46.  }
47.  }
48.  }
49. 
## find the sum of each row and each column of a matrix

1.  public  class SumofRowColumn
2.  {
3.  public  static  void main(String[] args) {
4.  int rows, cols, sumRow, sumCol;

5.  //Initialize matrix a
6.  int a[][] = {
7.  {1, 2, 3},
8.  {4, 5, 6},
9.  {7, 8, 9}
10.  };

11.  //Calculates number of rows and columns present in given matrix
12.  rows = a.length;
13.  cols = a[0].length;

14.  //Calculates sum of each row of given matrix
15.  for(int i = 0; i < rows; i++){
16.  sumRow = 0;
17.  for(int j = 0; j < cols; j++){
18.  sumRow = sumRow + a[i][j];
19.  }
20.  System.out.println("Sum of " + (i+1) +" row: " + sumRow);
21.  }

22.  //Calculates sum of each column of given matrix
23.  for(int i = 0; i < cols; i++){
24.  sumCol = 0;
25.  for(int j = 0; j < rows; j++){
26.  sumCol = sumCol + a[j][i];
27.  }
28.  System.out.println("Sum of " + (i+1) +" column: " + sumCol);
29.  }
30.  }
31.  }
32. 
## find the transpose of a given matrix

1.  public  class Transpose
2.  {
3.  public  static  void main(String[] args) {
4.  int rows, cols;

6.  //Initialize matrix a
7.  int a[][] = {
8.  {1, 2, 3},
9.  {4, 5, 6},
10.  {7, 8, 9}
11.  };

13.  //Calculates number of rows and columns present in given matrix
14.  rows = a.length;
15.  cols = a[0].length;

17.  //Declare array t with reverse dimensions
18.  int t[][] = new  int[cols][rows];

20.  //Calculates transpose of given matrix
21.  for(int i = 0; i < cols; i++){
22.  for(int j = 0; j < rows; j++){
23.  //Converts the row of original matrix into column of transposed matrix
24.  t[i][j] = a[j][i];
25.  }
26.  }

28.  System.out.println("Transpose of given matrix: ");
29.  for(int i = 0; i < cols; i++){
30.  for(int j = 0; j < rows; j++){
31.  System.out.print(t[i][j] + " ");
32.  }
33.  System.out.println();
34.  }
35.  }
36.  }