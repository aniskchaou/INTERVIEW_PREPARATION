## duplicate removal

    public static  int[] duplicateRemoval(int[] arr)
       {
           int[] temp=new int[arr.length];
           int count=0;
           
           // sort
           Arrays.sort(arr);
           
           //fill temp array
           for (int i = 0; i < arr.length-1; i++) {
               if (arr[i]!=arr[i+1]) {
                   temp[count++]=arr[i];
               }
               
           }
           
           //add the last elemebt
           temp[count++]=arr[arr.length-1];
           
           //fill the new array
           arr=new int[count];
           for (int i = 0; i < count; i++) {
               arr[i]=temp[i];
           }
           
           return arr;
       }



