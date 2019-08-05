## arrays

## duplicate

    public class HelloWorld{
    
             public static void duplicate(int[] arrA) {
                for (int i = 0; i < arrA.length; i++) {
                    for (int j = i + 1; j < arrA.length; j++) {
                        if (arrA[i] == arrA[j]) {
                            System.out.println("duplicates : " + arrA[i]);
                        }
                    }
                }
        
            }
        
            public static void main(String[] args) {
                int a[] = {1, 2, 2};
                duplicate(a);
            }
        }

## occurances

    public class HelloWorld{
    
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
    }

## recherche

## lineaire

    public class HelloWorld{
    
        static void linearSearch(int [] input, int x){
    
            for (int i = 0; i <input.length ; i++) {
                if(x==input[i]) {
                    System.out.println("Element " + x + " is found at index: " + i);
                    return; //exit
                }
            }
            
            System.out.println("Element " + x + " is not found in array");
        }
    
        public static void main(String[] args) {
            int input [] = {20, 30, 40, 10, 5, 2, 60, 73};
            int x = 10;
            linearSearch(input, x);
    
        }}

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

    public class FusionnerTableau {

    
        public static void main(String[] args) {
    
            //initialisation
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
    
            //affichage
            for (int i = 0; i < tab3.length; i++) {
                System.err.println("" + tab3[i]);
    
            }
        }
    
    }

## inverser un tableaux

    public class InverserTableau {
    
        public static void main(String[] args) {
    
    //Un algorithme qui permet de inverser un tableau:
            
            //initialisation
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
            
           
            
            //affichage
            for (int k = 0; k < tab.length; k++) {
                System.err.println("" + tab[k]);
            }
        }
    }

## calculer le minimum et maximum

    public class MinMaxTableau {
    
        public static void main(String[] args) {
    
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
    
            //affichage 
            System.err.println("min " + min);
            System.err.println("max " + max);
        }
    
    }

## moyenne

    public class MoyenneTableau {
        //   Une fonction qui permet de renvoyer la moyenne d’un tableau’:
    
        public static void main(String[] args) {
            
            //initialtion
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
            
            //affichage
            System.err.println("moyenne " + moyenne);
    
        }
    
    }

## rotation tableau

    public class ArrayRotation {
    
        static void rotate(int [] arr){
            
            System.out.println("Original Array: " + Arrays.toString(arr));
           
            //si le tableau est vide --> sortir de la fonction
            if(arr==null || arr.length==0)
                return ;
            //récuperer le premier element
            int temp = arr[0];
            //decaler les autres éléments 
            for (int i = 1; i <arr.length ; i++) {
                arr[i-1] = arr[i];
            }
            //mettre le premier element a la derniere case
            arr[arr.length-1] = temp;
            
            //afficher le tableau
            System.out.println("Rotated Array: " +  Arrays.toString(arr));
            System.out.println("_______________________________");
        
        }
    
        
        
        public static void main(String[] args) {
            int [] arr = {1, 2, 3, 4, 5,6,8};
            rotate(arr);
            
        }

## palindrome

    public class Palindrome {
        
        public static void main(String[] args) {
            
            char[] tab={'a','b','b','a'};
            System.err.println(""+isPalindrome(tab));
        }
        
      public static  boolean isPalindrome(char[] array) {
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
     
    }

## position élément dans un tableau

    public class PositionElementTableau {
       // Un algorithme qui permet de renvoyer la position d’un élément dans un tableau:
        public static void main(String[] args) {
            
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
            
            //affichage
            System.err.println(""+pos);
        }
    
    }

## matrice

## max matrice

    public class PlusGrandElmentMatrice {
        
        public static void main(String[] args) {
            
            //initialisation
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
            
            //affichage
            System.err.println("max: "+max);
        }
      
    }

## proche de zero

    public class CloseToZero {
    
        public static void main(String[] args) {
    
            int[] data = {2,3,-2,-1};
            int curr = 0;
            int near = data[0]; 
            Arrays.sort(data);     
            System.out.println(Arrays.toString(data));
            
            
            for ( int i=0; i < data.length; i++ ){
                
                 curr = data[i] * data[i]; 
    
                 if ( curr <= (near * near) )  { 
                    near = data[i];
                 } 
                 
                System.err.println(curr+"<= "+(near * near)+" "+( curr <= (near * near) ));  
                System.err.println("i "+i);
                System.err.println("curr "+curr);
                System.err.println("near "+near);
                System.err.println("");
                
            }
            
            System.out.println( near );
        }
        
    }

## tri

## tri bulle

    public class TriBulle {
    
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
    
        static void displayTab(int[] tab) {
            for (int i = 0; i < tab.length; i++) {
                System.out.print(tab[i] + " ");
            }
            System.out.println();
        }
    
        public static void main(String[] args) {
            int arr[] = {84, 12, 1, 43, 5, 10};
    
            System.out.println("---Avant le tri a bulle---");
    
            displayTab(arr);
    
            // tri des elements de tableau avec le tri a bulle
            tri_bulle(arr);
    
            System.out.println("---Apres le tri a bulle---");
    
            displayTab(arr);
        }
    } 

## tri rapide

    public class TriRapide {

        public static void main(String[] args) {
            
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
    
            //affichage
            for (int j = 0; j < tab.length; j++) {
                System.err.println("" + tab[j]);
            }
        }
    
    }
