## largest

1)
   

     int arr[]={1,6,9,3,7};
        Arrays.sort(arr);
        System.err.println("max "+arr[arr.length-1]);
        System.err.println("min "+arr[0]);

2)

          static int findLargest(int[] numbers)
      {
          
          if(numbers.length>0){
              int max=numbers[0];
              
              for (int i = 0; i < numbers.length; i++) {
                    if(numbers[i]>max)
                    {
                        max=numbers[i];
                    }
              }
              return max;
          }else
          {
              return -1;
          }
      }

