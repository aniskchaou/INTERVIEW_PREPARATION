## Count Down

     public static void main(String[] args) {
            countDownNormal(5);
            
            countDownNormal(5);
        }
        
       static  void countDownNormal(int n)
        {
            for (int i = n; i > 0; i--) {
                System.out.println(i);
            }
        }
        
        void countDownrecursive(int n)
        {
            if(n==0)
              return;
            else     
                countDownNormal(n-1);
        }
