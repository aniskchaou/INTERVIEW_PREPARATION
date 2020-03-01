  function sumFactor(n) {
    var sum=0;
    for (var i = 1; i <= n; i++) {
        if (n%i==0) {
            sum+=i;
        };
      }
        return sum;
}
console.log(sumFactor(15));