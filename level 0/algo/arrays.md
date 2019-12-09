## arrays

## duplicate
**idea**

**algo**
  

       public static void duplicate(int[] arrA) {
                
                for (int i = 0; i < arrA.length; i++) {
                    for (int j = i + 1; j < arrA.length; j++) {
                     
                        if (arrA[i] == arrA[j]) {
                            System.out.println("duplicates : " + arrA[i]);
                        }
                        
                    }
                }
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
   

## recherche

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


            int tab[] = {1, 2, 3, 4, 5, 6, 7, 8, 9};
            int i = 0, j = tab.length - 1, x = 0;
            
            //algorithme
            while (i < j) {
                
                x = tab[j];
                
                tab[j] = tab[i];
                
                tab[i] = x;
                
                i++;
                j--;
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
            
          

## rotation tableau

    static void rotate(int [] arr){
        
        
        //récuperer le premier element
        int temp = arr[0];
        //decaler les autres éléments 
        for (int i = 1; i <arr.length ; i++) {
            arr[i-1] = arr[i];
        }
        //mettre le premier element a la derniere case
        arr[arr.length-1] = temp;
       
    
    }
## palindrome

    public static boolean isPalindrome(char[] array) {
            int j = array.length;
            for (int i = 0; i < array.length; i++) {
                //start
                int start = array[i];
                // end
                int end = array[--j];
    
                // check if elements till the middle have been compared
                if (j < i) {
                    return true;
                }
    
                // if start element is not the same as end element, the array is not
                // palindrome
                if (start != end) {
                    return false;
                }
            }
            // if the control reaches here, means all the elements were same 
            return true;
        }

## position élément dans un tableau
**idea**

    position=0
    input= 0
    pour i=0 jusqua taille(tab)
            si tab[0] == input alors
                position = i

**algo**

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
            
 

## matrice

## max matrice


            int matrice[][]=new int[4][4];
            int max=0;
            
            //algorithme
            for (int i = 0; i < 4; i++) {
                for (int j = 0; j < 4; j++) {
                    if (matrice[i][j]>max) {
                        max=matrice[i][j];
                    }
                }
            }
            

## proche de zero
**idea**

    near=tab[0]
    curr=0
    pour i=0 jusqua taille(tab)
            curr = tab[i] * tab[i]
              n=near * near    
            si curr <= n alors
               near=curr

**algo**

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
**idea**

    changement=1
    x=0
    tantque(changement==1)
          changement=0
          pour i=0 jusqua taille(tab)
                  si tab[i]>tab[i+1] alors
                     x = tab[i]
                     tab[i] = tab[i + 1]
                     tab[i + 1] = x
                     changement = 1
           
            
**algo**

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
    

