       function factorial (n) {
        var res=BigInt(1);
        for (var i = 1n; i <= n; i++) {
            res=BigInt(res*i);
        };
        return res;
     }
    
     function numberCombinaison (n) {
     if(n>=2 && n<=1000)
            {
                return  Number(factorial(n)/(factorial(n-2)*factorial(2)));
            }else
            {
                return 0;
            }
        
     }
    
    console.log(numberCombinaison (4));
