

## css acronym
**CSS** is the **acronym** of “Cascading Style Sheets”.
/* Commentaire ici */

## basics

**< link rel="stylesheet" type="text/css" href="style.css"/>**
_**< style type="text/css"> Ici le code CSS < /style>**_
**< body style="margin:0px;">**

## syntax

selector { prop:value ;}
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

    .class  .intro  Selects all elements with class="intro"
   
    #id #firstname  Selects the element with id="firstname"
   
    *   *   Selects all elements
   
    element p   Selects all <p> elements
   
    element,element,..  div, p  Selects all <div> elements and all <p> elements


**Les classes**

< p>Voici un texte  **< span class="greenboldtext">**  avec une phrase en gras et vert alors que le reste ne change pas  **< /span>**  < /p>

 

    .greenboldtext{  
    font-size: small;  
    color: #008080;  
    font-weight: bold;  
    }
In this example only <p> elements with class="center" will be center-aligned:

    p.center  {  
    text-align:  center;  
    color:  red;  
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
**Group**
In this example we have grouped the selectors from the code above:

    h1, h2, p  {  
    text-align:  center;  
    color:  red;  
    }

## margin

**margin** **Marges extérieures** de l'élément.  

    margin: 25px 50px 75px 100px;
    
    -   top margin is 25px
    -   right margin is 50px
    -   bottom margin is 75px
    -   left margin is 100px
 **padding** : Marges extérieures
padding: 25px 50px 75px 100px;**

    -   top padding is 25px
    -   right padding is 50px
    -   bottom padding is 75px
    -   left padding is 100px

## expression order

    div#myRedDIV   {order: 2;}
    div#myBlueDIV  {order: 4;}
    div#myGreenDIV {order: 3;}
    div#myPinkDIV  {order: 1;}
    
    <div id="main">
      <div style="background-color:coral;" id="myRedDIV"></div>
      <div style="background-color:lightblue;" id="myBlueDIV"></div>
      <div style="background-color:lightgreen;" id="myGreenDIV"></div>
      <div style="background-color:pink;" id="myPinkDIV"></div>
    </div>

## z-index
éfinit l'ordre de superposition des éléments (dessus/dessous).
z-index: auto|_number_|initial|inherit;
rule stacking

## default display
 Block-level Elements

A block-level element always starts on a new line and takes up the full width available (stretches out to the left and right as far as it can).

The <div> element is a block-level element.

Examples of block-level elements:

    -   <div>
    -   <h1> - <h6>
    -   <p>
    -   <form>
    -   <header>
    -   <footer>
    -   <section>

----------

## Inline Elements

An inline element does not start on a new line and only takes up as much width as necessary.

This is  an inline <span> element inside  a paragraph.

Examples of inline elements:

    -   <span>
    -   <a>
    -   <img>

----------

## Display: none;

`display: none;`  is commonly used with JavaScript to hide and show elements without deleting and recreating them. Take a look at our last example on this page if you want to know how this can be achieved.

The  `<script>`  element uses  `display: none;`  as default.