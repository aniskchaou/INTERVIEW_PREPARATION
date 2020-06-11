## Bubble Sort
![enter image description here](https://www.studytonight.com/data-structures/images/basic-bubble-sort.png)

    public static void main(String[] args) {	
           int[] arr= {3,5,7,3,1,0};
           bubbleSort(arr);   
        }
    
    	static void bubbleSort(int[] arr)
    	{
    		int lastCell=arr.length-1;
    		int aux=0;
    		for (int i = 0; i < lastCell; i++) {
    			for (int j = 0; j < lastCell-i; j++) {
    				if(arr[j]>arr[j+1])
    				{
    					aux=arr[j];
    					arr[j]=arr[j+1];
    					arr[j+1]=aux;
    				}
    			}
    		}
    		System.out.println(Arrays.toString(arr));
    	}
