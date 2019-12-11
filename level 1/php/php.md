**Q #1) What is PHP?**

PHP is one of the popular server-side **`scripting languages for developing a web application.`**


**Q #3) Is PHP a `strongly typed language`?**

No. PHP is a weakly typed or loosely typed language.
Which means PHP **`does not require to declare data types of the variable when you declare any variable like the other standard programming languages C# or Java`**.


    $var = "Hello"; //String
    $var = 10; //Integer


**Q #4) What is meant by `variable variables` in PHP?**

**`When the value of a variable is used as the name of the other variables then it is called variable variables.`** $$ is used to declare variable variables in PHP.

    $str = "PHP";
    $$str = " Programming"; //declaring variable variables
    echo "$str ${$str}"; //It will print "PHP programming"
    echo "$PHP"; //It will print "Programming"
    
**Q #5) What are the differences between `echo` and `print`?**

**echo**  **`does not return any value after printing`** the output and it works faster than the print method.  
**print**  method is slower than the echo because it **`returns boolean value after printing the output`**.

    echo "PHP Developer";
    $n = print "Java Developer";
**Q #7) How can you declare the `array` in PHP?**

     //Numeric Array
    $computer = array("Dell", "Lenavo", "HP");
    //Associative Array
    $color = array("Sithi"=>"Red", "Amit"=>"Blue", "Mahek"=>"Green");
    //Multidimensional Array
    $courses = array ( array("PHP",50), array("JQuery",15), array("AngularJS",20) );

**What are the uses of `explode()` and `implode()` functions?**
**explode()** function is used to split a string into an array and 
**implode()** function is used to make a string by combining the array elements.

    $text = "I like programming";
    print_r (explode(" ",$text));
    $strarr = array('Pen','Pencil','Eraser');
    echo implode(" ",$strarr);

**Q #9) Which function can be used to `exit` from the script after displaying the error message?**

**Answer:**

You can use  **exit()**  or  **die()**  function to exit from the current script after displaying the error message.
echo gettype(true).''; //boolean
echo gettype(10).''; //integer
echo gettype('Web Programming').''; //string
echo gettype(null).''; //NULL

**Q #12) What is meant by ‘passing the variable by `value` and `reference`' in PHP?**


 **pass variable by value**.



    function test($n) {
    $n=$n+10;
    }
    
    $m=5;
    test($m);
    echo $m;

**pass variable by reference**

    function test(&$n) {
        $n=$n+10;
    }
    $m=5;
    test($m);
    echo $m;

**How can you make a `connection with MySQL` server using PHP?**

    $mysqli = mysqli_connect("localhost","username","password");
    $mysqli = new mysqli("localhost","username","password");
    
**How can you retrieve data from the MySQL database using PHP?**

**`mysqli_fetch_array()`**  – It is used to fetch the records as a numeric array or an associative array.
**`mysqli_fetch_row()`** – It is used to fetch the records in a numeric array.
**`mysqli_fetch_assoc()`** – It is used to fetch the records in an associative array.
**`mysqli_fetch_object()`** – It is used to fetch the records as an object.

** What are the differences between `mysqli_connect` and `mysqli_pconnect`?**

**mysqli_pconnect()** function `is used for making a persistence connection with the database` that does not terminate when the script ends.

**mysqli_connect()**  function searches any existing persistence connection first and if no persistence connection exists, `then it will create a new database connection and terminate the connection at the end of the script.`

**Which function is used in PHP to count the total `number of rows` returned by any query?**

**mysqli_num_rows()**  function is used to count the total number of rows returned by the query.

** How can you create a session in PHP?**

**session_start()**  function is used in PHP to create a session.

** Which function you can use in PHP to `open a file` for reading or writing or for both?**

You can use  **fopen()**  function to read or write or for doing both in PHP.

    $file1 = fopen("myfile1.txt","r"); //Open for reading
    $file2 = fopen("myfile2.txt","w"); //Open for writing
    $file3 = fopen("myfile3.txt","r+"); //Open for reading and writing

**What is the difference between include() and require()?**

If any error occurs at the time of including a file using  
**include()**  function, then **`it continues the execution of the script after showing an error message.`**  
**require()**  **`function stops the execution of a script by displaying an error message if an error occurs.`**

** Which function is used in PHP to `delete` a file?**
**unlink()**  function is used in PHP to delete any file.

**Q #23) What is the use of strip_tags() method?**

**strip_tags()**  function is used to retrieve the string from a text by omitting HTML, XML and PHP tags. 

    //Remove all tags from the text
    echo strip_tags("<b>PHP</b> is a popular <em>scripting</em> language");
    //Remove all tags excluding <b> tag
    echo strip_tags("<b>PHP</b> is a popular <em>scripting</em> language","<b>");

**How can you send HTTP header to the client in PHP?**

**header()**  function is used to send raw HTTP header to a client before any output is sent.

`header(``'Location: http://www.your_domain/'``);`

**Which functions are used to count the total number of array elements in PHP?**

**count()**  and  **sizeof()** 

**what is the difference between substr() and strstr()?**

**substr()**  function returns a part of the string based on the starting point and length.

**strstr()** function searches the first occurrence of a string inside another string. 

`echo`  `substr``(``"Computer Programming"``,9,7);` `//Returns “Program”`


`echo`  `substr``(``"Computer Programming"``,9);` `//Returns “Programming”`


`1`

`echo`  `strstr``(``"Learning Laravel 5!"``,``"Laravel"``);` `//Returns Laravel 5!`

`2`

`echo`  `strstr``(``"Learning Laravel 5!"``,``"Laravel"``,true);` `//Returns Learning`

**How can you declare a constant variable in PHP?**

**define()**  function is used to declare a constant variable in PHP. Constant variable declares without the $ symbol.

`define(``"PI"``,3.14);`

**Which function is used in PHP to search a particular value in an array?**
**in_array()**  function is used to search a particular value in an array.

**What is the use of $_REQUEST variable?**

The **$_REQUEST**  variable is used to read the data from the submitted HTML form.

**Which operator is used to combine string values in PHP?**

Two or more string values can be combined by using ‘.’ operator.

**Does PHP `support multiple inheritances`?**
PHP does not support multiple inheritances. 

    interface Isbn { 
    public function setISBN($isbn);
    }
    interface Type{
    public function setType($type); 
    }
    class bookDetails implements Isbn, Type {
    private $isbn; 
    private $type; 
    
    public function setISBN($isbn)
    { 
    $this -> isbn = $isbn; 
    }
    
    public function setType($type)
    { 
    $this -> type = $type; 
    }
    }

**Which functions are used to remove whitespaces from the string?**

There are three functions in PHP to remove the whitespaces from the string.

**trim()**  – It removes whitespaces from the left and right side of the string.  
**ltrim()**  – It removes whitespaces from the from the left side of the string.  
**rtrim()**  – It removes whitespaces from the from the right side of the string.

 **How can a `cross-site scripting attack` be prevented by PHP?**

Htmlentities() function of PHP can be used for preventing cross-site scripting attack.

 **Which PHP `global variable` is used for uploading a file?**

$_FILE[] array contains all the information of an uploaded file.

**What is URL rewriting?**
Appending the session ID in every local URL of the requested page for keeping the session information is called URL rewriting.


 **What is PDO?**

The full form of PDO is PHP Data Objects.

**How can we determine whether a variable is set?**

The boolean function isset determines if a variable is set and is not NULL.

**what the difference between the 'BITWISE AND' operator and the 'LOGICAL AND' operator?**

$a and $b: TRUE if both $a and $b are TRUE.

$a & $b: Bits that are set in both $a and $b are set.

**What are the `two main string operators`?**

The first is the concatenation operator ('.'), which returns the concatenation of its right and left arguments. 
The second is ('.='), which appends the argument on the right to the argument on the left.

**What does the array operator '`===`' means?**

$a === $b TRUE if $a and $b have the same key/value pairs **in the same order and of the same types.**

**What is the differences between $a != $b and $a !== $b?**

!= means inequality (TRUE if $a is not equal to $b) and !== means non-identity (TRUE if $a is not identical to $b).

 **How can we determine whether a PHP variable is an `instantiated object of a certain class`?**

To be able to verify whether a PHP variable is an instantiated object of a certain class we use instanceof.

**How is the ternary conditional operator used in PHP?**

Expression_1?Expression_2 : Expression_3;

 **What does the `unset()` function mean?**

The unset() function is dedicated for variable management. **`It will make a variable undefined.`**

**How do I check if a given variable is `empty`?**

     empty() 

 **How can we display information of a variable and `readable by a human with PHP`?**

    print_r().

**What do the initials of PHP stand for?**

PHP means PHP: Hypertext Preprocessor.

