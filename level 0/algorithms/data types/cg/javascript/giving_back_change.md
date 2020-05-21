  ````
   var c = optimalChange(9223372036854775807);
 alert("coin2 " + c.coin2 + "  bill 5  " + c.bill5 + " bill 10  " + c.bill10)
var Change = {
   coin2: 0,
   bill5: 0,
   bill10: 0
 };

 function optimalChange(s) {
   if (s == 1 || s <= 0 || s > 9223372036854775807) {
     return null;
   }
   var c = rendumonnaie(s);
   return c;
 }

 function rendumonnaie(s) {
   var euros = [2, 5, 10];
   var rendu = new Array(3);
   if (s >= 10) {
     for (var i = rendu.length - 1; i >= 0; i--) {
       rendu[i] = Math.floor((s / euros[i]));
       s %= euros[i];
     }
   } else {
     for (var i = 0; i < rendu.length; i++) {
       rendu[i] = Math.floor(s / euros[i]);
       s %= euros[i];
     }

   }

   var c ={};
   c.bill10 = rendu[2];
   c.bill5 = rendu[1];
   c.coin2 = rendu[0];

   return c;
 }



````
