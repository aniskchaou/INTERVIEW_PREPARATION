   function factorial (n) {
    var res=BigInt(1);
    for (var i = 1n; i <= n; i++) {
        res=BigInt(res*i);
    };
    return res;
 }

 function numberCombinaison (n) {
    return  Number(factorial(n)/(factorial(n-2)*factorial(2)));
 }

console.log(numberCombinaison (4));