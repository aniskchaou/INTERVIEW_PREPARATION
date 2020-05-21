## find all possible subsets of a string

**Input:**

    str = "ABC"

**Output:**

    All subsets for given string are:
    A
    AB
    ABC
    B
    BC
    C

**program**
     public static void main(String[] args) {
    
            String str = "ABC";
            int len = str.length();
            
            //Total possible subsets for string of size n is n*(n+1)/2
            List arr=new ArrayList();
    
            //This loop maintains the starting character
            for (int i = 0; i < len; i++) {
                //This loop adds the next character every iteration for the subset to form and add it to the array
                for (int j = i; j < len; j++) {
                    arr.add(str.substring(i, j + 1));
                 
                }
            }
    
            //This loop prints all the subsets formed from the string.
            System.out.println("All subsets for given string are: ");
            for (int i = 0; i < arr.size(); i++) {
                System.out.println(arr.get(i));
            }
        }