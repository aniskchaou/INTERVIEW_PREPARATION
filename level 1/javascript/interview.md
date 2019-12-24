# **1. What is JavaScript?**

JavaScript is also an **Object based Programming language**

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#2-enumerate-the-differences-between-java-and-javascript)2. Enumerate the differences between Java and JavaScript?**

Java is a **complete programming language**. In contrast, JavaScript is a **coded program that can be introduced to HTML pages**.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#3-what-are-javascript-data-types)3. What are JavaScript Data Types?

-   Number
-   String
-   Boolean
-   Object
-   Undefined

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#4-what-is-the-use-of-isnan-function)4. What is the use of isNaN function?

isNan function returns true if the argument is not a number otherwise it is false.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#5-between-javascript-and-an-asp-script-which-is-faster)**5. Between JavaScript and an ASP script, which is faster?**

JavaScript is faster. **JavaScript is a client-side language** and thus it does not need the assistance of the web server to execute. On the other hand, ASP is a **server-side language and hence is always slower than JavaScript**. Javascript now is also a server side language (nodejs).

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#6-what-is-negative-infinity)6. What is negative infinity?

Negative Infinity is a number in JavaScript which can be derived by dividing negative number by zero.



# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#8-which-company-developed-javascript)8. Which company developed JavaScript?

Netscape is the software company who developed JavaScript.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#9-what-are-undeclared-and-undefined-variables)9. What are undeclared and undefined variables?

_**Undeclared variables** are those that do not exist in a program and are not declared._  If the program tries to read the value of an undeclared variable, then a runtime error is encountered.

_**Undefined variables** are those that are declared in the program but have not been given any value._  If the program tries to read the value of an undefined variable, an undefined value is returned.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#10-write-the-code-for-adding-new-elements-dynamically)10. Write the code for adding new elements dynamically?

    function addNode() { 
    var newP = document.createElement("p");
     var textNode = document.createTextNode(" This is a new text node");
      newP.appendChild(textNode); document.getElementById("firstP").appendChild(newP);
       } 

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#11-what-are-global-variables-how-are-these-variable-declared-and-what-are-the-problems-associated-with-using-them)11. What are global variables? How are these variable declared and what are the problems associated with using them?

The var keyword is used to declare a local variable or object. If the var keyword is omitted, a global variable is declared.

    globalVariable = "Test";



# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#12-what-is-a-prompt-box)12. What is a prompt box?

A prompt box  **is a box which allows the user to enter input by providing a text box**. Label and box will be provided to enter the text or number.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#13-what-is-this-keyword-in-javascript)13. What is 'this' keyword in JavaScript?

**'This'** keyword refers to the object from where it was called.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#14-explain-the-working-of-timers-in-javascript-also-elucidate-the-drawbacks-of-using-the-timer-if-any)14. Explain the working of timers in JavaScript? Also elucidate the drawbacks of using the timer, if any?

Timers are used to execute a piece of code at a set time or also to repeat the code in a given interval of time. This is done by using the functions  **setTimeout, setInterval**  and  **clearInterval**.

**Timers are operated within a single thread, and thus events might queue up, waiting to be executed.**

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#15-which-symbol-is-used-for-comments-in-javascript)15. Which symbol is used for comments in Javascript?

// for Single line comments and

/* Multi

Line

Comment

*/



# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#17-what-is--operator)17. What is === operator?

=== is called as strict equality operator which returns true when the two operands are having the same value without any type conversion.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#18-explain-how-can-you-submit-a-form-using-javascript)18. Explain how can you submit a form using JavaScript?

To submit a form using JavaScript use document.form[0].submit();

    document.form[0].submit();



# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#20-how-can-the-styleclass-of-an-element-be-changed)20. How can the style/class of an element be changed?

It can be done in the following way:

    document.getElementById("myText").style.fontSize = "20?;

or

    document.getElementById("myText").className = "anyclass";

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#21-explain-how-to-read-and-write-a-file-using-javascript)21. Explain how to read and write a file using JavaScript?

-   Using JavaScript extensions
-   Using a web page and Active X objects

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#22-what-are-all-the-looping-structures-in-javascript)22. What are all the looping structures in JavaScript?

-   For
-   While
-   do-while loops



# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#25-explain-the-difference-between--and-)25. Explain the difference between "== " and "==="?

**"=="**  checks only for equality in value  **"==="**  is a stricter equality test and returns false if either the value or the type of the two variables are different.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#26-what-would-be-the-result-of-327)26. What would be the result of 3+2+"7"?

Since 3 and 2 are integers, they will be added numerically. And since 7 is a string, its concatenation will be done. So the result would be 57.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#27-explain-how-to-detect-the-operating-system-on-the-client-machine)27. Explain how to detect the operating system on the client machine?

the **navigator.platform** string (property) should be used.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#28-what-do-mean-by-null-in-javascript)28. What do mean by NULL in Javascript?

The NULL value is used to represent no value or no object.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#29-what-is-the-function-of-delete-operator)29. What is the function of delete operator?

The delete keyword is used to delete the property as well as its value.

    var student= {age:20, batch:"ABC"}; delete student.age;

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#30-what-is-an-undefined-value-in-javascript)30. What is an undefined value in JavaScript?

-   Variable used in the code doesn't exist
-   Variable is not assigned to any value
-   Property doesn't exist

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#31-what-are-all-the-types-of-pop-up-boxes-available-in-javascript)31. What are all the types of Pop up boxes available in JavaScript?

-   Alert
-   Confirm and
-   Prompt

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#32-what-is-the-use-of-void0)32. What is the use of Void(0)?

**Void(0) is used to prevent the page from refreshing and parameter "zero" is passed while calling.**

Void(0) is used to call another method without refreshing the page.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#33-how-can-a-page-be-forced-to-load-another-page-in-javascript)33. How can a page be forced to load another page in JavaScript?

The following code has to be inserted to achieve the desired effect:

< script language="JavaScript" type="text/javascript" > < /script>

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#35-what-is-the-difference-between-an-alert-box-and-a-confirmation-box)35. What is the difference between an alert box and a confirmation box?

 - An alert box displays only one button which is the OK button.
 - But a Confirmation box displays two buttons namely OK and cancel.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#36-what-are-escape-characters)36. What are escape characters?

Escape characters (Backslash) is used when working with special characters like single quotes, double quotes, apostrophes and ampersands.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#38-explain-what-is-popmethod-in-javascript)38. Explain what is pop()method in JavaScript?

The pop() method is similar as the shift() method **but the difference is that the Shift method works at the start of the array.** Also the pop() method take the last element off of the given array and returns it. The array on which is called is then altered.

Example:

    var cloths = ["Shirt", "Pant", "TShirt"]; cloths.pop();

//Now cloth becomes Shirt,Pant




# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#43-how-generic-objects-can-be-created)43. How generic objects can be created?

Generic objects can be created as:

    var I = new object();

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#44-what-is-the-use-of-type-of-operator)44. What is the use of type of operator?

**'Typeof'** is an operator which is used to return a string description of the type of a variable.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#45-which-keywords-are-used-to-handle-exceptions)45. Which keywords are used to handle exceptions?

Try… Catch---finally is used to handle exceptions in the JavaScript

    Try{ Code } 
    Catch(exp){ Code to throw an exception } 
    Finally{ Code runs either it finishes successfully or after catch }

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#46-which-keyword-is-used-to-print-the-text-in-the-screen)46. Which keyword is used to print the text in the screen?

document.write("Welcome") 

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#47-what-is-the-use-of-blur-function)47. What is the use of blur function?

Blur function is used **to remove the focus from the specified object.**


# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#51-what-is-the-use-of-push-method-in-javascript)51. What is the use of Push method in JavaScript?

The push method is used to add or **append one or more elements to the end of an Array.** 

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#52-what-is-unshift-method-in-javascript)52. What is unshift method in JavaScript?

Unshift method is like push method **which works at the beginning of the array.** 


# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#54-how-are-object-properties-assigned)54. How are object properties assigned?

Properties are assigned to objects in the following way -

obj["class"] = 12;

or

obj.class = 12;



# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#56-what-is-the-way-to-get-the-status-of-a-checkbox)56. What is the way to get the status of a CheckBox?

The status can be acquired as follows -

    alert(document.getElementById('checkbox1').checked);

If the CheckBox will be checked, this alert will return TRUE.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#57-how-can-the-os-of-the-client-machine-be-detected)57. How can the OS of the client machine be detected?

The **navigator.appVersion** string can be used to detect the operating system on the client machine.

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#58-explain-windowonload-and-ondocumentready)58. Explain window.onload and onDocumentReady?

The onload function is not run **until all the information on the page is loaded**. 

onDocumentReady **loads the code just after the DOM is loaded.** 

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#60-how-can-a-value-be-appended-to-an-array)60. How can a value be appended to an array?

A value can be appended to an array in the given manner -

    arr[arr.length] = value;



# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#62-describe-the-properties-of-an-anonymous-function-in-javascript)62. Describe the properties of an anonymous function in JavaScript?

A function that is declared without any named identifier is known as an anonymous function.


    var anon = function() { 
    alert('I am anonymous');
     }; 
    anon();


# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#65-is-javascript-case-sensitive-give-an-example)65. Is JavaScript case sensitive? Give an example?

Yes, JavaScript is case sensitive.  **For example, a function parseInt is not same as the function Parseint.**

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#66-what-boolean-operators-can-be-used-in-javascript)66. What boolean operators can be used in JavaScript?

The 'And' Operator &&, 'Or' Operator || and the 'Not' Operator (!) can be used in JavaScript.



# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#68-what-is-the-role-of-break-and-continue-statements)68. What is the role of break and continue statements?

Break statement is used  **to come out of the current loop**  continue statement  **continues the current loop with a new recurrence.**

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#72-how-are-dom-utilized-in-javascript)72. How are DOM utilized in JavaScript?

DOM stands for Document Object Model and is responsible for how various objects in a document interact with each other. 

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#77-what-are-screen-objects)77. What are Screen objects?

Screen objects are used  **to read the information from the client's screen**.

-   **AvailHeight:**  Gives the height of client's screen
-   **AvailWidth:**  Gives the width of client's screen.
-   **ColorDepth:**  Gives the bit depth of images on the client's screen
-   **Height:**  Gives the total height of the client's screen, including the taskbar
-   **Width:**  Gives the total width of the client's screen, including the taskbar

# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#78-explain-the-unshift-method-)78. Explain the unshift() method ?

This method is functional at the starting of the array

    var name = [ "john" ];
     name.unshift( "charlie" ); 
     name.unshift( "joseph", "Jane" ); 
     console.log(name);

**output**

    [" joseph "," Jane ", " charlie ", " john "]



# [](https://github.com/aniskchaou/JAVA_SWIFT_ALGORITHME/blob/master/level%201/javascript/interview.md#80-what-are-the-decodeuri-and-encodeuri)80. What are the decodeURI() and encodeURI()?

EncodeURl() is used  _to convert URL into their hex coding._  DecodeURI() is used  _to convert the encoded URL back to normal._

```
var uri="my test.asp?name=ståle&car=saab";

document.write(encodeURI(uri)+ "<br>");

document.write(decodeURI(uri));

```

**Output -**

    my%20test.asp?name=st%C3%A5le&car=saab
    
    my test.asp?name=ståle&car=saab

# 82. What does the following statement declares?

    var myArray = [[[]]];

It declares a three dimensional array.

# 83. How are JavaScript and ECMA Script related?

ECMA Script are like **rules and guideline** while Javascript is a scripting language used for web development.