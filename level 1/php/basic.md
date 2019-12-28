

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

## PHP echo: printing variable value



    1.  <?php
    2.  $msg="Hello JavaTpoint PHP";
    3.  echo "Message is: $msg";
    4.  ?>


## PHP Variable: Rules

PHP variables must start with letter or underscore only.

PHP variable can't be start with numbers and special symbols.

    1.  $4c="hello";//number (invalid)
    2.  $*d="hello";//special symbol (invalid)
    
    3.  echo "$4c <br/> $*d";

## PHP constant: const keyword

The const keyword defines constants at compile time. It is a language construct not a function.

**It is bit faster than define().**

It is always case sensitive.



    1.  <?php
    2.  const MESSAGE="Hello const by JavaTpoint PHP";
    3.  echo MESSAGE;
    4.  ?>


## 8) PHP array_intersect() function

PHP array_intersect() function returns the intersection of two array. 

    1.  <?php
    2.  $name1=array("sonoo","john","vivek","smith");
    3.  $name2=array("umesh","sonoo","kartik","smith");
    4.  $name3=array_intersect($name1,$name2);
    5.  foreach( $name3  as  $n )
    6.  {
    7.  echo  "$n<br />";
    8.  }

## 4) PHP count() function

PHP count() function counts all elements in an array.


    1.  <?php
    2.  $season=array("summer","winter","spring","autumn");
    3.  echo  count($season);
    4.  ?>


## 5) PHP sort() function

PHP sort() function sorts all the elements in an array.


    1.  <?php
    2.  $season=array("summer","winter","spring","autumn");
    3.  sort($season);
    4.  foreach( $season  as  $s )
    5.  {
    6.  echo  "$s<br />";
    7.  }
    8.  ?>


## 6) PHP array_reverse() function



    1.  <?php
    2.  $season=array("summer","winter","spring","autumn");
    3.  $reverseseason=array_reverse($season);
    4.  foreach( $reverseseason  as  $s )
    5.  {
    6.  echo  "$s<br />";
    7.  }
    8.  ?>

# PHP File Handling

PHP File System allows us to create file, read file line by line, read file character by character, write file, append file, delete file and close file.

## PHP Open File - fopen()

The PHP fopen() function is used to open a file.


**Example**

    1.  <?php
    2.  $handle = fopen("c:\\folder\\file.txt", "r");
    3.  ?>




## PHP Close File - fclose()

The PHP fclose() function is used to close an open file pointer.



    1.  <?php
    2.  fclose($handle);
    3.  ?>

## PHP Read File - fread()

The PHP fread() function is used to read the content of the file. It accepts two arguments: resource and file size.



**Example**

    1.  <?php
    2.  $filename = "c:\\myfile.txt";
    3.  $handle = fopen($filename, "r");//open file in read mode
    
    5.  $contents = fread($handle, filesize($filename));//read file
    
    7.  echo  $contents;//printing data of file
    8.  fclose($handle);//close file
    9.  ?>





## PHP Write File - fwrite()

The PHP fwrite() function is used to write content of the string into file.



**Example**

    1.  <?php
    2.  $fp = fopen('data.txt', 'w');//open file in write mode
    3.  fwrite($fp, 'hello ');
    4.  fwrite($fp, 'php file');
    5.  fclose($fp);
    
    7.  echo  "File written successfully";
    8.  ?>

Output

File written successfully



## PHP Delete File - unlink()

The PHP unlink() function is used to delete file.



    1.  <?php
    2.  unlink('data.txt');
    
    3.  echo  "File deleted successfully";
    4.  ?>


# PHP File Upload

PHP allows you to upload single and multiple files through few lines of code only.

PHP file upload features allows you to upload binary and text files both. Moreover, you can have the full control over the file to be uploaded through PHP authentication and file operation functions.



## PHP $_FILES



### $_FILES['filename']['name']

returns file name.

### $_FILES['filename']['type']

returns MIME type of the file.

### $_FILES['filename']['size']

returns size of the file (in bytes).

### $_FILES['filename']['tmp_name']

returns temporary file name of the file which was stored on the server.

### $_FILES['filename']['error']

returns error code associated with this file.

----------

## move_uploaded_file() function

The move_uploaded_file() function moves the uploaded file to a new location. The move_uploaded_file() function checks internally if the file is uploaded thorough the POST request. It moves the file if it is uploaded through the POST request.
## Get the IP address of the website

**$_SERVER['REMOTE_ADDR']**  - It returns the IP address of the user currently visiting the webpage.
# PHP MySQL Select Query



**Example**  

    1.  <?php
    2.  $host = 'localhost:3306';
    3.  $user = '';
    4.  $pass = '';
    5.  $dbname = 'test';
    6.  $conn = mysqli_connect($host, $user, $pass,$dbname);
    7.  if(!$conn){
    8.  die('Could not connect: '.mysqli_connect_error());
    9.  }
    10.  echo  'Connected successfully<br/>';
    
    11.  $sql = 'SELECT * FROM emp4';
    12.  $retval=mysqli_query($conn, $sql);
    
    13.  if(mysqli_num_rows($retval) > 0){
    14.  while($row = mysqli_fetch_assoc($retval)){
    15.  echo  "EMP ID :{$row['id']} <br> ".
    16.  "EMP NAME : {$row['name']} <br> ".
    17.  "EMP SALARY : {$row['salary']} <br> ".
    18.  "--------------------------------<br>";
    19.  } //end of while
    20.  }else{
    21.  echo  "0 results";
    22.  }
    23.  mysqli_close($conn);
    24.  ?>

## PHP json_encode example 1

Let's see the example to encode JSON.

    1.  <?php
    2.  $arr = array('a' => 1, 'b' => 2, 'c' => 3, 'd' => 4, 'e' => 5);
    3.  echo json_encode($arr);
    4.  ?>

Output

    {"a":1,"b":2,"c":3,"d":4,"e":5}