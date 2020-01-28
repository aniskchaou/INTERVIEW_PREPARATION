## proche de zero


        int[] data = {2,3,-2,-1};
        int curr = 0;
        int near = data[0]; 
        Arrays.sort(data);     

        for ( int i=0; i < data.length; i++ ){
            
             curr = data[i] * data[i]; 

             if ( curr <= (near * near) )  { 
                near = data[i];
             }     
        }
            
        