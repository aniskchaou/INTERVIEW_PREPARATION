function toByteArray (str) {
    var strr=str.toLowerCase();
    var arr=[];
    for (var i = 0; i < str.length; i++) {
        arr.push(strr.charCodeAt(i));
        
    };
    arr.sort();
    
    return arr ;
}

function isTwin (str1,str2) {
    var arr=toByteArray (str1);
    var arr2=toByteArray (str2);
    str1=String.fromCharCode.apply(null, arr);
    str2=String.fromCharCode.apply(null, arr2);
    return str1===str2;
}