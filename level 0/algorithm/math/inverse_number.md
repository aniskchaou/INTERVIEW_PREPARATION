## Nombre inverse
**exemple**
123-->321
3+0=3
30+2=32
320+1=321
**algorithme**

      int num=123;
      int rest=0;
      int inverse=0;
        while (num!=0) {            
           rest=num%10;
           inverse= (inverse*10)+rest;
            num=num/10;
        }
        System.err.println(""+inverse);

