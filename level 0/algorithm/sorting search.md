
# Bubble Sort
1.  public  class BubbleSortExample {
2.  static  void bubbleSort(int[] arr) {
3.  int n = arr.length;
4.  int temp = 0;
5.  for(int i=0; i < n; i++){
6.  for(int j=1; j < (n-i); j++){
7.  if(arr[j-1] > arr[j]){
8.  //swap elements
9.  temp = arr[j-1];
10.  arr[j-1] = arr[j];
11.  arr[j] = temp;
12.  }

13.  }
14.  }

15.  }
16.  public  static  void main(String[] args) {
17.  int arr[] ={3,60,35,2,45,320,5};

18.  System.out.println("Array Before Bubble Sort");
19.  for(int i=0; i < arr.length; i++){
20.  System.out.print(arr[i] + " ");
21.  }
22.  System.out.println();

23.  bubbleSort(arr);//sorting array elements using bubble sort

24.  System.out.println("Array After Bubble Sort");
25.  for(int i=0; i < arr.length; i++){
26.  System.out.print(arr[i] + " ");
27.  }

28.  }
29.  }
# Selection Sort
1.  public  class SelectionSortExample {
2.  public  static  void selectionSort(int[] arr){
3.  for (int i = 0; i < arr.length - 1; i++)
4.  {
5.  int index = i;
6.  for (int j = i + 1; j < arr.length; j++){
7.  if (arr[j] < arr[index]){
8.  index = j;//searching for lowest index
9.  }
10.  }
11.  int smallerNumber = arr[index];
12.  arr[index] = arr[i];
13.  arr[i] = smallerNumber;
14.  }
15.  }

16.  public  static  void main(String a[]){
17.  int[] arr1 = {9,14,3,2,43,11,58,22};
18.  System.out.println("Before Selection Sort");
19.  for(int i:arr1){
20.  System.out.print(i+" ");
21.  }
22.  System.out.println();

23.  selectionSort(arr1);//sorting array using selection sort

24.  System.out.println("After Selection Sort");
25.  for(int i:arr1){
26.  System.out.print(i+" ");
27.  }
28.  }
29.  }
# Insertion Sort
1.  public  class InsertionSortExample {
2.  public  static  void insertionSort(int array[]) {
3.  int n = array.length;
4.  for (int j = 1; j < n; j++) {
5.  int key = array[j];
6.  int i = j-1;
7.  while ( (i > -1) && ( array [i] > key ) ) {
8.  array [i+1] = array [i];
9.  i--;
10.  }
11.  array[i+1] = key;
12.  }
13.  }

14.  public  static  void main(String a[]){
15.  int[] arr1 = {9,14,3,2,43,11,58,22};
16.  System.out.println("Before Insertion Sort");
17.  for(int i:arr1){
18.  System.out.print(i+" ");
19.  }
20.  System.out.println();

21.  insertionSort(arr1);//sorting array using insertion sort

22.  System.out.println("After Insertion Sort");
23.  for(int i:arr1){
24.  System.out.print(i+" ");
25.  }
26.  }
27.  }
# Linear Search
1.  public  class LinearSearchExample{
2.  public  static  int linearSearch(int[] arr, int key){
3.  for(int i=0;i<arr.length;i++){
4.  if(arr[i] == key){
5.  return i;
6.  }
7.  }
8.  return -1;
9.  }
10.  public  static  void main(String a[]){
11.  int[] a1= {10,20,30,50,70,90};
12.  int key = 50;
13.  System.out.println(key+" is found at index: "+linearSearch(a1, key));
14.  }
15.  }
# Binary Search
1.  class BinarySearchExample{
2.  public  static  void binarySearch(int arr[], int first, int last, int key){
3.  int mid = (first + last)/2;
4.  while( first <= last ){
5.  if ( arr[mid] < key ){
6.  first = mid + 1;
7.  }else  if ( arr[mid] == key ){
8.  System.out.println("Element is found at index: " + mid);
9.  break;
10.  }else{
11.  last = mid - 1;
12.  }
13.  mid = (first + last)/2;
14.  }
15.  if ( first > last ){
16.  System.out.println("Element is not found!");
17.  }
18.  }
19.  public  static  void main(String args[]){
20.  int arr[] = {10,20,30,40,50};
21.  int key = 30;
22.  int last=arr.length-1;
23.  binarySearch(arr,0,last,key);
24.  }
25.  }