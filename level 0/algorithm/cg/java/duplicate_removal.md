## duplicate removal

    public static  int[] duplicateRemoval(int[] arr)
       {
           int[] temp=new int[arr.length];
           int count=0;
           Arrays.sort(arr);
           for (int i = 0; i < arr.length-1; i++) {
               if (arr[i]!=arr[i+1]) {
                   temp[count++]=arr[i];
               }
               
           }
           temp[count++]=arr[arr.length-1];
           arr=new int[count];
           for (int i = 0; i < count; i++) {
               arr[i]=temp[i];
           }
           
           return arr;
       }



