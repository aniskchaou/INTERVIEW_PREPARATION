    function duplicateRemoval(arr) {
        var temp=new Array(arr.length);
        var count=0;
        arr.sort();
        for (var i = 0; i < arr.length-1; i++) {
            if (arr[i]!=arr[i+1]) {
                temp[count++]=arr[i];
            };
        };
    
        temp[count++]=arr[arr.length-1];
        arr=new Array(count);
        for (var i = 0; i < count; i++) {
            arr[i]=temp[i];
        };
    
        return arr;
    }
