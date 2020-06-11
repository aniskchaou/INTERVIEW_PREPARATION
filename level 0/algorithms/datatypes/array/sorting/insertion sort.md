## Insertion sort
![enter image description here](https://miro.medium.com/max/3204/1*5t5q_OLP-kGwQyblAN-nog.png)

    public static void main(String[] args) {	
           int[] arr= {3,5,7,12,1,0};
          insertionSort(arr);  
        }
    
    	static void insertionSort(int[]arr)
    	{
    		for (int i = 1; i < arr.length; i++) {
    			int currentNumber=arr[i];
    			int j=i;
    			while(j>0 && arr[j-1]>currentNumber )
    			{
    				arr[j]=arr[j-1];
    				j--;
    			}
    			
    		arr[j]=currentNumber;
    		}
    		System.out.println(Arrays.toString(arr));
    	}
