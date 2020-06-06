# Longest Increasing Subsequence
**Input:** arr[] = {3, 10, 2, 1, 20}
**Output:** Length of LIS = 3
The longest increasing subsequence is 3, 10, 20

**Input:** arr[] = {3, 2}
**Output:** Length of LIS = 1
The longest increasing subsequences are {3} and {2}

**Input:** arr[] = {50, 3, 10, 7, 40, 80}
**Output:** Length of LIS = 4
The longest increasing subsequence is {3, 7, 40, 80}

**Algorithm**

    class Main
    {
    	// Function to find length of longest increasing subsequence
    	public static int LIS(int[] A, int i, int n, int prev)
    	{
    		// Base case: nothing is remaining
    		if (i == n) {
    			return 0;
    		}
    
    		// case 1: exclude the current element and process the
    		// remaining elements
    		int excl = LIS(A, i + 1, n, prev);
    
    		// case 2: include the current element if it is greater
    		// than previous element in LIS
    		int incl = 0;
    		if (A[i] > prev) {
    			incl = 1 + LIS(A, i + 1, n, A[i]);
    		}
    
    		// return maximum of above two choices
    		return Integer.max(incl, excl);
    	}
    
    	// Program for Longest Increasing Subsequence
    	public static void main(String[] args)
    	{
    		int[] A = { 0, 8, 4, 12, 2, 10, 6, 14, 1, 9, 5, 13, 3, 11, 7, 15 };
    
    		System.out.print("Length of LIS is "
    						+ LIS(A, 0, A.length, Integer.MIN_VALUE));
    	}
    }
