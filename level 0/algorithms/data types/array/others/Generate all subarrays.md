## Generate all subarrays

## Output

    All Non-empty Subarrays
    1 
    1 2 
    1 2 3 
    1 2 3 4 
    2 
    2 3 
    2 3 4 
    3 
    3 4 
    4

## Program

         static int arr[] = new int[]{1, 2, 3, 4}; 
          
        // Prints all subarrays in arr[0..n-1] 
        static void subArray( int n) 
        { 
            List  listCombinaison=new ArrayList();
           String arrString=arrayToString(arr);
            // Pick starting point 
            for (int i=0; i <n; i++) 
            { 
                // Pick ending point 
                for (int j=i; j<n; j++) 
                { 
                    listCombinaison.add(arrString.substring(i, j+1));
                } 
            } 
            printCombinaison(listCombinaison);
        } 
         static String arrayToString(int arr[]){
             String res="";
             for (int character : arr) {
                 res+=character;
             }
             return res;
         }
    
        static void printCombinaison(List listCombinaison)
        {
            for (Object word : listCombinaison) {
      // Driver method to test the above function 
        public static void main(String[] args)  
        { 
            System.out.println("All Non-empty Subarrays"); 
            subArray(arr.length); 
              
        }            System.out.println(word);
            }
        }
        
        // Driver method to test the above function 
        public static void main(String[] args)  
        { 
            System.out.println("All Non-empty Subarrays"); 
            subArray(arr.length); 
              
        } 
