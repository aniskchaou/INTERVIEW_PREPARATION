## HeadingMove all zeroes


**Example:**

    Input :  arr[] = {1, 2, 0, 4, 3, 0, 5, 0};
    Output : arr[] = {1, 2, 4, 3, 5, 0, 0};
    
    Input : arr[]  = {1, 2, 0, 0, 0, 3, 6};
    Output : arr[] = {1, 2, 3, 6, 0, 0, 0};

**program**

       static void pushZerosToEnd(int arr[], int n) {
        int count = 0;
    
        for (int i = 0; i < n; i++) {
            if (arr[i] != 0) {
                arr[count++] = arr[i];
            }
        }
    
        while (count < n) {
            arr[count++] = 0;
        }
    }
