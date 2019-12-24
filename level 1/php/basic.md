

# Variables

## Integer

    $int_var = 12345;
    $another_int = -12345 + 12345;


## Doubles

    $many = 2.2888800;
    
    $many_2 = 2.2111200;
    
    $few = $many + $many_2;
    
    print("$many + $many_2 = $few <br>");



## Boolean



    if (TRUE)
    
    print("This will always print<br>");


## Strings

    $variable = "name";
    
    $literally = 'My $variable will not print!';

    $variable = "name";
    $literally = 'My $variable will not print!\\n';
**String Concatenation Operator**



    $string1="Hello World";
    
    $string2="1234";
    
    echo $string1 . " " . $string2;


**Using the strlen() function**

The strlen() function is used to find the length of a string.

    echo strlen("Hello world!");


**Using the strpos() function**

The strpos() function is used to search for a string or character within a string.


echo strpos("Hello world!","world");

## Array
There are three different kind of arrays :

**Numeric array** − An array with a numeric index.

**Associative array** − An array with strings as index. 

**Multidimensional array** − An array containing one or more arrays and values are

**Numeric array**

    $numbers = array( 1, 2, 3, 4, 5);
    
    foreach( $numbers as $value ) {
    
    echo "Value is $value <br />";
    
    }
**Associative array**

    $salaries = array("mohammad" => 2000, "qadir" => 1000, "zara" => 500);
    
    echo "Salary of mohammad is ". $salaries['mohammad'] . "<br />";
    echo "Salary of qadir is ". $salaries['qadir']. "<br />";
    echo "Salary of zara is ". $salaries['zara']. "<br />";
**Multidimensional Arrays**

    $marks = array(
    
    "mohammad" => array (
    
    "physics" => 35,
    
    "maths" => 30,
    
    "chemistry" => 39
    
    ),
    
    "qadir" => array (
    
    "physics" => 30,
    
    "maths" => 32,
    
    "chemistry" => 29
    
    ),
    
    "zara" => array (
    
    "physics" => 31,
    
    "maths" => 22,
    
    "chemistry" => 39
    
    )
    
    );
    
    /* Accessing multi-dimensional array values */
    
    echo "Marks for mohammad in physics : " ;
    
    echo $marks['mohammad']['physics'] . "<br />";
    
    echo "Marks for qadir in maths : ";
    
    echo $marks['qadir']['maths'] . "<br />";
    
    echo "Marks for zara in chemistry : " ;
    
    echo $marks['zara']['chemistry'] . "<br />";

## constant


    define("MINSIZE", 50);
    
    echo MINSIZE;

**PHP Magic constants**

**__ LINE__**

The current line number of the file.

**__ FILE__**

The full path and filename of the file. 

**__ FUNCTION__**

function name as it was declared (case-sensitive).


**__ CLASS__**

The class name.

**__ METHOD__**

The class method name. 

## Date
**time**
The integer returned by time() represents the number of seconds elapsed since midnight GMT on January 1, 1970.

**date(format,timestamp)**
The date() optionally accepts a time stamp if omitted then current date and
time will be used. 

    print date("m/d/y G.i:s<br>", time());
    print "Today is ";
    print date("j of F Y, \a\\t g.i a", time());

## Include file

**The include() Function**
The include() function takes all the text in a specified file and copies
it into the file that uses the include function. **If there is any problem
in loading a file then the include() function generates a warning but the
script will continue execution.**

**The require() Function**

The require() function takes all the text in a specified file and copies it into the file that uses the include function. **If there is any problem in loading a file then the require() function generates a fatal error and halt the execution of the script.**

So there is no difference in require() and include() except they handle error
conditions. It is recommended to use the require() function instead of include(), because scripts should not continue executing if files are missing or misnamed.

