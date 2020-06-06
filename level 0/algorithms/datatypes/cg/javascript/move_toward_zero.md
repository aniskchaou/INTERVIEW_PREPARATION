    function moveTowardZeros (arr) {
        var count=0;
    
        for (var i = 0; i < arr.length; i++) {
            if (arr[i]!=0) {
                arr[count++]=arr[i];
            };
        };
    
        while(count<arr.length)
        {
           arr[count++]=0;
        }
    
        return arr;
    }

