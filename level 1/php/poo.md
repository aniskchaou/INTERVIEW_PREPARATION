

## Defining PHP Classes

    class Books {
    
    /* Member variables */
    
    var $price;
    
    var $title;
    
    /* Member functions */
    
    function setPrice($par){
    
    $this->price = $par;
    
    }
    
    function getPrice(){
    
    echo $this->price ."<br/>";
    
    }
    
    function setTitle($par){
    
    $this->title = $par;
    
    }
    
    function getTitle(){
    
    echo $this->title ." <br/>";
    
    }
    
    }

## Creating Objects in PHP

    $physics = new Books;
    
    $maths = new Books;
    
    $chemistry = new Books;
    $physics->setTitle( "Physics for High School" );
    
    $chemistry->setTitle( "Advanced Chemistry" );
    
    $maths->setTitle( "Algebra" );

## Constructor Functions

    function __construct( $par1, $par2 ) {
    
    $this->title = $par1;
    
    $this->price = $par2;
    
    }

## Inheritance

    class Novel extends Books {
    
    var $publisher;
    
    function setPublisher($par){
    
    $this->publisher = $par;
    
    }
    
    function getPublisher(){
    
    echo $this->publisher. "<br />";
    
    }
    
    }

## Interface
interface Mail {

    public function sendMail();
    
    }
    
    //Then, if another class implemented that interface, like this −
    
    class Report implements Mail {
    
    // sendMail() Definition goes here
    
    }

## Parent constructor

    class Name {
    
    var $_firstName;
    
    var $_lastName;
    
    function Name($first_name, $last_name) {
    
    $this->_firstName = $first_name;
    
    $this->_lastName = $last_name;
    
    }
    
    function toString() {
    
    return($this->_lastName .", " .$this->_firstName);
    
    }
    
    }
    
    class NameSub1 extends Name {
    
    var $_middleInitial;
    
    function NameSub1($first_name, $middle_initial, $last_name) {
    
    Name::Name($first_name, $last_name);
    
    $this->_middleInitial = $middle_initial;
    
    }
    
    function toString() {
    
    return(Name::toString() . " " . $this->_middleInitial);
    
    }
    
    }

## static

    class Foo {
    
    public static $my_static = 'foo';
    
    public function staticValue() {
    
    return self::$my_static;
    
    }
    
    }
    
    print Foo::$my_static . "\n";
    
    $foo = new Foo();
    
    print $foo->staticValue() . "\n";
