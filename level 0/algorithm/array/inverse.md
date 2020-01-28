## inverser un tableaux


     public static int[] reverseArray(int[] a)
    {
        int[] temp=new int[a.length];
        int j=0;
        for (int i = a.length-1; i >=0; i--) {
            temp[j++]=a[i];
        }
        
        return temp;
    }

  