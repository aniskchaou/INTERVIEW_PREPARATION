## giving change

```
public class A {

   static  class Change{
        long coin2=0;
        long bill5=0;
        long bill10=0;
    }
    
    static Change optimalChange(long s)
    {
        if(s==1 || s<=0||s>9223372036854775807l)
        {
            return null;
        }
        Change c=rendumonnaie(s);
        return c;
    }
    
    static Change rendumonnaie(Long s){
        int[] euros={2,5,10};
        Long[] rendu=new  Long[3];
        if(s>=10)
        {
            for (int  i=rendu.length-1; i>=0;i--) {
                rendu[i]=s/euros[i];
                s%=euros[i];
            }
        }else
        {for (int i = 0; i < rendu.length; i++) {
                rendu[i]=s/euros[i];
                s%=euros[i];
            }
            
        }
        
        Change c=new Change();
        c.bill10=rendu[2];
        c.bill5=rendu[1];
        c.coin2=rendu[0];
        
        return c;
    }
    
    public static void main(String[] args) {
       Change c= optimalChange(9223372036854775807l);
        System.err.println("coin2 "+c.coin2+"  bill 5  "+c.bill5+" bill 10  "+c.bill10);
    }
}
```
