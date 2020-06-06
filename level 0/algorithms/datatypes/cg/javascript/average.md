     function average (arr) {
          
        var somme=0;
        var moyenne=0;
        
        for(var i=0;i<arr.length;i++)
        {
          somme+=arr[i];  
        }
        
        moyenne=somme/arr.length;
        
       return parseInt(moyenne);
         
    }
