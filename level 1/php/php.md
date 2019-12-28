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

# PHP Interview Questions


There is given PHP interview questions and answers that have been asked in many companies. Let's see the list of top PHP interview questions.



### 2) What is PEAR in PHP?

**PEAR**  is a framework and  _repository for reusable PHP components_. PEAR stands for  **PHP Extension and Application Repository**. It contains all types of PHP code snippets and libraries.

It also provides a command line interface to install "packages" automatically.

----------

### 3) Who is known as the father of PHP?

_Rasmus Lerdorf_

----------

### 4) What was the old name of PHP?

The old name of PHP was Personal Home Page.

----------

### 5) Explain the difference b/w static and dynamic websites?

In  **static websites**,  _content can't be changed_  after running the script. You can't change anything on the site. It is predefined.

In  **dynamic websites**,  _content of script can be changed at the run time_. Its content is regenerated every time a user visit or reload. Google, yahoo and every search engine is the example of dynamic website.

----------

### 6) What is the name of scripting engine in PHP?

The scripting engine that powers PHP is called  _Zend Engine 2_.

----------

### 7) Explain the difference between PHP4 and PHP5.

PHP4 doesn't support oops concept and uses Zend Engine 1.

PHP5 supports oops concept and uses Zend Engine 2.

----------

### 8) What are the popular Content Management Systems (CMS) in PHP?

-   **WordPress:**  WordPress is a free and open-source content management system (CMS) based on PHP & MySQL. It includes a plug-in architecture and template system. It is mostly connected with blogging but supports another kind of web content, containing more traditional mailing lists and forums, media displays, and online stores.
-   **Joomla:**  Joomla is a free and open-source content management system (CMS) for distributing web content, created by Open Source Matters, Inc. It is based on a model-view-controller web application framework that can be used independently of the CMS.
-   **Magento:**  Magento is an open source E-trade programming, made by Varien Inc., which is valuable for online business. It has a flexible measured design and is versatile with many control alternatives that are useful for clients. Magento utilizes E-trade stage which offers organization extreme E-business arrangements and extensive support network.
-   **Drupal:**  Drupal is a CMS platform developed in PHP and distributed under the GNU (General Public License).

----------

### 9) What are the popular frameworks in PHP?

-   CakePHP
-   CodeIgniter
-   Yii 2
-   Symfony
-   Zend Framework etc.

----------

### 10) Which programming language does PHP resemble to?

PHP has borrowed its syntax from Perl and C.

----------

### 11) List some of the features of PHP7.

-   Scalar type declarations
-   Return type declarations
-   Null coalescing operator (??)
-   Spaceship operator
-   Constant arrays using define()
-   Anonymous classes
-   Closure::call method
-   Group use declaration
-   Generator return expressions
-   Generator delegation
-   Space ship operator

----------

### 12) What is "echo" in PHP?

PHP echo output one or more string. 

### 13) What is "print" in PHP?

PHP print output a string. It is a language construct not a function. So the use of parentheses is not required with the argument list. Unlike echo, it always returns 1.



### 14) What is the difference between "echo" and "print" in PHP?

**Echo**  can  _output one or more string_  but  **print**  can only  _output one string and always returns 1_.

**Echo**  is  _faster than print_  because it does not return any value.

----------

### 15) How a variable is declared in PHP?

A PHP variable is the name of the memory location that holds data. It is temporary storage.

**Syntax:**

 

    $variableName=value;



### 16) What is the difference between $message and $$message?

**$message**  _stores variable data_  while  **$$message**  is used  _to store variable of variables_.

$message stores fixed data whereas the data stored in $$message may be changed dynamically.



### 17) What are the ways to define a constant in PHP?

PHP constants are name or identifier that can't be changed during execution of the script. PHP constants are defined in two ways:

-   Using define() function
-   Using const() function



### 18) What are magic constants in PHP?

PHP magic constants are predefined constants, which change based on their use. They start with a double underscore (__) and end with a double underscore (__).



### 19) How many data types are there in PHP?

PHP data types are used to hold different types of data or values. There are 8 primitive data types which are further categorized in 3 types:

-   Scalar types
-   Compound types
-   Special types



### 20) How to do single and multi line comment in PHP?

PHP single line comment is made in two ways:

-   Using // (C++ style single line comment)
-   Using # (Unix Shell style single line comment)

PHP multi-line comment is made by enclosing all lines within.



### 21) What are the different loops in PHP?

For, while, do-while and for each.

----------

### 22) What is the use of count() function in PHP?

The PHP count() function is used  _to count total elements in the array, or something an object_.

----------

### 23) What is the use of header() function in PHP?

The header() function is used to send a raw HTTP header to a client. It must be called before sending the actual output. For example, you can't print any HTML element before using this function.

----------

### 24) What does isset() function?

The isset() function checks if the variable is defined and not null.

----------



### 26) Explain PHP variable length argument function

PHP supports variable length argument function. It means you can pass 0, 1 or n number of arguments in function. To do this, you need to use 3 ellipses (dots) before the argument name. The 3 dot concept is implemented for variable length argument since PHP 5.6.



### 27) Explain PHP variable length argument function.

PHP supports variable length argument function. It means you can pass 0, 1 or n number of arguments.

----------

### 28) What is the array in PHP?

An array is used to store multiple values in a single value. In PHP, it orders maps of pairs of keys and values. It saves the collection of the data type.



### 29) How many types of array are there in PHP?

There are three types of array in PHP:

1.  **Indexed array:**  an array with a numeric key.
2.  **Associative array:**  an array where each key has its specific value.
3.  **Multidimensional array:**  an array containing one or more arrays within itself.

----------

### 30) Explain some of the PHP array functions?

There are many array functions in PHP:

-   array()
-   array_change_key_case()
-   array_chunk()
-   count()
-   sort()
-   array_reverse()
-   array_search()
-   array_intersect()



### 31) What is the difference between indexed and associative array?

The indexed array holds elements in an indexed form which is represented by number starting from 0 and incremented by 1. For example:

 

$season=array("summer","winter","spring","autumn");

The associative array holds elements with name. For example:

     $salary=array("Sonoo"=>"350000","John"=>"450000","Kartik"=>"200000");



### 32) How to get the length of string?

The strlen() function is used to get the length of the string.



### 33) Explain some of the PHP string functions?

There are many array functions in PHP:

-   strtolower()
-   strtoupper()
-   ucfirst()
-   lcfirst()
-   ucwords()
-   strrev()
-   strlen()



### 34) What are the methods to submit form in PHP?

There are two methods GET and POST.



### 35) How can you submit a form without a submit button?

You can use JavaScript submit() function to submit the form without explicitly clicking any submit button.

----------

### 36) What are the ways to include file in PHP?

PHP allows you to include file so that page content can be reused again. There are two ways to add the file in PHP.

1.  include
2.  require



### 37) Differentiate between require and include?

Require and include both are used to include a file, but if data is not found  _include sends warning_  whereas  _require sends Fatal error_.



### 38) Explain setcookie() function in PHP?

PHP setcookie() function is used to set cookie with HTTP response. Once the cookie is set, you can access it by $_COOKIE superglobal variable.



### 39) How can you retrieve a cookie value?

     echo  $_COOKIE ["user"];





### 41) What is the method to register a variable into a session?

    1.  <?php
    2.  Session_register($ur_session_var);
    3.  ?>

----------


### 43) What is PHP session_start() and session_destroy() function?

PHP session_start() function is used to start the session.


### 45) Write syntax to open a file in PHP?

PHP fopen() function is used to open file or URL and returns resource.

### 46) How to read a file in PHP?

PHP provides various functions to read data from the file. Different functions allow you to read all file data, read data line by line, and read data character by character.

PHP file read functions are given below:

-   fread()
-   fgets()
-   fgetc()



### 47) How to write in a file in PHP?

PHP fwrite() and fputs() functions are used to write data into file. To write data into a file, you need to use w, r+, w+, x, x+, c or c+ mode.



### 48) How to delete file in PHP?

The unlink() function is used to delete a file in PHP.

     bool unlink (string $filename)



### 49) What is the method to execute a PHP script from the command line?

You should just run the PHP command line interface (CLI) and specify the file name of the script to be executed as follows.

----------

### 50) How to upload file in PHP?

The move_uploaded_file() function is used to upload file in PHP.

 

    bool move_uploaded_file ( string $filename , string $destination )



### 51) How to download file in PHP?

The readfile() function is used to download the file in PHP.

 

    int readfile ( string $filename )



### 52) How can you send email in PHP?

The mail() function is used to send email in PHP.

  

    bool mail($to,$subject,$message,$header);



### 53) How do you connect MySQL database with PHP?

There are two methods to connect MySQL database with PHP. Procedural and object-oriented style.



### 54) How to create connection in PHP?

The mysqli_connect() function is used to create a connection in PHP.

      resource mysqli_connect (server, username, password)



----------

### 55) How to create database connection and query in PHP?

Since PHP 4.3, mysql_reate_db() is deprecated. Now you can use the following 2 alternatives.

-   mysqli_query()
-   PDO::_query()



### 56) How can we increase execution time of a PHP script?

You can change the script run time by changing the max_execution_time directive in the php.ini file.


-

### 57) What are the different types of errors in PHP?

There are 3 types of error in PHP.

1.  **Notices:**These are non-critical errors. These errors are not displayed to the users.
2.  **Warnings:**These are more serious errors, but they do not result in script termination. By default, these errors are displayed to the user.
3.  **Fatal Errors:**These are the most critical errors. These errors may cause due to immediate termination of script.

----------

### 58) How to stop the execution of PHP script?

The exit() function is used to stop the execution of PHP script.

----------

### 59) What are the encryption functions in PHP?

_CRYPT()_  and  _MD5()_

----------

### 60) What is htaccess in PHP?

The .htaccess is a configuration file on Apache server. You can change configuration settings using directives in Apache configuration files like .htaccess and httpd.conf.

----------

### 61) Explain PHP explode() function.

The PHP explode() function breaks a string into an array.

----------

### 62) Explain PHP split() function.

The PHP split() function splits string into an array by regular expression.

----------

### 63) How can we get IP address of a client in PHP?

    $_SERVER["REMOTE_ADDR"];

----------

### 64) What is the meaning of a Persistent Cookie?

A persistent cookie is permanently stored in a cookie file on the browser's computer. By default, cookies are temporary and are erased if we close the browser.

----------

### 65) What is the use of the function 'imagetypes()'?

imagetypes() gives the image format and types supported by the current version of GD-PHP.

----------

### 66) What are include() and require() functions?

The  **Include()**  function is used to put data of one PHP file into another PHP file. If errors occur, then the include() function produces a warning but does not stop the execution of the script, and it will continue to execute.

The  **Require()**  function is also used to put data of one PHP file to another PHP file. If there are any errors, then the require() function produces a warning and a fatal error and stops the script.

----------

### 67) What is Cookies? How to create cookies in PHP?

A cookie is used to identify a user. A cookie is a little record that the server installs on the client's Computer. Each time a similar PC asks for a page with a program, it will send the cookie as well. With PHP, you can both make and recover cookie value.

**Some important points regarding Cookies:**

1.  Cookies maintain the session id generated at the back end after verifying the user's identity in encrypted form, and it must reside in the browser of the machine
2.  You can store only string values not object because you can't access any object across the website or web apps
3.  Scope: - Multiple pages.
4.  By default, cookies are temporary and transitory cookie saves in the browser only.
5.  By default, cookies are URL particular means Gmail isn't supported in Yahoo and the vice versa.
6.  Per site 20 cookies can be created in one website or web app
7.  The Initial size of the cookie is 50 bytes.
8.  The Maximum size of the cookie is 4096 bytes.

----------

### 68) What is the Importance of Parser in PHP?

PHP parser parses the PHP developed website from the opening to the closing tag. Tags indicate that from where PHP code is being started and ended. In other words, opening and closing tags decide the scope of PHP scripting syntax of closing tag in PHP

<?php syntax of opening tag in PHP  
?> syntax of closing tag in PHP

----------

### 69) How can we create a database using PHP and MySQL?

The necessary steps to create a MySQL database using PHP are:

-   Establish a  **connection**  to MySQL server from your PHP script.
-   If the connection is successful, write a SQL query to create a  **database**  and store it in a string variable.
-   **Execute**  the query. 