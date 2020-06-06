## Compare 2 strings 

 

       public static boolean compare(String x, String y){
           
            if(x.length()!=y.length())
                return false;
     
            for (int i = 0; i <x.length() ; i++) {
                if(x.charAt(i)!=y.charAt(i))
                    return false;
            }
            
            return true;
        }

    
