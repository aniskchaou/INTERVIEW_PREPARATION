 var euros=[50,20,10,5];
                                      
 function rendreMonnaie(montant)
{
var rendu=new Array(euros.length);
   for (var i=0;i<euros.length;i++)
   {
   rendu[i]=montant/euros[i];
    montant %= euros[i];
   }
   return rendu;                                   
}
                                      
var rendu=rendreMonnaie(55);
                                      
for(var j=0;j<rendu.length;j++)
{
  if(rendu[j]>=1)
 {
  print(Math.round(rendu[j])+"pieces de "+euros[j]+"euro");
                                      
 }
}