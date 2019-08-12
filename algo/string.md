
## comparer 2 chaines
**idea**

    fonction comparer(chaine1, chaine2)
       si taille(chaine1) != taille(chaine2)
              sortir
        pour i=0 jusqua taille(chaine1)
           si chaine1[i] !=chaine2[j] alors
                 sortir

**algo**
 

       public static boolean compare(String x, String y){
           
            if(x.length()!=y.length())
                return false;
     
            for (int i = 0; i <x.length() ; i++) {
                if(x.charAt(i)!=y.charAt(i))
                    return false;
            }
            
            return true;
        }

    

## frequence d(apparition

    public class FrequenceApparition {
    
        public static void main(String[] args) {
            // Un algorithme qui permet d’afficher la fréquence d’apparition de s1 dans s:
            
            //initialisation
            String s = "sdfsd sdfsdf sdfsdf sdfs f ";
            String s1 = "sdfsd";
            String s2 = "";
            int fre = 0;
            
            //algorithme
            for (int i = 0; i < s.length(); i++) {
                if (s.indexOf(s1) != 0) {
                    fre++;
                }
            }
           
            //affichage
            System.err.println("frequence :  " + fre);
    
        }
    }

## inverser une chaine
**idea**

    chaine_normal ="hello"
    chaine_inverse=""
    tab_caractere[]=chaine_normal 
    
    pour i=taille(tab_caractere)-1 jusqua i>=0
            chaine_inverse = chaine_inverse + tab_caractere[i]

**algo**

            String chaine = "hello world";
            char[] inputStringArray = chaine.toCharArray();
            String reverseString = "";
    
            for (int i = inputStringArray.length - 1; i >= 0; i--) {
                reverseString += inputStringArray[i];
            }
    
            System.err.println("" + reverseString);

## inverser une phrase
**idea**
pour i=0 jusqua taille(chaine)
**algo**
 

     String chaine = "I love Java Programming"; 
            String[] temp = chaine.split(" ");
            String result = ""; 
      
    
            for (int i = 0; i < temp.length; i++) {
                
                if (i == temp.length - 1) 
                    result = temp[i] + result; 
                else
                    result = " " + temp[i] + result; 
            } 
            
            System.out.println(result);
    
## consonne voyelle
**idea**

    chaine[]="hello"
    tab_voyelle[]=[a,e,i,o,u]
    tab_consonne[]=[a,b,c,d,f]
    nb_consonne=0
    nb_voyelle=0
    
    pour i=0 jusqua taille(chaine)
          pour j=0 jusqua taille(tab_voyelle)
              si chaine[i]=tab_voyelle[j] alors
                 voyelle=voyelle+1
                 
         pour k=0 jusqua taille(tab_consonne)
              si chaine[i]=tab_consonne[k] alors
                 consonne=consonne+1     

   
**algo**

            char[] input = "hello world"
            char[] voyelle = "aeiouy".toCharArray();
            char[] consonne ="abcdfghjklmnpqrstvxz".toCharArray();
            int cons = 0;
            int voy = 0;
            
    
            //algorithme
            for (int i = 0; i < input.length; i++) {
                for (int j = 0; j < voyelle.length; j++) {
                    if (input[i] == voyelle[j]) {
                        voy++;
                    }
                }
    
                for (int j = 0; j < consonne.length; j++) {
                    if (input[i] == consonne[j]) {
                        cons++;
                    }
                }
    
            }
            
            System.err.println("consonne " + cons);
            System.err.println("voyelle " + voy);
    

## palindrome
**idea**

    debut =0
    fin = taille(chaine)-1
    
    tant que debut< fin
          si chaine[i] !=chaine[j]  alors
           sortir
    debut++
    fin--

**algo**

    public static boolean isPalindrome(String s) {
        
                int i = 0;
                int j = s.length() - 1;
        
                while (i < j) {
                    if (s.charAt(i) != s.charAt(j)) {
                        return false;
                    }
        
                    i++;
                    j--;
                }
                return true;
            }

## miniscule majuscule

idea

algo

    char maj[] = {'A', 'B', 'Z'};
    char min[] = {'a', 'b', 'z'};
    String input = "abz";
    char[] char_array = input.toCharArray();

    
    for (int k = 0; k < char_array.length; k++) {
        for (int l = 0; l < min.length; l++) {
            if (min[l] == char_array[k]) {
                char_array[k] = maj[l];
            }
        }
    }

    //affichage
    String res = new String(char_array);

