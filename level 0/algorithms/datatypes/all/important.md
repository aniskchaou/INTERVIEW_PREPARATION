

## largest

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

## average

     int arr[]={1,6,9,3,7};
            int somme=0;
            int n=arr.length;
            int moyenne= 0;
            
            for (int i = 0; i < arr.length; i++) {
                somme=somme+arr[i];
                
            }
            
            moyenne=somme/n;
            
            System.err.println(""+moyenne);






## duplicate removal

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






## approximation pi

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

## loop detection

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
       



## last digit power

    double num=0;
                if(n>0)
                {
                  num =Math.pow(2,n);
                  num=Math.floor(num%10);
                  result=(int)num;
                  
                }
    
                System.out.println(result);



## second number

     Arrays.sort(inputVector);
            
            result=inputVector[inputVector.length-2];
            
    







