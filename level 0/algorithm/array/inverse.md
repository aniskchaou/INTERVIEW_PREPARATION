
## inverser un tableaux
**input** 

    [4,5,6]

**output**

    [6,5,4]

**algorithm**

       public static int[] reverseArray(int[] a)
      {
          int[] res=new int[a.length];
          int k=0;
          for (int i = a.length-1; i >=0; i--) {
              res[k]=a[i];
              k++;
          }
          return res;
      }

  