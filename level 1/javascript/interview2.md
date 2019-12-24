
# How to redirect a page to another page in Javascript?


1.  **Using location.href:**  
window.location.href =“https://www.onlineinterviewquestions.com/”
3.  **Using location.replace:** 
window.location.replace(" https://www.onlineinterviewquestions.com/;");



# Is JavaScript multi-threaded or single-threaded?

JavaScript is single-threaded.

# What is difference between Array.splice() and Array.slice() method in JavaScript?


    Syntax of splice(): array.splice(index, howmany, item1, ....., itemX)
    
    Syntax of slice(): array.slice(start, end)


# How to you change the title of the page by JavaScript?



    document.title="My New Title";




# How to clone an object in Javascript?

Object.assign() method is used for cloning an object in Javascript.Here is sample usage

    var x = {myProp: "value"};
    var y = Object.assign({}, x);


# How to add/remove properties to object dynamically in Javascript?

You can add a property to an object using object.property_name =value, delete object.property_name is used to delete a property.


    let user = new Object();
    // adding a property
    user.name='Anil';
    user.age  =25;
    console.log(user);
    delete user.age;
    console.log(user);



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



.
