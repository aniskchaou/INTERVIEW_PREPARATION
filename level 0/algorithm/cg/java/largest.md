## largest

1)
   

     int arr[]={1,6,9,3,7};
        Arrays.sort(arr);
        System.err.println("max "+arr[arr.length-1]);
        System.err.println("min "+arr[0]);

2)

       int arr[]={1,6,9,3,7};
            int max=arr[0];
            int min =arr[0];
            
            for (int i = 0; i < arr.length; i++) {
                if(arr[i]>max)
                {
                    max=arr[i];
                }
                
                if(arr[i]<min)
                {
                    min=arr[i];
                }
            }
            
            System.err.println("max "+max+" min "+min);
