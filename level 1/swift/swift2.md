## Explain how you `define variables` in Swift language?

 You announce constants with the let keyword and variables with the var keyword.

## What is the significance of “?” in swift?

 In case the property does not hold a value, the “?” `helps in avoiding runtime errors.(optional)`


## Mention what is the difference between Swift and ‘Objective-C’ language?


**`Swift`** 
In a swift, the variable and constants are declared before their use
You have to use “let” keyword for constant and “var” keyword for variable
There is no need **`to end code with semi-colon`**
Swift does not require to create a separate interface like Objective C. You can define `classes in a single file (.swift)`

**`Objective-C`**
The code ends with semi-colon
In objective C, you have to choose between **`NSMutableString and NSString for string to be modified`**.
For classes, **`you create separate interface (.h) and implementation (.m)`** files for classes


 

## Mention what are the type of integers does Swift have?

Swift provides unsigned and signed integers in `8, 16, 32 and 64 bit forms.` 

## Explain how multiple line comment can be written in swift?

Multiple line comment can be written as forward-slash followed by an asterisk (/*)  and end with an asterisk followed by a forward slash (*/).

 

## What is de-initializer and how it is written in Swift?

A de-initializer is declared immediately before a class instance is `de-allocated`.  

    deinit  {
    
    // perform the deinitialization
    
    }

## Explain what Lazy stored properties is and when it is useful?

Lazy stored properties are used for a property whose initial **values is not calculated until the first time it is used**. 

## What is iOS Swift?

Swift is a compiled and new programming language evolved by Apple Inc in June 2014 in order to develop apps for mobile and desktop. This language works for `watchOS, macOS, iOS, and tvOS`.
Apple created Swift language to work with both `Cocoa Touch and Cocoa`. 

## What are the tools that are required to develop iOS applications?

 - Mac/MacMini
 -  Xcode
 -  Swift Programming Language
 -  Apple Developer Program

## Explain the common execution states for a swift iOS App (iOS Application Lifecycle).

**Not Running:** **`This is a simple state in which our app is not launched`** or no code is being executed and terminated by the system and the application is completely switched off.

**Inactive:** This state is just a transitional state. Inactive state means our application **`is running in the background but is not able to receive events`**.

**Active:** Active state is the main execution state, **`where our app is running in the background and is able to receive events`**.

**Background:** This is the state where our App is running in the background and **`still is able to execute the code in the background`**.

**Suspended:** This state means that our app running is in the background state and **`the system suspends this app and the application cannot execute any code`**.

## Is Swift an object-oriented programming language?

 Yes, 

## What type of objects are basic data types in swift?

 - Int
 -  Double and Float
 -  String
 -  Arrays
 -  Dictionaries

## What is init() in Swift?

**`Initializers are also called to create a new instance of a particular type`**. An initializer is an instance method with no parameters. Using initializer, we write the init keyword.

    init()
    {
    // perform some New Instance initialization here
    }

## What are the control transfer statements that are used in iOS swift?

 - Return 
 - Break 
 - Continue 
 - Fallthrough

## What is the difference between Let and Var in swift?

**Let:** Let keyword is immutable, it’s used to declare a `constant variable`, and the constant variable cannot be changed once they are initialized.

     let myAge = 25

**Var:** Var keyword is mutable, and is used to declare a `variant variable`. These variant variables can change the run time.

    var myName = “Dell”

we can change the value of name = “Apple”.

## Which JSON framework is supported by iOS?

SBJson framework is supported by iOS.

## What is PLIST in iOS?

Answer: PLIST stands for Property List. PLIST **`is basically a dictionary of value and keys that can be stored in our file system with a .plist file extension`**. 

## What is a Protocol in swift?

    Protocol Someprotocol
    {
    // protocol definition goes here
    }

We can define multiple protocols, which are separated by commas:

    Class SomeClass: SomeSuperclass, Firstprotocol, Secondprotocol
    {
    // Structure definition goes here
    }

## What is a delegate in swift?

Delegate is a design pattern, **`which is used to pass the data or communication between structs or classes.`** 
Delegate allows sending a message from one object to another object when a **`specific event happens and is used for handling table view and Collection View events.`**


## What is the use of double question mark “??” in swift?

The double question mark “??” is a nil-coalescing operator,
 

    stringVar ?? “default string”

This exactly does the common thing, if stringVar is not nil then it is returned, `otherwise the “default string” is returned`.

## What is a GUARD statement? What is the benefit of using GUARD statement in swift?

 A guard statement is used **`to transfer the program control out of the scope when one or more conditions are not met`**. Using the guard statement helps in avoiding the pyramid of doom.



    guard true  else  {`
    print("Condition not met")`
    }`
    print("Condition met")
    
result : Condition met
`

## What is “defer”?

Answer: The “defer” is a keyword that provides **`a block of code that can be executed while the execution is leaving the current scope.`**
```swift
func writeFile() {
    let file: FileHandle? = FileHandle(forReadingAtPath: filepath)
    defer { file?.closeFile() }

    // Write changes to the file
}
```

## What is the difference between Array and NSArray?

 - An array can hold only one type of data, whereas **NSArray can hold
   different types of data**. 
 - An array is a value type, whereas NSArray is
   **an immutable reference type**.

## What are the best ways of achieving concurrency in iOS?

 - Dispatch queues
 -  Threads
 -  Operation queues

## How to create a constant in Swift programming?

 We have to use the “let” keyword to declare a constant in the Swift Programming.

## How to pass the data between view controllers?

Answer: There are three ways to pass the data between view controllers as shown below.

 - **Using Segue**, in prepareForSegue method (Forward). 
 - Setting the **variable directly** (Backword). 
 - **Delegate** (Backword).

 

## How can we define a base class in swift?

 In a swift programming language, **classes are not inherited from the base class**. 

## How can we make a property Optional in swift?

 Declaring a Question mark “?” in the swift code can make a property optional. This question mark “?” **helps to avoid the runtime error when a property doesn’t hold a value**.
