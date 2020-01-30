
## Position
**input**

    t=[4,5,6]        n=5

**output**

    1

**algorithm**

     public static int getPosition(int[] tab,int n)
       {
           for (int i = 0; i < tab.length; i++) {
               if (tab[i]==n) {
                   return i;
               }
           }
           
           return -1;
       } 
