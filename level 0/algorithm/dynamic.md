


## somme des digits


    static int sum_of_digit(int n) {
    
        if (n == 0) {
            return 0;
        }
    
        return (n % 10 + sum_of_digit(n / 10));
    }

 

## Giving change

   

    public static final int[] CENTIMES = {500, 200, 100, 50, 20, 10, 5, 2, 1};
    
        public static int[] monnaie(int centimes) {
            int[] rendu = new int[CENTIMES.length];
    
            for (int i = 0; i < CENTIMES.length; i++) {
                rendu[i] = centimes / CENTIMES[i];
                centimes %= CENTIMES[i];
            }
    
            return rendu;
        }
    
        public static void afficher(int[] rendu) {
            for (int i = 0; i < CENTIMES.length; i++) {
                if (rendu[i] != 0) {
                    System.out.printf("%d pièces de %d centimes\n", rendu[i], CENTIMES[i]);
                }
            }
        }

## Power

     static int power(int x, int y) 
     { 
                if (y == 0) 
                    return 1; 
                else if (y % 2 == 0) //pair
                    return power(x, y / 2) * power(x, y / 2); 
                else //impair
                    return x * power(x, y / 2) * power(x, y / 2); 
      } 



