## comparer 2 chaines

public class CompareStrings {

    public static boolean compare(String x, String y){
        if(x==null || y==null){
            return false;
        }
        //compare lengths
        if(x.length()!=y.length())
            return false;

        //compare all characters
        for (int i = 0; i <x.length() ; i++) {
            if(x.charAt(i)!=y.charAt(i))
                return false;
        }
        //if here, means both strings are equal
        return true;
    }

    public static void main(String[] args) {
        String x = "tutorial";
        String  y = "tutorial";
       
    }
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

    public class InverserChaine {
    
        static String chaine = "anis";
    
        public static void main(String[] args) {
            
            //1) convertir chaine en tableau de caractere
            char[] inputStringArray = chaine.toCharArray();
           
            //2) variable pour mettre la chaine 
            String reverseString = "";
    
            //3) decompteur
            for (int i = inputStringArray.length - 1; i >= 0; i--) {
                reverseString += inputStringArray[i];
            }
            //4) afficher la chiane
            System.err.println("" + reverseString);
            
        }
    
        
    }

## inverser une phrase

    public class InverserPhrase {
        
        
        public static void main(String[] args) {
            
            //la chaine en entrée
            String chaine = "I love Java Programming"; 
    
           //découper la phrase en un ensemmble de mots
            String[] temp = chaine.split(" ");
           
            //resultat
            String result = ""; 
      
           //parcourir la tableau
            for (int i = 0; i < temp.length; i++) { 
                //si temp est le dernier mot
                if (i == temp.length - 1) 
                    //concatiner avec result 
                    result = temp[i] + result; 
                else
                    //mettre un espace avant 
                    result = " " + temp[i] + result; 
            } 
            
            System.out.println(result);
            
        }
      
      
    }

## consonne voyelle

    public class NombreConsonnesVoyelles {
    
        public static void main(String[] args) {
            
            //initialisation
            Scanner sc = new Scanner(System.in);
            char[] input = sc.next().toCharArray();
            char[] voyelle = "aeiouy".toCharArray();
            char[] consonne = "bcdfghjklmnpqrstvxz".toCharArray();
            int cons = 0;
            int voy = 0;
            int blanc = 0;
    
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
            
            //affichage
            System.err.println("consonne " + cons);
            System.err.println("voyelle " + voy);
    
        }
    }

## palindrome

    public class Palindrome {
    
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
    
        public static void main(String[] args) {
            System.err.println("" + isPalindrome("hello"));
        }
    
    }

## miniscule majuscule

    public class TransformerMinusculeMajuscule {
    
        public static void main(String[] args) {
            
            //initialisation
            char maj[] = {'A', 'B', 'Z'};
            char min[] = {'a', 'b', 'z'};
    
            Scanner sc = new Scanner(System.in);
            String input = sc.next();
            
            //algorithme
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
            System.out.println("resultat : " + res);
    
        }
    }
