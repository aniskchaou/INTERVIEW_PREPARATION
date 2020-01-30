## duplicate removal

     int arr[]={1,2,3,4,7,2,7,3,5};
            Arrays.sort(arr);
            int temp[]=new int[arr.length];
            int count=0;
            
            for (int i = 0; i < arr.length-1; i++) {
                if(arr[i]!=arr[i+1])
                {
                    temp[count++]=arr[i];
                }
            }
            
           temp[count++]=arr[arr.length-1];
           arr=new int[count];
            for (int i = 0; i < count; i++) {
               arr[i]=temp[i]; 
            }
            
            System.err.println(""+Arrays.toString(arr));




