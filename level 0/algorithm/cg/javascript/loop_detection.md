    var fromIds=[2,6,9];
    var toIds=[6,9,5];
    var startPoint=2;
    
    function hasLoop (fromIds,toIds) {
        for (var i = 0; i < fromIds.length; i++) {
            fromIds[i]
            if (fromIds[i]==toIds[i]) {
                return 1;
            };
        };
    
        return 0;
    }
    function getIndex (elem,arr) {
        for (var i = 0; i < arr.length; i++) {
            if (elem==arr[i]) {
                return i;
            };
        };
    
        return -1;
    }
    
    function findNetworkEndPoint (startPoint,fromIds,toIds) {
    if ( hasLoop (fromIds,toIds)==0) {
      var index=getIndex(startPoint,fromIds)
      if (index==-1) {
        console.log("end point "+startPoint);
                    return;
      };
      findNetworkEndPoint(toIds[index],fromIds,toIds);
    };
    }
    
    findNetworkEndPoint(startPoint,fromIds,toIds);
