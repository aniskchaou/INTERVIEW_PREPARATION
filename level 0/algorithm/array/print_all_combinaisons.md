## Print all possible combinations of r elements in a given array of size n

Given an array of size n, generate and print all possible combinations of r elements in array. For example, if input array is {1, 2, 3, 4} and r is 2, then output should be {1, 2}, {1, 3}, {1, 4}, {2, 3}, {2, 4} and {3, 4}.

    static void combinationUtil(int arr[], int data[], int start, 
                                            int end, int index, int r) 
                { 
                    
                    if (index == r) 
                    { 
                        for (int j=0; j<r; j++) 
                            System.out.print(data[j]+" "); 
                        System.out.println(""); 
                        return; 
                    } 
              
                   
                    for (int i=start; i<=end && end-i+1 >= r-index; i++) 
                    { 
                        data[index] = arr[i]; 
                        combinationUtil(arr, data, i+1, end, index+1, r); 
                    } 
                } 