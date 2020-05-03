## Intervals
    public static int binarySearch(int arr[], int elementToSearch) {
    
        int firstIndex = 0;
        int lastIndex = arr.length - 1;
    
        
        while(firstIndex <= lastIndex) {
            
            int middleIndex = (firstIndex + lastIndex) / 2;
            
            if (arr[middleIndex] == elementToSearch) {
                return middleIndex;
            }
    
            
            else if (arr[middleIndex] < elementToSearch)
                firstIndex = middleIndex + 1;
    
            
            else if (arr[middleIndex] > elementToSearch)
                lastIndex = middleIndex - 1;
    
        }
        return -1;
    }
