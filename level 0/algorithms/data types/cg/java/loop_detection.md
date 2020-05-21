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
       

