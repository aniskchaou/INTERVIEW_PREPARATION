 function rangeSum (start,end,tab) {
    var sum=0;
    for (var i = 0; i < tab.length; i++) {
        if (i>=start && i<=end) {
            sum+=tab[i];
        };
    };
    return sum;
}