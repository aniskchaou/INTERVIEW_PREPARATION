largest

1)
        int arr[]={1,6,9,3,7};
        Arrays.sort(arr);
        System.err.println("max "+arr[arr.length-1]);
        System.err.println("min "+arr[0]);
2)
   int arr[]={1,6,9,3,7};
        int max=arr[0];
        int min =arr[0];
        
        for (int i = 0; i < arr.length; i++) {
            if(arr[i]>max)
            {
                max=arr[i];
            }
            
            if(arr[i]<min)
            {
                min=arr[i];
            }
        }
        
        System.err.println("max "+max+" min "+min);

average

 int arr[]={1,6,9,3,7};
        int somme=0;
        int n=arr.length;
        int moyenne= 0;
        
        for (int i = 0; i < arr.length; i++) {
            somme=somme+arr[i];
            
        }
        
        moyenne=somme/n;
        
        System.err.println(""+moyenne);


move to zero

 int arr[]={1,0,0,0,7};
        int res[]=new int[arr.length];
        int count=0;
        for (int i = 0; i < res.length; i++) {
           if(arr[i]!=0)
           {
             res[count++]=arr[i];  
           }
            
        }
        
        while (count<res.length) {            
            res[count]=0;
            
            count++;
        }
        
        System.out.println(Arrays.toString(res));


 range sum
 
  int arr[]={1,2,3,4,7};
       int start=1;
       int end = 3;
       int sum=0;
       
        if(start<arr.length && end <arr.length)
        {
            while (start<=end) {                
                sum+=arr[start];
                start++;
            }
            
            System.err.println("sum "+sum);
        }

duplicate removal
 int arr[]={1,2,3,4,7,2,7,3,5};
        Arrays.sort(arr);
        int temp[]=new int[arr.length];
        int count=0;
        
        for (int i = 0; i < arr.length-1; i++) {
            if(arr[i]!=arr[i+1])
            {
                temp[count++]=arr[i];
            }
        }
        
       temp[count++]=arr[arr.length-1];
       arr=new int[count];
        for (int i = 0; i < count; i++) {
           arr[i]=temp[i]; 
        }
        
        System.err.println(""+Arrays.toString(arr));

palindrome

    public static void main(String[] args) {
       int arr[]={1,2,3,9,3,2,1};
       boolean palindrome=true;
       int n=arr.length-1;
       int start=0;
       int end=0;
        for (int i = 0; i < arr.length; i++) {
            start=arr[i];
            end=arr[n];
            
            if(i>n)
            {
                palindrome=true;
                break;
            }
            
            if(start != end)
            {
                palindrome=false;
                break;
            }

            n--;
        }
        
        if(palindrome)
        {
            System.err.println("palindrome");
        }else
        {
            System.err.println("non palindrome");
        }
    }


    inverse
  public static void main(String[] args) {
       int arr[]={1,2,3,9};
       int temp=0;
       int j=arr.length;
       int i=0;
       
        while (i<j) {            
            temp=arr[i];
            arr[i]=arr[j];
            arr[j]=temp;
            i++;
            j--;
        }
    }
    
factoriel

 public static void main(String[] args) {
      int num=3;
      int fac=1;
      
        for (int i =1; i <= num; i++) {
            fac*=i;
        }
        
        System.err.println(""+fac);
        System.err.println(""+factoriel(num));
    }
    
   public static int factoriel(int num)
   {
       if (num==1) {
          return 1; 
       } else {
           return num*factoriel(num-1);
       }
   }
premier/non premier

public static void main(String[] args) {
      int num=6;
      boolean premier=true;
      
        for (int i = 2; i < Math.sqrt(num); i++) {
            if (num%i==0) {
                premier=false;
            }
            
           
        }
        
         if (premier) {
                System.err.println("premier");
            } else {
                System.err.println("non premier");
            }
    }

approximation pi

public static void main(String[] args) {
      int c=4;
      double pi=0.00;
      double n=1.00;
      
        for (int i = 0; i <= c; i++) {
            pi=pi+((4/n)-(4/(n+2)));
            n+=4;
        }
        
        System.err.println(""+pi);
    }             


import Foundation

var arr:[Int] = [1,0,0,0,7];
var res = [Int](repeating:0,count:arr.count)
var count :Int = 0;
var i:Int = 0
 while (i < res.count) {
    if(arr[i] != 0) {
        
    res[count] = arr[i]; 
    count = count+1 
    }
      i = i+1      
 }
        
        while (count<res.count) {            
            res[count]=0;
            
            count = count + 1;
        }

import Foundation

var  arr : [Int] = [1,2,3,4,7,2,7,3,5];
        arr.sort()
var  temp = [Int](repeating:0,count:arr.count)
    var count=0;
    var i = 0
        while( i < arr.count-1) {
            if(arr[i] != arr[i+1] )
            {
                temp[count]=arr[i];
                count = count + 1
            }

            i = i + 1
        }
        
       temp[count] = arr[arr.count-1];
       count = count + 1
       arr=[Int](repeating:0,count:count)
       var j = 0
        while(j < count) {
           arr[j] = temp[j];
           j = j + 1 
        }
        
        dump(arr)
join point

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

loop detection
 public static void main(String[] args) {
        int fomIds[]={2,6,9};
        int toIds[]={6,9,5};
        int startPoint=2;     
        findNetworkEndPoint(startPoint, fomIds, toIds);
    }
       
    public static void findNetworkEndPoint(int startPoint,int fomIds[], int toIds[])
    {
        if(hasLoop(startPoint, fomIds, toIds)==0)
        {
           int index=searchFrom(startPoint,fomIds) ;
        
        if(index==-1)
        {
            System.err.println("end point "+startPoint);
            return;
        }
        
        findNetworkEndPoint(toIds[index], fomIds, toIds);
       
  
        }
           }
       
    public static int searchFrom(int point,int startPoint[])
    {
        for (int i = 0; i < startPoint.length; i++) {
            if (startPoint[i]==point) {
                return i;
            } 
        }
        return -1;
    }
    
    
     public static int hasLoop(int point,int startPoint[], int toIds[])
    {
        for (int i = 0; i < startPoint.length; i++) {
            if (startPoint[i]==toIds[i]) {
                return 1;
            } 
        }
        return 0;
    }
       
check digits

public class Pi {
   
     public static int  res=0;
    public static void main(String[] args) {
        BufferedReader in;
        int result=0;
        try {
            
            int n = 2355;
          //  somme(n);
            

               System.err.println(""+somme(n));     
           // System.out.println(result);
        }
        catch (Exception e){
            e.printStackTrace();
        }
    }
    
    public static  int somme(int n)
    {
        
            int mod=0;
            int sum=0;
          while(n>0)
            {
              mod=n%10;
              sum=sum+mod;
              n=n/10;
              
            }
            
            if(sum>10)
            {
                return somme(sum);
            }else
            {
               return sum;
            }
    }
}



power of 2

import java.io.BufferedReader;
import java.io.File;
import java.io.FileReader;
import java.util.Arrays;
public class Main {
    /* The name of the class has to be Main. */
    public static void main(String[] args) {
        BufferedReader in;
        try {
            in = new BufferedReader(new FileReader(new File(args[0])));
            String line = null;
            int i = 0;
            int result = -1;
            line = in.readLine();
            int n = Integer.valueOf(line);
            
            if(n>0)
            {
                result=isPrime(n);
            }
            
            System.out.println(result);
        }
        catch (Exception e){
            e.printStackTrace();
        }
    }
    
    public static int  isPrime(int num)
    {
        if(num%2==0)
        {
            return 1;
        }else
        {
           return 0;            
        }
    }
}           

last digit power

double num=0;
            if(n>0)
            {
              num =Math.pow(2,n);
              num=Math.floor(num%10);
              result=(int)num;
              
            }

            System.out.println(result);

has duplicate

        result=hasDuplicate(n,inputVector);
        System.out.println(result);
    }
    
    public static int hasDuplicate(int n,int tab[])
    {
        for(int i=0;i<n;i++)
        {
            for(int j=i+1;j<n;j++)
            {
                
                    
                    if(tab[i]==tab[j])
                    {
                       return 1; 
                    }
                
            }
            
        }    
        return 0;
    }


list of    prime number        
public class Main {
    /* The name of the class has to be Main. */
    public static void main(String[] args) {
        int N;
        int[] result = null;

        try (Scanner scanner = new Scanner(new File(args[0]))) {
            N = Integer.parseInt(scanner.nextLine());
              
              int k=0;
            List<Integer> l=new ArrayList<Integer>();
             for(int i=2;i<N;i++){      
             if(isPrime(i)){
                 l.add(i);
             }
             }
             result=new int[l.size()];
             for(int i=0;i<l.size();i++)
             {
                 result[k++]=l.get(i);
             }

            for (int j = 0; j < result.length; j++) {
                System.out.print(result[j]);
                if (j < result.length - 1) {
                    System.out.print(" ");
                }
            }
            System.out.println();
        }
        catch (FileNotFoundException ex) {
            throw new RuntimeException(ex);
        }
    }
    
    static boolean isPrime(int n) 
{ 
// Corner case 
if (n <= 1) 
    return false; 
  
// Check from 2 to n-1 
for (int i = 2; i < n; i++) 
    if (n % i == 0) 
        return false; 
  
return true; 
}
}

second number
 Arrays.sort(inputVector);
        
        result=inputVector[inputVector.length-2];
        
        if(inputVector[inputVector.length-2]==inputVector[inputVector.length-1])
        {
            result=inputVector[inputVector.length-3];
        }    