
## The Window Object

The window object is supported by all browsers. It represents
the browser's window.

**Window Size**

 - **window.innerHeight** - the inner height of the browser window (in pixels)
 - **window.innerWidth** - the inner width of the browser window (in pixels)
 - **window.open()**  open a new window List item
 - **window.close()** - close the current window
 - **window.moveTo()** - move the current window
 - **window.resizeTo() -** resize the current window

## Variables

    var x=5;
    
    var y=6;
    
    var z=x+y;
    
    console.log("resultat : "+z);



**redeclaring javascript variables**

    var carName ="Volvo";
    
    var carName
    
    console.log(carName);

**data type**

    var length=16; //Number
    
    var lastName="John" //String
    
    var x={firstName:"John",lastName:"Adams"};
    
    console.log(x.firstName+" "+x.lastName);



**arithmetic operations**

 

       var x=5+6+7
        
        var x="John"+" "+"Adams"
        
        var x="5"+5+6
        
        var x="5"+(5+6)

output

    18
    
    John Adams
    
    556
    
    511


## Intervals
 **window.setTimeout()** 
 - The first parameter is a function to be executed.
 - The second parameter indicates the number of milliseconds before
   execution.

< button onclick="setTimeout(myFunction, 3000)">Try it< /button>

function myFunction() {

alert('Hello');

}

**clearTimeout()** method stops the execution of the function specified in setTimeout().

    myVar = setTimeout(function, milliseconds);
    
    clearTimeout(myVar);

 **setInterval()** 

 **window.setInterval()** method can be written without the window prefix.

 - The first parameter is the function to be executed.
 - The second parameter indicates the length of the time-interval
   between each execution.


    var myVar = setInterval(myTimer, 1000);
    
    function myTimer() {
    
    var d = new Date();
    
    document.getElementById("demo").innerHTML = d.toLocaleTimeString();
    
    }

 **clearInterval()** method stops the executions of the function specified in the setInterval() method.
 

## Browser Object Model

 - document
 - history
 - screen
 - navigator
 - location

## Strings

**//length**

    var ch="ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    
    console.log(ch.length)

**//locate**

    var str = "Please locate where 'locate' occurs!";
    
    var pos = str.search("locate");
    
    console.log(pos);

**//indexOf**

    var str = "Please locate where 'locate' occurs!";
    
    var pos = str.indexOf("locate");

**//lastIndexOf**

    var str = "Please locate where 'locate' occurs!";
    
    var pos = str.lastIndexOf("locate");
    
    // 21

//Both indexOf(), and lastIndexOf() return -1 if the text is not found

    var str = "Please locate where 'locate' occurs!";
    
    var pos = str.lastIndexOf("John");
    
    //-1
    
    //Both methods accept a second parameter as the starting
    
    var str = "Please locate where 'locate' occurs!";
    
    var pos = str.indexOf("locate",15);

**//search()**

    var str = "Please locate where 'locate' occurs!";
    
    var pos = str.search("locate");

**//slice()**

    var str = "Apple, Banana, Kiwi";
    
    var res = str.slice(7, 13);
    
    // Banana
    
    var str = "Apple, Banana, Kiwi";
    
    var res = str.slice(-12, -6);
    
    //Banana
    
    var res = str.slice(7);
    
    var res = str.slice(-12);
    
    // Banana, Kiwi

**//substring**

    var str = "Apple, Banana, Kiwi";
    
    var res = str.substring(7, 13);
    
    //--> Banana

**//substr**

    var str = "Apple, Banana, Kiwi";
    
    var res = str.substr(7, 6);
    
    //-->Banana
    
    var str = "Apple, Banana, Kiwi";
    
    var res = str.substr(7);

**//replace**

    str = "Please visit Microsoft!";
    
    var n = str.replace("Microsoft", "W3Schools");

**//toUpperCase**

    var text1 = "Hello World!";
    
    var text2 = text1.toUpperCase();

**//concat**

    var text = "Hello" + " " + "World!";
    
    var text = "Hello".concat(" ", "World!");

**//trim**

    var str = " Hello World! ";
    
    str.trim();

**//charAt**

    var str = "HELLO WORLD";
    
    str.charAt(0); // returns H
    
    var str = "Hello";
    
    var arr = str.split("");
    
    var text = "";
    
    var i;
    
    for (i = 0; i < arr.length; i++) {
    
    text += arr[i] + "<br>"
    
    }

## Strict Mode



    "use strict";
    
    myFunction();
    
    function myFunction() {
    
    y = 3.14; // This will also cause an error because y is not declared
    
    }

## Scope

**Local JavaScript Variables**



    function fonction () {
    
    var local_variable=0;
    
    }


**Global JavaScript Variables**

    var global_variables=0;
    
    function fonction (argument) {
    
    // body...
    
    }

**Automatically Global**

If you assign a value to a variable that has not been declared, it will automatically become a GLOBAL variable.

    function fonction (argument) {
    
    local_variable=0
    
    }

In a web browser, global variables are deleted when you close the browser window (or tab), but remain

## Objects

    var person = {
    
    firstName:"John",
    
    lastName:"Doe",
    
    age:50,
    
    eyeColor:"blue"
    
    };
    
    var person = {
    
    firstName: "John",
    
    lastName : "Doe",
    
    id : 5566,
    
    fullName : function() {
    
    return this.firstName + " " + this.lastName;
    
    }
    
    };
    
    name = person.fullName();

## numbers

    var x = 123;
    
    var y = new Number(123); // typeof x returns number
    
    // typeof y returns object
    
    var x = 500;
    
    var y = new Number(500); // (x == y) is true because x and y have equal values
    
    var x = new Number(500);
    
    var y = new Number(500); // (x == y) is false because objects cannot be compared
    
    toString() var x = 123;
    
    x.toString(); // returns 123 from variable x
    
    (123).toString(); // returns 123 from literal 123
    
    (100 + 23).toString(); // returns 123 from expression 100 + 23 toExponential()
    
    var x = 9.656; x.toExponential(2); // returns 9.66e+0 x.toExponential(4); // returns 9.6560e+0
    
    x.toExponential(6); // returns 9.656000e+0

 

## Math Object

**Math.PI;** // returns 3.141592653589793

**Math.round()**

Math.round(4.7); // returns 5

Math.round(4.4); // returns 4

**Math.pow()**

Math.pow(8, 2);

**Random JavaScript**

**Math.random();**

Math.floor(Math.random() * 11); // returns a random integer from 0 to 10

Math.floor(Math.random() * 101); // returns a random integer from 0 to 100

## Window

 **window.location** 

window.location.href returns the href (URL) of the current page window.location.hostname returns the domain name of the web host

**window.location.pathname** 

**window.location.assign** 

**window.location.href** 

**window.location.hostname** 

**window.location.pathname** 

**window.location.protocol** 

**window.location.port** 

 **window.location.assign()** method loads a new document.

    function newDoc() {
    
    window.location.assign("https://www.w3schools.com")
    
    }

## JSON

 **Storing**

    var myObj = {
    
    name: "John",
    
    age: 31,
    
    city: "New York"
    
    };
    
    myJSON = JSON.stringify(myObj);
    
    localStorage.setItem("testJSON", myJSON);

 **Retrieving data:**

    text = localStorage.getItem("testJSON");
    
    obj = JSON.parse(text);
    
    document.getElementById("demo").innerHTML = obj.name;

 returns John

    person.name;

returns John

    person["name"];

## Functions

    function multiplication (a,b) {
    
    return a*b;
    
    }
    
    function sayHello (name) {
    
    console.log("Hello "+name);
    
    }

sayHello("World");

var x=multiplication(3,4);





## Events

    < button onclick="document.getElementById('demo').innerHTML = Date()">The time is?< /button>
    
    < button onclick="displayDate()">The time is?< /button>


**onclick** occurs when element is clicked.

**ondblclick** occurs when element is double-clicked.

**onfocus** occurs when an element gets focus such as button, input, textarea etc.

**onblur** occurs when form looses the focus from an element.

**onsubmit** occurs when form is submitted.

**onmouseover** occurs when mouse is moved over an element.

**onmouseout** occurs when mouse is moved out from an element (after moved over).

**onmousedown** occurs when mouse button is pressed over an element.

**onmouseup** occurs when mouse is released from an element (after mouse is pressed).

**onload** occurs when document, object or frameset is loaded.

**onunload** occurs when body or frameset is unloaded.

**onscroll** occurs when document is scrolled.

**onresized** occurs when document is resized.

**onreset** occurs when form is reset.

**onkeydown** occurs when key is being pressed.

**onkeypress** occurs when user presses the key.

**onkeyup** occurs when key is released.

## DOM

    document.getElementById('button').addEventListener('click',createH1);
    
    function createH1 (argument) {
    
    var container=document.getElementById('container');
    
    var h1=document.createElement("h1");
    
    var text=document.createTextNode("hello world !");
    
    h1.appendChild(text);
    
    container.appendChild(h1);
    
    }
    var paragraphs=document.getElementsByTagName('p')
    
    console.log(paragraphs[0].innerHTML);
    
    console.log(paragraphs[1].innerHTML);
    
    document.getElementsByTagName('p')[0].innerHTML="hello world ! "
    document.getElementById('button').addEventListener('click',clicked);
    
    function clicked () {
    
    console.log("clicked");
    
    }
    
    document.getElementById('button').onclick=function clicked (argument) {
    
    console.log("clicked 2");
    
    }

## Display

**//innerHTML**

    document.getElementById("demo").innerHTML = 5 + 6;

**document.write()**

    document.write(5 + 6);

//Using document.write() after an HTML document is loaded, will delete all existing HTML

**window.alert()**

    window.alert(5 + 6);

**console.log()**

    console.log(5 + 6);

**//Using innerHTML**

    document.getElementById("demo").innerHTML = 5 + 6;

**document.write()**

    document.write(5 + 6);

//Using document.write() after an HTML document is loaded, will delete all existing HTML

**window.alert()**

    window.alert(5 + 6);

**console.log()**

    console.log(5 + 6);

## Date

    Date var d = new Date();
    
    var d = new Date(2018, 11, 24, 10, 33, 30);
    
    var d = new Date("October 13, 2014 11:13:00");
    
    var d = new Date(0); var d = new Date(86400000);
    
    d = new Date(); var d = new Date("2015-03");
    
    var d = new Date("2015-03-25");

getFullYear() //Get the year as a four digit number (yyyy)

getMonth() //Get the month as a number (0-11)

getDate() //Get the day as a number (1-31)

getHours() //Get the hour (0-23)

getMinutes() //Get the minute (0-59)

getSeconds() //Get the second (0-59)

getMilliseconds() //Get the millisecond (0-999)

getTime() //Get the time (milliseconds since January 1, 1970)

getDay() //Get the weekday as a number (0-6)

Date.now() //Get the time. ECMAScript 5.

## Conversion



    var x = 123;
    
    x.valueOf(); // returns 123 from variable x
    
    (123).valueOf(); // returns 123 from literal 123
    
    (100 + 23).valueOf(); // returns 123 from expression 100 + 23

## Number

    Number(true); // returns 1
    
    Number(false); // returns 0
    
    Number("10"); // returns 10
    
    Number(" 10"); // returns 10
    
    Number("10 "); // returns 10
    
    Number(" 10 "); // returns 10
    
    Number("10.33"); // returns 10.33
    
    Number("10,33"); // returns NaN
    
    Number("10 33"); // returns NaN
    
    Number("John"); // returns NaN

**//parseInt()**

    parseInt("10"); // returns 10
    
    parseInt("10.33"); // returns 10
    
    parseInt("10 20 30"); // returns 10
    
    parseInt("10 years"); // returns 10
    
    parseInt("years 10"); // returns NaN

**//parseFloat()**

    parseFloat("10"); // returns 10
    
    parseFloat("10.33"); // returns 10.33
    
    parseFloat("10 20 30"); // returns 10
    
    parseFloat("10 years"); // returns 10
    
    parseFloat("years 10"); // returns NaN



## history

 window.history 

 - history.back() 

 - history.forward()



## screen

 - screen.width
 - screen.height
 - screen.availWidth
 - screen.availHeight

 










