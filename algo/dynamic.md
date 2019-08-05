

## programmation dynamique

## somme des digits

    public class RecursiveDigitSum {
        
      
        static int sum_of_digit(int n) 
        {  
              System.out.println("nb  "+n); 
            if (n == 0) 
                return 0; 
            
             System.out.println("nb/10  "+n / 10);
             System.out.println("nb%10  "+n % 10);
             
            return (n % 10 + sum_of_digit(n / 10)); 
        } 
      
        
        public static void main(String args[]) 
        { 
            int num = 12345; 
            int result = sum_of_digit(num); 
            System.out.println("Sum of digits in " +  num + " is " + result); 
        } 
    }

## suite fibonacci

    class Fibonacci 
    { 
        static int fib(int n) 
        { 
        if (n <= 1) 
           return n; 
        
        return fib(n-1) + fib(n-2); 
        } 
           
        public static void main (String args[]) 
        { 
        int n = 9; 
        System.out.println(fib(n)); 
        } 
    } 

## permutation

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

## rendre monnaie

    public class RendreMonnaie {
       public static final int[] CENTIMES = {500, 200, 100, 50, 20, 10, 5, 2, 1};
    
    public static int[] monnaie(int centimes)
    {
        int[] rendu = new int[CENTIMES.length];
        
        for (int i = 0; i < CENTIMES.length; i++ )
        {
            rendu[i] = centimes / CENTIMES[i];
            centimes %= CENTIMES[i];
        }
        
        return rendu;
    }
    
    public static void afficher(int[] rendu)
    {
        for (int i = 0; i < CENTIMES.length; i++ )
            if (rendu[i] != 0)
                System.out.printf("%d pièces de %d centimes\n", rendu[i], CENTIMES[i]);
    }
    
    public static void main(String[] args)
    {
        int centimes = 4789;
        System.out.printf("Monnaie sur %d centimes :\n", centimes);
        afficher(monnaie(centimes));
    } 
    }

## puissance

    class power { 
        /* Function to calculate x raised to the power y */
        static int power(int x, int y) 
        { 
            if (y == 0) 
                return 1; 
            else if (y % 2 == 0) 
                return power(x, y / 2) * power(x, y / 2); 
            else
                return x * power(x, y / 2) * power(x, y / 2); 
        } 
      
        /* Program to test function power */
        public static void main(String[] args) 
        { 
            int x = 2; 
            int y = 3; 
      
            System.out.printf("%d", power(x, y)); 
        } 
    } 
