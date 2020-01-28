## right rotate the elements of an array

**Input:**

arr = [1, 2, 3, 4, 5]
Here, n determine the number of times an array should be rotated
      n = 3

**Output:**

Original array: 1 2 3 4 5
Array after right rotation: 3 4 5 1 2

    1.  public  static  void main(String[] args) {
    
    3.  //Initialize array
    4.  int [] arr = new  int [] {1, 2, 3, 4, 5};
    5.  //n determine the number of times an array should be rotated.
    6.  int n = 3;
    
    8.  //Displays original array
    9.  System.out.println("Original array: ");
    10.  for (int i = 0; i < arr.length; i++) {
    11.  System.out.print(arr[i] + " ");
    12.  }
    
    14.  //Rotate the given array by n times toward right
    15.  for(int i = 0; i < n; i++){
    16.  int j, last;
    17.  //Stores the last element of array
    18.  last = arr[arr.length-1];
    
    20.  for(j = arr.length-1; j > 0; j--){
    21.  //Shift element of array by one
    22.  arr[j] = arr[j-1];
    23.  }
    24.  //Last element of array will be added to the start of array.
    25.  arr[0] = last;
    26.  }
    
    28.  System.out.println();
    
    30.  //Displays resulting array after rotation
    31.  System.out.println("Array after right rotation: ");
    32.  for(int i = 0; i< arr.length; i++){
    33.  System.out.print(arr[i] + " ");
    34.  }
    35.  }

## left rotate the elements of an array

**Input**:

    arr = [1, 2, 3, 4, 5]

**Output**:

    Original array: 1 2 3 4 5
    Array after left rotation: 4 5 1 2 3

**Program**

      public static int[] leftRotation(int nbTimes, int[] a) {
    
            int j = 0;
            for (int i = 0; i < nbTimes; i++) {
                int first = a[0];
    
                for (j = 0; j < a.length - 1; j++) {
                    a[j] = a[j + 1];
                }
    
                a[j] = first;
            }
    
            return a;
        }


