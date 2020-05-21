## occurances
**input**

    a=[4,5,6] n=4

**output**

    1

**algorithm**

     public static int getOccurance(int a[],int n)
    {
        int occurance=0;
        for (int i = 0; i < a.length; i++) {
            if (a[i]==n) {
           occurance++; 
            }
        }
        
        return occurance;
    }

   
