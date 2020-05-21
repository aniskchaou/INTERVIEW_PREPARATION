## Intervals
      public static boolean exists(int[] ints, int k) {
    
         if(ints==null) return false;
         
        int firstIndex = 0;
        int lastIndex = ints.length - 1;
    
        
        while(firstIndex <= lastIndex) {
            
            int middleIndex = (firstIndex + lastIndex) / 2;
            
            if (ints[middleIndex] == k) {
                return true;
            }
    
            
            else if (ints[middleIndex] < k)
                firstIndex = middleIndex + 1;
    
            
            else if (ints[middleIndex] > k)
                lastIndex = middleIndex - 1;
    
        }
        return false;
    }
