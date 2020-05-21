## join point
````
public static int computeJointPoint(int s1,int s2)
{
    if(s1>0&&s2>0)
    {
       while(s1<=20000000 && s2<=20000000)
     {
         s1 +=sommedigit(s1);
         s2 +=sommedigit(s2);
         if(s1==s2)
         {
             break;
            
            
         }
         
     } 
    }
     
     
     return s1;
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
````
