## join point

     public static void main(String[] args) {
       
        System.err.println(somme(471,480));
        
    }
    
    public static int somme(int num,int num2)
    {
        
         while(num<=20000 && num2<=20000)
         {
             num +=sommedigit(num);
             num2 +=sommedigit(num2);
             if(num==num2)
             {
                 break;
                
                
             }
             
         }
         
         return num;
    }
    public static int sommedigit(int m)
    {
        int n=0;
        int sum=0;
         while(m > 0)
        {
            n = m % 10;
            sum = sum + n;
            m = m / 10;
        }
         
         return sum;
    }   