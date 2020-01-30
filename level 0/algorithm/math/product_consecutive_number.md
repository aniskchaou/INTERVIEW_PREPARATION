## Pronic number

A number is said to be pronic number if it is a product of two consecutive numbers.

For examples:

    6 = 2 x 3  
    72 = 8 x 9

**Input:**

    range(1, 101)

**Output:**

    2 6 12 20 30 42 56 72 90

**Algorithm**
     public static void isPronic(int start,int end)
      {
          for (int i = start; i <=100; i++) {
              if (productConsecutive(i)) {
                  System.out.println(i);
              }
          }
      }
      
      public static boolean productConsecutive(int n)
      {
          boolean product=false;
          for (int i = 1; i <n; i++) {
              if(i*(i+1)==n)
              {
                  product=true;
                  break;
              }
          }
          
          return product;
      }
    
    



    

