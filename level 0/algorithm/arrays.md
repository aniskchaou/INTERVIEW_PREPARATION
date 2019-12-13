
## Duplicate

     public static boolean hasDuplicate(int[] a)
        {
            boolean duplicate = false;
            
            for (int i = 0; i < a.length; i++) {
                for (int j = i+1; j < a.length; j++) {
                    if (a[i]==a[j]) {
                        duplicate= true;
                        break;
                    }
                }
            }
            return duplicate;
        }

## occurances

            int occurance=0;
            int  input=4;
            int tab[]={1,2,3,4,4,4};
            
    
            for (int i = 0; i < tab.length; i++) {
                if(tab[i]==input)
                {
                    occurance++;
                }  
            }
    
            System.err.println("nombre apparition "+occurance);
        }
   


## lineaire

    static void linearSearch(int[] input, int x) {

        for (int i = 0; i < input.length; i++) {
            if (x == input[i]) {
                return; //exit
            }
        }

        System.out.println("Element " + x + " is not found in array");
    }

## dichotomique

    public int runBinarySearchRecursively(
      int[] sortedArray, int key, int low, int high) {
        int middle = (low + high) / 2;
             
        if (high < low) {
            return -1;
        }
     
        if (key == sortedArray[middle]) {
            return middle;
        } else if (key < sortedArray[middle]) {
            return runBinarySearchRecursively(
              sortedArray, key, low, middle - 1);
        } else {
            return runBinarySearchRecursively(
              sortedArray, key, middle + 1, high);
        }
    }

## traitement

## fusionner 2 tableaux


            int tab1[] = {1, 2, 3};
            int tab2[] = {4, 5, 6};
            int k = 0;
            int tab3[] = new int[tab1.length + tab2.length];
    
            //for i=0
            for (int i = 0; i < tab1.length; i++) {
                tab3[i] = tab1[i];
            }
            //for j=tab.length
            for (int j = tab1.length; j < tab1.length + tab2.length; j++) {
                tab3[j] = tab2[k];
                k++;
            }


## inverser un tableaux


     public static int[] reverseArray(int[] a)
    {
        int[] temp=new int[a.length];
        int j=0;
        for (int i = a.length-1; i >=0; i--) {
            temp[j++]=a[i];
        }
        
        return temp;
    }

   

## calculer le minimum et maximum


            //initialisation
            int tab[] = {2, 6, 8, 8, 9, 10};
            int min = 0, max = 0;
    
            //algorithme
            for (int i = 0; i < tab.length; i++) {
                if (tab[i] < min) {
                    min = tab[i];
                } else if (tab[i] > max) {
                    max = tab[i];
                }
            }
    
  
## moyenne


            int somme = 0;
            int moyenne = 0;
            int[] tab = {1, 4, 6, 6, 3, 9, 3, 0, 3};
            
            //nombre d'elements
            int n = tab.length;
           
            //somme
            for (int j = 0; j < n; j++) {
                somme += tab[j];
            }
            //moyenne = somme/nombre
            moyenne = somme / n;
            
          


## Palindrome

     public static boolean isPalindrome(int[] a)
        {
            int j=a.length-1;
            boolean palindrome=true;
            for (int i = 0; i < a.length && j>=0 ; i++) {
                
                    if (a[i]!=a[j] ) {
                        System.err.println("i "+i+" "+j);
                        palindrome=false;
                        break;
                    }
                j--;
            }
            
            return palindrome;
        }

## position élément dans un tableau


            //initialisation
            int tab[]={1,2,3,4,5,6};
            int input=4;
            int pos=0;
            
            //algorithme
            for (int i = 0; i < tab.length; i++) {
                if (tab[i]==input) {
                    pos=i;
                }
            }
            
 

  

## proche de zero


        int[] data = {2,3,-2,-1};
        int curr = 0;
        int near = data[0]; 
        Arrays.sort(data);     

        for ( int i=0; i < data.length; i++ ){
            
             curr = data[i] * data[i]; 

             if ( curr <= (near * near) )  { 
                near = data[i];
             }     
        }
            
        

## tri

## tri bulle
 **idea**

     temp=0
    pour i=0 jusqua taille(tab)
          pour j=1 jusqua taille(tab)-i
             si tab[j-1] >tab[j] alors
                 tmp = tab[j - 1];  
                 tab[j - 1] = tab[j];  
                 tab[j] = tmp;

**algo**   
 

       static void tri_bulle(int[] tab) {
            int taille = tab.length;
            int tmp = 0;
            for (int i = 0; i < taille; i++) {
                for (int j = 1; j < (taille - i); j++) {
                    if (tab[j - 1] > tab[j]) {
                        //echanges des elements
                        tmp = tab[j - 1];
                        tab[j - 1] = tab[j];
                        tab[j] = tmp;
                    }
    
                }
            }
        }


## tri rapide


            //initialisation
            int i = 0;
            int x = 0;
            int[] tab = {3, 5, 6, 9, 3, 1, 5, 2};
           
            //pour continuer l'itération
            boolean changement = true;
    
            //algorithme
            while (changement) {
    
                changement = false;
    
                for (i = 0; i < tab.length - 1; i++) {
    
                    if (tab[i] > tab[i + 1]) {
                        
                        x = tab[i];
                        
                        tab[i] = tab[i + 1];
                        
                        tab[i + 1] = x;
                        
                        changement = true;
                    }
    
                }
            }
    

## sort the elements of an array in descending order.

     public static int[] sortDescending(int[] a) {
            Arrays.sort(a);
            int temp = 0;
            for (int i = 0; i < a.length; i++) {
                for (int j = i + 1; j < a.length; j++) {
                    if (a[i] < a[j]) {
                        temp = a[i];
                        a[i] = a[j];
                        a[j] = temp;
                    }
                }
            }
    
            return a;
        }

## right rotate the elements of an array

**Input:**

arr = [1, 2, 3, 4, 5]
Here, n determine the number of times an array should be rotated
      n = 3

**Output:**

Original array: 1 2 3 4 5
Array after right rotation: 3 4 5 1 2

    1.  public  static  void main(String[] args) {
    
    3.  //Initialize array
    4.  int [] arr = new  int [] {1, 2, 3, 4, 5};
    5.  //n determine the number of times an array should be rotated.
    6.  int n = 3;
    
    8.  //Displays original array
    9.  System.out.println("Original array: ");
    10.  for (int i = 0; i < arr.length; i++) {
    11.  System.out.print(arr[i] + " ");
    12.  }
    
    14.  //Rotate the given array by n times toward right
    15.  for(int i = 0; i < n; i++){
    16.  int j, last;
    17.  //Stores the last element of array
    18.  last = arr[arr.length-1];
    
    20.  for(j = arr.length-1; j > 0; j--){
    21.  //Shift element of array by one
    22.  arr[j] = arr[j-1];
    23.  }
    24.  //Last element of array will be added to the start of array.
    25.  arr[0] = last;
    26.  }
    
    28.  System.out.println();
    
    30.  //Displays resulting array after rotation
    31.  System.out.println("Array after right rotation: ");
    32.  for(int i = 0; i< arr.length; i++){
    33.  System.out.print(arr[i] + " ");
    34.  }
    35.  }

## Second Smallest Number in an Array

       public static int getSecondSmallest(int[] a, int total) {
            Arrays.sort(a);
            return a[1];
        } 

## left rotate the elements of an array

**Input**:

    arr = [1, 2, 3, 4, 5]

**Output**:

    Original array: 1 2 3 4 5
    Array after left rotation: 4 5 1 2 3

**Program**

      public static int[] leftRotation(int nbTimes, int[] a) {
    
            int j = 0;
            for (int i = 0; i < nbTimes; i++) {
                int first = a[0];
    
                for (j = 0; j < a.length - 1; j++) {
                    a[j] = a[j + 1];
                }
    
                a[j] = first;
            }
    
            return a;
        }

