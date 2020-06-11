## Selection Sort
![enter image description here](https://www.programmingsimplified.com/images/c/selection-sort.png)
	

static void selectionSort(int[]arr)
	{
		int temp=0;
		int lastCell=arr.length-1;
		for (int i = 0; i <= lastCell; i++) {
		
			int minelement=findMinimum(i+1, lastCell, arr, i);
			if(minelement!=i)
			{
				temp=arr[i];
				arr[i]=arr[minelement];
				arr[minelement]=temp;
				
			}
			
		}
		
		System.out.println(Arrays.toString(arr));
	}
	
	static int findMinimum(int start,int end,int[] arr, int min)
	{
		for (int j =start; j <= end; j++) {
			if(arr[j]<arr[min])
				min=j;
			
			
		}
		return min;
	}
	
