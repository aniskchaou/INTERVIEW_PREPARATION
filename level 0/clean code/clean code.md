# clean code
## Variables
### Use meaningful and pronounceable variable names

            //bad
            Date yyymmdd=new Date();
            
            //good
            Date today=new Date();
### Use searchable names

    //bad
    // What the heck is 86400000 for?
    setTimeout(blastOff, 86400000);
    :
    //good
    // Declare them as capitalized `const` globals.
    public static final int MILLISECONDS_IN_A_DAY = 86400000;
    setTimeout(blastOff, MILLISECONDS_IN_A_DAY);

### Avoid Mental Mapping

    //bad
    String [] l = {"Austin", "New York", "San Francisco"};
    
    for (int i = 0; i < l.length; i++) {
        String li = l[i];
        doStuff();
        doSomeOtherStuff();
        // ...
        // ...
        // ...
        // Wait, what is `$li` for again?
        dispatch(li);
     }
    Good:
    //good
    String[] locations = {"Austin", "New York", "San Francisco"};
    
    for (String location : locations) {
        doStuff();
        doSomeOtherStuff();
        // ...
        // ...
        // ...
        dispatch(location);
     }
## **Functions**

### Function arguments (2 or fewer ideally)

            //bad
            void printProduct(long id,String name,String type,double quantity){
            
            }
            //good
             void printProduct(Product product){
            
            }
### Functions should do one thing
### Function names should say what they do
### Avoid negative conditionals
### Remove duplicate code
### Encapsulate conditionals

    //bad
    
    if (fsm.state === "fetching" && isEmpty(listNode)) {
      // ...
    }
    //good
    function shouldShowSpinner(fsm, listNode) {
      return fsm.state === "fetching" && isEmpty(listNode);
    }
    
    if (shouldShowSpinner(fsmInstance, listNodeInstance)) {
      // ...
    }

## **SOLID**
## **Comments**
## **Formatting**
### automatic formatting (tabs,identations)
### Use consistent capitalization

            //bad
            final int DAYS_IN_WEEK = 7;
            final int daysInMonth = 30;
    
            final String[] songs = {"Back In Black", "Stairway to Heaven", "Hey Jude"};
            final String[] Artists = {"ACDC", "Led Zeppelin", "The Beatles"};
    
            void erasedatabase() {}
            void restore_database() {}
    
            class animal {}
            class Alpaca {}
           
            //good
            
              final int DAYS_IN_WEEK = 7;
            final int DAYS_IN_MONTH  = 30;
    
            final String[] SONGS = {"Back In Black", "Stairway to Heaven", "Hey Jude"};
            final String[] ARTISTS = {"ACDC", "Led Zeppelin", "The Beatles"};
    
            void eraseDatabase() {}
            void restoreDatabase() {}
    
            class Animal {}
            class Alpaca {}
### Function callers and callees should be close

     //bad
            void function4(){
               function5();
            }       
             void function3(){
            
            }   
            void function1()
            {
                function3();
                function2();
                function4();
            }
              void function5(){
            
            }
            
            void function2(){
            
            }
            
            //good
             void function1()
            {
                function2();
                function3();
                function4();
            }
            
            void function2(){
            
            }
            void function3(){
            
            }   
            
            void function4(){
               function5();
            }   
             void function5(){
            
            }

## **Objects**
### Use getters and setters
### Make objects have private members