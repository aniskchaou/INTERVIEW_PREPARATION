
## fusionner 2 tableaux
**input**

    a=[1,2,3]
    b=[4,5,6]

**output**

    [1, 2, 3, 4, 5, 6]

**algorithm**

           public static int[] arrayFusion(int[] a,int[] b)
    {
        int c[]=new int[a.length+b.length];
        int k=0;
        for (int i = 0; i < a.length; i++) {
            c[i]=a[i];
        }
        
        for (int i = a.length; i < c.length; i++) {
            c[i]=b[k];
            k++;
        }
        
        return c;
    }


 
