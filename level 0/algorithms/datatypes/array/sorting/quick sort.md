	## Quick sort
	public static void main(String[] args) {	
       int[] arr= {3,5,7,12,1,0};
      quickSort(arr, 0, arr.length-1);  
      printArray(arr);
    }

	public static void quickSort(int[] array, int start, int end) {
		if (start < end) {
			int pivot = partition(array, start, end);
			quickSort(array, start, pivot-1 );
			quickSort(array, pivot + 1,end);
		}
	}//end of method

	
	static int partition(int[] array, int p, int q) {
		int pivot = q;
		int i = p-1;
		for (int j = p; j <= q; j++) {
			if (array[j] <= array[pivot]) {
				i++;
				int temp = array[i];
				array[i] = array[j];
				array[j] = temp;
			}
		}
		return i;

	}//end of method
