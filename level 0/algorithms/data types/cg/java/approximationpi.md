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

         

