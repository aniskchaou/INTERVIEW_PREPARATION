
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

 
 

## Declaring JavaScript global variable within function

 you need to use  **window object**. For example:

 `window.value=90;`

Now it can be declared inside any function and can be accessed from any function. For example:

    1.  function m(){
    2.  window.value=100;//declaring global variable by window object
    3.  }
    4.  function n(){
    5.  alert(window.value);//accessing global variable from other function
    6.  }

## JavaScript Function Methods



**apply()**

It is used to call a function contains this value and a single array of arguments.

    1.  var array = [1,2,3,4];
    2.  var newarray=["One","Two","Three","Four"]
    3.  array.push.apply(array, newarray);
    4.  document.writeln(array);

**bind()**

It is used to create a new function.

**call()**

It is used to call a function contains this value and an argument list.

**toString()**

It returns the result in a form of a string.

# Object

## 1) JavaScript Object by object literal

 
    2.  emp={id:102,name:"Shyam Kumar",salary:40000}
    3.  document.write(emp.id+" "+emp.name+" "+emp.salary);

## 2) By creating instance of Object

    2.  var emp=new Object();
    3.  emp.id=101;
    4.  emp.name="Ravi Malik";
    5.  emp.salary=50000;
    6.  document.write(emp.id+" "+emp.name+" "+emp.salary);

## JavaScript Object Methods

**Object.assign()**

This method is used to copy enumerable and own properties from a source object to a target object

**Object.create()**

This method is used to create a new object with the specified prototype object and properties.




## JavaScript Array Methods



**concat()**

It returns a new array object that contains two or more merged arrays.

**copywithin()**
It copies the part of the given array with its own elements and returns the modified array.

**every()**

It determines whether all the elements of an array are satisfying the provided function conditions.

**fill()**

It fills elements into an array with static values.

**filter()**

It returns the new array containing the elements that pass the provided function conditions.

**find()**

It returns the value of the first element in the given array that satisfies the specified condition.

**findIndex()**

It returns the index value of the first element in the given array that satisfies the specified condition.

**forEach()**

It invokes the provided function once for each element of an array.

**includes()**

It checks whether the given array contains the specified element.

**indexOf()**

It searches the specified element in the given array and returns the index of the first match.

**join()**

It joins the elements of an array as a string.

**lastIndexOf()**

It searches the specified element in the given array and returns the index of the last match.

**map()**

It calls the specified function for every array element and returns the new array

**pop()**

It removes and returns the last element of an array.

**push()**

It adds one or more elements to the end of an array.

**reverse()**
It reverses the elements of given array.

**shift()**

It removes and returns the first element of an array.

**slice()**

It returns a new array containing the copy of the part of the given array.

**sort()**

It returns the element of the given array in a sorted order.

**splice()**

It add/remove elements to/from the given array.

**unshift()**

It adds one or more elements in the beginning of the given array.
## 1) JavaScript array literal


    2.  var emp=["Sonoo","Vimal","Ratan"];
    3.  for (i=0;i<emp.length;i++){
    4.  document.write(emp[i] + "<br/>");
    5.  }


## 2) JavaScript Array directly (new keyword)


    2.  var i;
    3.  var emp = new Array();
    4.  emp[0] = "Arun";
    5.  emp[1] = "Varun";
    6.  emp[2] = "John";
    
    8.  for (i=0;i<emp.length;i++){
    9.  document.write(emp[i] + "<br>");
    10.  }


## 3) JavaScript array constructor (new keyword)


    2.  var emp=new Array("Jai","Vijay","Smith");
    3.  for (i=0;i<emp.length;i++){
    4.  document.write(emp[i] + "<br>");
    5.  }



## By string object (using new keyword)


    2.  var stringname=new String("hello javascript string");
    3.  document.write(stringname);


## JavaScript String Methods



**charAt()**

It provides the char value present at the specified index.

**charCodeAt()**
It provides the Unicode value of a character present at the specified index.

**concat()**

It provides a combination of two or more strings.

**indexOf()**

It provides the position of a char value present in the given string.

**lastIndexOf()**

It provides the position of a char value present in the given string by searching a character from the last position.

**search()**

It searches a specified regular expression in a given string and returns its position if a match occurs.

**match()**

It searches a specified regular expression in a given string and returns that regular expression if a match occurs.

**replace()**

It replaces a given string with the specified replacement.

**substr()**

It is used to fetch the part of the given string on the basis of the specified starting position and length.

**substring()**

It is used to fetch the part of the given string on the basis of the specified index.

**slice()**

It is used to fetch the part of the given string. It allows us to assign positive as well negative index.

**toLowerCase()**

It converts the given string into lowercase letter.

**toLocaleLowerCase()**

It converts the given string into lowercase letter on the basis of host?s current locale.

**toUpperCase()**

It converts the given string into uppercase letter.

**toLocaleUpperCase()**

It converts the given string into uppercase letter on the basis of host?s current locale.

**toString()**

It provides a string representing the particular object.

**valueOf()**

It provides the primitive value of string object.
# JavaScript Math


## JavaScript Math Methods



abs()
acos()
asin()
atan()
cbrt()
ceil()
cos()
cosh()
exp()
floor()
hypot()
log()
max()
pow()
random()
round()
sign()
sin()
sinh()
sqrt()
tan()
tanh()
trunc()

## JavaScript Number Constants



**MIN_VALUE**

returns the largest minimum value.

**MAX_VALUE**

returns the largest maximum value.

**POSITIVE_INFINITY**

returns positive infinity, overflow value.

**NEGATIVE_INFINITY**

returns negative infinity, overflow value.

**NaN**

represents "Not a Number" value.

## JavaScript Number Methods



**isFinite()**

**isInteger()**
It determines whether the given value is an integer.

**parseFloat()**

It converts the given string into a floating point number.

**parseInt()**

It converts the given string into an integer number.

**toExponential()**

It returns the string that represents exponential notation of the given number.

**toFixed()**

It returns the string that represents a number with exact digits after a decimal point.

**toPrecision()**

It returns the string representing a number of specified precision.

**toString()**

It returns the given number in the form of string.
## JavaScript Boolean Properties



## JavaScript Boolean Methods

**toSource()**

returns the source of Boolean object as a string.

**toString()**

converts Boolean into String.

**valueOf()**

converts other type into Boolean.

## Methods of window object



**alert()**

displays the alert box containing message with ok button.

**confirm()**

displays the confirm dialog box containing message with ok and cancel button.

**prompt()**

displays a dialog box to get input from the user.

**open()**

opens the new window.

**close()**

closes the current window.

**setTimeout()**

performs action after specified time like calling function, evaluating expressions etc.

## Methods of document object

**write("string")**

writes the given string on the doucment.

**writeln("string")**

writes the given string on the doucment with newline character at the end.

**getElementById()**

returns the element having the given id value.

**getElementsByName()**

returns all the elements having the given name value.

**getElementsByTagName()**

returns all the elements having the given tag name.

**getElementsByClassName()**

returns all the elements having the given class name.









