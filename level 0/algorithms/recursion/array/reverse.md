## Reverse Array

        public static void main(String[] args) {
            int[] numbers={1,2,3,4,5};
            int start=0;
            int end=numbers.length;
            printArray(start, end, numbers);
             printReverseArray(start, end-1, numbers);
        }
        
      static void printArray(int start,int end,int[] numbers)
       {
           if(start==end)
           {   return ;}
           else
           {  System.out.print(numbers[start]);
               printArray(start+1, end, numbers);
           }
       }
       
       static void printReverseArray(int start,int end,int[] numbers)
       {
           if(start>end)
           {   return ;}
           else
           { 
               System.out.print(numbers[end]);
               printReverseArray(start, end-1, numbers);
                
           }
       }
