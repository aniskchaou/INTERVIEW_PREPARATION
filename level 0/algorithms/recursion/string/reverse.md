## Reverse String

      public static void main(String[] args) {
            String inputString="hello world";
            int start=0;
            int end=inputString.length();
            //printStr(start, end, inputString.toCharArray());
             printReverseStr(start, end-1, inputString.toCharArray());
        }
        
      static void printStr(int start,int end,char[] inputString)
       {
           if(start==end)
           {   return ;}
           else
           {  System.out.print(inputString[start]);
               printStr(start+1, end, inputString);
           }
       }
       
       static void printReverseStr(int start,int end,char[] inputString)
       {
           if(start>end)
           {   return ;}
           else
           { 
               System.out.print(inputString[end]);
               printReverseStr(start, end-1, inputString);
                
           }
       }
