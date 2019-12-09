# Write a program to reverse a string in pure JavaScript?


str="jQuery";
str = str.split(""); //convert 'jQuery' to array
str = str.reverse(); //reverse 'jQuery' order 
str = str.join(""); //then combines  the reverse order values.
alert(str);

First split the string to an array, then reverse an array and after that join the characters to form a string.


# How to redirect a page to another page in Javascript?


1.  **Using location.href:**  
window.location.href =“https://www.onlineinterviewquestions.com/”
3.  **Using location.replace:** 
window.location.replace(" https://www.onlineinterviewquestions.com/;");

# How to remove duplicate values from a JavaScript array?


let duplicates = ['delhi','kanpur','kanpur','goa','delhi','new york'];

function removeDuplicatesValues(arr){
    let unique_array = [];
    for(let i = 0;i < arr.length; i++){
        if(unique_array.indexOf(arr[i]) == -1){
            unique_array.push(arr[i])
        }
    }
    return unique_array
}

console.log(removeDuplicatesValues(duplicates));

# Is JavaScript multi-threaded or single-threaded?

JavaScript is single-threaded.

# What is difference between Array.splice() and Array.slice() method in JavaScript?

-   The array.slice() removes items from the array and then return those removed items as an array whereas array.slice() method is selected items from an array and then those elements as a new array object.
-   The splice() method affects the original array whereas slice() method doesn’t affect the original array.
-   Splice() method takes n number of arguments whereas slice() can take only two arguments.

Syntax of splice(): array.splice(index, howmany, item1, ....., itemX)

Syntax of slice(): array.slice(start, end)

# How to call a function in every x seconds in JavaScript?

In JavaScript, we use the function setInterval() to call any function in every x seconds.

**Syntax:**  setInterval(function, milliseconds, param1, param2, ...)

**Function:**  it is a required parameter which includes the function to be execute.

**Milliseconds:**  required parameter which tells how often the function will execute.

Others are an additional parameter.

**For example:**  setInterval(function (){ alert("Hello"); }, 3000);

In the above example, this function calls hello function in very 3 seconds.


# How to you change the title of the page by JavaScript?

You can change the title of a webpage using setting the title property of the document object.

document.title="My New Title";

# Explain Typecasting in Javascript?

In Programming whenever we need to convert a variable from one data type to another Typecasting is used. In Javascript, we can do this via library functions. There are basically 3 typecasts are available in Javascript Programming, they are:

-   Boolean(value): Casts the inputted value to a Boolean
-   Number(value): Casts the inputted value to an Integer or Floating point Number.
-   String(value) : Casts the inputted value value a string

# List different ways of empty an array in Javascript?

In Javascript, there are many ways to empty an array in Javascript, below we have listed 4 major

-   By assigning an empty array.
    
    var arr1 =[1,4,5,6];
    arr1=[];
    
-   By assigning array length to 0.
    
    var arr2 =[1,4,5,6];
    arr2.length=0;
    
-   By poping the elements of the array.
    
    var arr2 =[1,4,5,6];
    while(arr.length > 0) {
        arr.pop();
    }
    
-   By using .splice() .
    
    var arr =[1,4,5,6];
    arr.splice(0,arr.length)

# How to clone an object in Javascript?

Object.assign() method is used for cloning an object in Javascript.Here is sample usage

	var x = {myProp: "value"};
	var y = Object.assign({}, x);
# How to convert Javascript date to ISO standard?

**toISOString()**  method is used to convert javascript date to ISO standard. It converts JavaScript Date object into a string, using the ISO standard.

var date = new Date();
var n = date.toISOString();
console.log(n);
// YYYY-MM-DDTHH:mm:ss.sssZ

# How to add/remove properties to object dynamically in Javascript?

You can add a property to an object using object.property_name =value, delete object.property_name is used to delete a property.


    let user = new Object();
    // adding a property
    user.name='Anil';
    user.age  =25;
    console.log(user);
    delete user.age;
    console.log(user);

# How to calculate Fibonacci numbers in JavaScript?

Fibonacci numbers are a sequence of numbers where each value is the sum of the previous two, starting with 0 and 1. The first few values are 0, 1, 1, 2, 3, 5, 8, 13 ,…,

function fib(n) {
	var a=0, b=1;
	for (var i=0; i < n; i++) {
		var temp = a+b; 
		a = b;
		b = temp;
	}
	return a;
}

# What is Javascript BOM?

BOM stands for “Browser Object Modal” that allows Javascript to ‘talk’ to the browser, no standards, modern browsers implement similar BOMS – window, screen, location, history, navigator, timing, cookies.

# What does the instanceof operator do?

In Javascript **instanceof** operator checks whether the object is an instance of a class or not:

Square.prototype = new Square();
console.log(sq instanceof Square); // true

# How to get the primitive value of a string in Javascript?

In Javascript **valueOf()** method is used to get the primitive value of a string.

var myVar= "Hi!"
console.log(myVar.valueOf())

# How to get the last index of a string in Javascript?

**string.length-1** is used to get the last index of a string in Javascript


var myString="JavascriptQuestions";
console.log(myString.length-1);

# List the comparison operators supported by Javascript?

Javascript supports below comparison operators

-   > Greater than
-   < Less than
-   <= Less than or equal to
-   >= Greater than or equal to
-   == Equal to
-   != Not Equal to
-   === Equal to with datatype check
-   !== Not equal to with datatype check

# What is the difference between let and var?

Both var and let are used for variable/ method declaration in javascript but the main difference between let and var is that  **var**  is function scoped whereas  **let**  is block scoped.

# What close() does in Javascript?

In Javascript close() method is used to close the current window.