# Edit Distance

Given two strings str1 and str2 and below operations that can performed on str1. Find minimum number of edits (operations) required to convert ‘str1’ into ‘str2’.

1.  Insert
2.  Remove
3.  Replace

All of the above operations are of equal cost.  
**  
Examples:**

    Input:   str1 = "geek", str2 = "gesek"
    Output:  1
    We can convert str1 into str2 by inserting a 's'.
    
    Input:   str1 = "cat", str2 = "cut"
    Output:  1
    We can convert str1 into str2 by replacing 'a' with 'u'.
    
    Input:   str1 = "sunday", str2 = "saturday"
    Output:  3
    Last three and first characters are same.  We basically
    need to convert "un" to "atur".  This can be done using
    below three operations. 
    Replace 'n' with 'r', insert t, insert a
**Algorithm**

    public class ConvertOneStringToAnother_DC {
    
    	public int findMinOperations(String s1, String s2) {
    		return findMinOperationsAux(s1, s2, 0, 0);
    	}//end of method
    
    	private int findMinOperationsAux(String s1, String s2, int i1, int i2) {
    		if (i1 == s1.length()) // if we have reached the end of s1, then insert all the remaining characters of s2
    			return s2.length() - i2;
    
    		if (i2 == s2.length()) // if we have reached the end of s2, then delete all the remaining characters of s1
    			return s1.length() - i1;
    
    		if (s1.charAt(i1) == s2.charAt(i2)) // If the strings have a matching character, recursively match for the remaining lengths.
    			return findMinOperationsAux(s1, s2, i1 + 1, i2 + 1);
    
    		int c1 = 1 + findMinOperationsAux(s1, s2, i1 + 1, i2); // perform deletion
    		int c2 = 1 + findMinOperationsAux(s1, s2, i1, i2 + 1); // perform insertion
    		int c3 = 1 + findMinOperationsAux(s1, s2, i1 + 1, i2 + 1); // perform replacement
    
    		return Math.min(c1, Math.min(c2, c3));
    	}//end of method
    
    	public static void main(String[] args) {
    		ConvertOneStringToAnother_DC editDisatnce = new ConvertOneStringToAnother_DC();
    		System.out.println(editDisatnce.findMinOperations("table", "tbres"));
    
    	}//end of method
    }// end of class

