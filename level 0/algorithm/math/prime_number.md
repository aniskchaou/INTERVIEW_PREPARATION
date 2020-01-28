## Nombre premier

     static void naiveMethod(int n){
           
            boolean isPrime = true;
            for (int i = 2; i <n ; i++) {
                if(n%i==0) {
                    isPrime = false;
                    break;
                }
            }
            if(isPrime)
                System.out.println(n);
        
        }
