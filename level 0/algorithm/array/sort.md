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



## Second Smallest Number in an Array

       public static int getSecondSmallest(int[] a, int total) {
            Arrays.sort(a);
            return a[1];
        } 

