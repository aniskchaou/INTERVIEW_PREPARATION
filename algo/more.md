## Factorial
**recurisive version:**

**idea**

    fonction fac(a1)
    si a<= 1
      retourner 1
    sinon 
     retourner a1* fac(a1-1)

**algo**
  

      int f(int a1)    
        {
           if (a1 <= 1)               
              return 1;                
           else                      
              return a1 * f(a1 - 1);  
        }

**Non-recursive version:**
**idea**

    pour i=1 jusqu'a n
      resultat = resultat * i

  
**algo**

    int fact(int n)
    {
     int i;
     int prod = 1;
     
     for (int i = 1; i <= n; i++) 
      prod *= i; 
      
       return prod; 
    }

## HeadingHeading Write a program to print all permutations of a given string


    Below are the permutations of string ABC.  
    ABC ACB BAC BCA CBA CAB
    
        // Java program to print all permutations of a 
        // given string. 
        public class Permutation 
        { 
            public static void main(String[] args) 
            { 
                String str = "ABC"; 
                int n = str.length(); 
                Permutation permutation = new Permutation(); 
                permutation.permute(str, 0, n-1); 
            } 
          
          
            private void permute(String str, int l, int r) 
            { 
                if (l == r) 
                    System.out.println(str); 
                else
                { 
                    for (int i = l; i <= r; i++) 
                    { 
                        str = swap(str,l,i); 
                        permute(str, l+1, r); 
                        str = swap(str,l,i); 
                    } 
                } 
            } 
          
           
            public String swap(String a, int i, int j) 
            { 
                char temp; 
                char[] charArray = a.toCharArray(); 
                temp = charArray[i] ; 
                charArray[i] = charArray[j]; 
                charArray[j] = temp; 
                return String.valueOf(charArray); 
            } 
          
        }

 

## Greatest Common Divisor

**idea**

    pgcd( nombre , diviseur)
    reste= nombre mod diviseur
    si reste = 0
    retourner diviseur
    sinon
    retourner pgcd(diviseur, reste)

**algo**

      int gcd(int a, int b)    
        {   
           int remainder = a % b;   
           if (remaider == 0)  
              return b; 
           else 
              return gcd(b, remainder); 
        }



## How to Find Square Root of a Number in Java
**idea**

    pour i=1 jusqu'a carre < n
    temp = i
     carre = temp * temp

  
**algo**
 

       public static float root(int number) {
            float root = 0.0f;
            float square = root;
            while (square < number) {
              root++;
              square = root * root;
            }
            return root;
          }

Output

    4
    square root: 2.0
    9
    square root: 3.0
    16
    square root: 4.0
    25
    square root: 5.0
    26
    square root: 6.0

  
  

## HeadingJava Program to print Prime numbers in Java
**idea**

    pour i=2 jusqua i<limite
         si est_primere(i) alors
            affiche(i)
   
   
    fonction est_primere(i)
       pour j=2 jusqua i<i
         si i mod j=0
           retouner faux
         sinon 
           retourner vrai  

**algo**
   

      public class PrimeNumberExample {
        
            public static void main(String args[]) {
        
                int limit = 100;
        
                for (int number = 2; number <= limit; number++) {
                    if (isPrime(number)) {
                        System.out.println(number);
                    }
                }
        
            }
        
            public static boolean isPrime(int number) {
                for (int i = 2; i < number; i++) {
                    if (number % i == 0) {
                        return false;  //number is divisible so its not prime_  
                    }
                }
                return true;  //number is prime now_  
            }
        }

  
**Output:**  

    Enter the number till which prime number to be printed:  
    20  
    Printing prime number from  1  to  20  
    2  
    3  
    5  
    7  
    11  
    13  
    17  
    19

## How to print Floyd's Triangle
**idea**

    nombre = 0
    pour i=1 jusqua nombredeligne
           pour j=1 jusqua i
                    afficher(nombre)
                    nombre=nombre+1
           retourligne()

**algo**

     public static void printFloydTriangle(int rows) {
                int number = 1;
                
         
                for (int i = 1; i <= rows; i++) {
                    
                    for (int j = 1; j <= i; j++) {
                        System.out.print(number + " ");
                        number++;
                    }
         
                    System.out.println();
                }
            }

 
**Output**

    Enter the number of rows of Floyd's triangle, you want to display
    5
    Floyd's triangle of 5 rows is :
    1
    2 3
    4 5 6
    7 8 9 10
    11 12 13 14 15

 



# How to print Pascal Triangle in Java

    public static void printPascalTriangle(int rows) {
                
                for (int i = 0; i < rows; i++) {
                    int number = 1;
                    System.out.printf("%" + (rows - i) * 2 + "s", "");
                    
                    for (int j = 0; j <= i; j++) {
                        System.out.printf("%4d", number);
                        number = number * (i - j) / (j + 1);
        
                    }
                    
                    System.out.println();
                }
            }

Output

   
               1
             1   1
           1   2   1
         1   3   3   1
    
    

## How to Find Prime Factors of Integer Numbers

  

     public static Set<Integer> primeFactors(long number) {
            Set<Integer> primefactors = new HashSet<>();
    
            for (int i = 2; i <= number; i++) {
    
                if (number % i == 0) {
                    primefactors.add(i);
                    number /= i;
                    i--;
                }
            }
            return primefactors;
        }

Output:

    Prime factors of number '35' are : [5, 7]
    Prime factors of integer '72' are : [2, 3]
    Prime factors of positive number '189' is : [3, 7]
    Prime factors of number '232321' are as follows : [4943, 47]
    Prime factors of number '67232321' are as follows : [12343, 419, 13]

## Heading How to Print Pyramid Pattern in Java?
**idea**

    pour i=0 jusqua nbligne
              pour j=0 jusqua nbligne-i
                     affiche (espace)
            
          pour k=0 jusqua k<= i
            affiche(*)  

**algo**

    public static void drawPyramidPattern(int rows) {
    
            for (int i = 0; i < rows; i++) {
               
                // '  '
                int nombreespace = rows - i;
                for (int j = 0; j < nombreespace; j++) {
                    System.out.print(" ");
                }
    
                // *
                for (int k = 0; k <= i; k++) {
                    System.out.print("* ");
                }
    
                System.out.println();
            }

## How to Find Duplicate Characters on String
**idea**

    tab_caratere[]=chaine_entree
    nb_caracetre_duplique=0
    pour i=0  jusqua taille(tab_caractere)
           pour j=i+1 jusqua taille(tab_caractere)
                 si tab_caractere[i]=tab_caractere[j]
                    nb_caractere_duplique=nb_caractere_duplique + 1
                    sortir

**algo**
   

    String str = "w3schools";
        int cnt = 0;
        char[] chartab = str.toCharArray();
        
        System.out.println("Duplicate Characters are:");
        
        
        for (int i = 0; i < chartab.length; i++) 
            
            for (int j = i + 1; j < chartab.length; j++) {
               
                if (chartab[i] == chartab[j]) {
                    System.out.println(chartab[j]);
                    cnt++;
                }
                
            }
    
    }

# Decimal to Binary Conversion in Java
**idea**

    fonction binaire(nombre)
       reste=0
       si nombre <=1 alors
          sortir
    
    reste = nombre mod 2
    binaire (nombre >> 1) 

**algo**
  

    private static void printBinaryform(int number) {
            int remainder;
    
            if (number <= 1) {
                System.out.print(number);
                return; 
            }
    
            remainder = number % 2;
            printBinaryform(number >> 1);
            System.out.print(remainder);
        }

 


## Count Number of Digits in an Integer using while loop

**idea**

     tant que nombre != 0
        nombre = nombre/ 10
         digit = digit + 1 

**algo**
  

    public static void main(String[] args) {
    
            int count = 0, num = 3452;
    
            while (num != 0) {
                num /= 10;
                ++count;
            }
    
            System.out.println("Number of digits: " + count);
    
        }

When you run the program, the output will be:

    Number of digits: 4














