## Sum Array
   

    public static void main(String[] args) {
            int[] numbers={1,2,3,4,5};
            int start=0;
            int end=numbers.length;
            int sum=0;
            System.out.println(sumReverse(start, end, sum, numbers));
        }
        
      static int sumNormal(int start,int end,int[]numbers)
      {
          int sum=0;
          for (int i = start; i < end; i++) {
              sum+=numbers[i];
          }
          return sum;
      }
      
      
      static int sumReverse(int start,int end,int sum,int[]numbers)
      {
          if(start==end)
           return sum ;
          else
            return (sum+sumReverse(start+1,end,sum+1,numbers));  
      }
    
      public int sumOfArray(int[] a, int n) {
        if (n == 0)
            return a[n];
        else
            return a[n] + sumOfArray(a, n-1);
    }
