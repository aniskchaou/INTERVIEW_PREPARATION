function joinPoint (num1,num2) {
    

    while(num1<=20000 && num2<=20000)
    {
        var som=somme(num1);
        var som2=somme(num2);
         num1=parseInt(num1+som);
         num2=parseInt(num2+som2);
         
         if (num1==num2){

            break;
         };

    }
    return num1;
}

function somme (n) {
    var sum=0;

    while(n!=0)
    {
        sum+=parseInt(n%10);
        n=parseInt(n/10);
        
    }
    //sum=sum);
    return sum ;
}