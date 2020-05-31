## k'th smallest and largest

    public static int kthSmallest(Integer[] arr, int k) {
    		Arrays.sort(arr);
    		return arr[k - 1];
    	}
    	
    	public static int kthLargest(Integer[] arr, int k) {
    		Arrays.sort(arr);
    		int numElements=arr.length;
    		return arr[numElements-k];
    	}
    
    // driver program 
    	public static void main(String[] args) {
    		Integer arr[] = new Integer[] { 12, 3, 5, 7, 19 };
    		int k = 2;
    		System.out.println("K'th smallest element is " + kthSmallest(arr, k));
    		System.out.println("K'th largest element is " + kthLargest(arr, k));
    	}
