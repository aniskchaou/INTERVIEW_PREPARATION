

## css acronym
**CSS** is the **acronym** of “Cascading Style Sheets”.
/* Commentaire ici */

## basics

**< link rel="stylesheet" type="text/css" href="style.css"/>**
_**< style type="text/css"> Ici le code CSS < /style>**_
**< body style="margin:0px;">**

## bold

    p.normal {  
    font-weight:  normal;  
    }  
      
    p.thick {  
    font-weight:  bold;  
    }  
      
    p.thicker {  
    font-weight:  900;  
    }


## prefixes
_-webkit-_transition: all 4s ease;  
_-moz-_transition: all 4s ease;  
_-ms-_transition: all 4s ease;  
_-o-_transition: all 4s ease;  
transition: all 4s ease;

-moz-border-radius: 10px 5px;  
-webkit-border-top-left-radius: 10px;  
-webkit-border-top-right-radius: 5px;  
-webkit-border-bottom-right-radius: 10px;  
-webkit-border-bottom-left-radius: 5px;  
border-radius: 10px 5px;
## colors
body  { color: rgb(255, 0, 0); }
body  { color: rgba(255, 0, 0, 0.5); }
body  { color: red; }
body  { color: #FF0000; }
## selector

**Les classes**

< p>Voici un texte  **< span class="greenboldtext">**  avec une phrase en gras et vert alors que le reste ne change pas  **< /span>**  < /p>

 
.greenboldtext{  
font-size: small;  
color: #008080;  
font-weight: bold;  
}




**ID**  
**< div id="container">**  Ici le code HTML relatif au contenu..  **< /div>**

**cote CSS**  
#container{  
width: 80%;  
padding: 20px;  
border: 1px solid #666;  
background: #ffffff;  
}

Remarque : On utilise un # pour les id et un "." pour les classes.
default display

## margin

**margin** Marges extérieures de l'élément.  

    margin: 25px 50px 75px 100px;
    
    -   top margin is 25px
    -   right margin is 50px
    -   bottom margin is 75px
    -   left margin is 100px
    padding

## expression order

## z-index

z-index: auto|_number_|initial|inherit;
rule stacking
