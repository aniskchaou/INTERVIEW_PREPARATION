## Joining point

## Loop detection

## Approximation of pi

## Combinaition options in a tourments

    func factoriel(_ n:Int)  ->  Int
    
    {
    
    var i:Int  =  1
    
    var f:Int  =  1
    
    while i <= n {
    
    f = f * i
    
    i = i +  1
    
    }
    
    return f
    
    }
    
    func count(n:Int)  ->  Int
    
    {
    
    return  (factoriel(n)/(factoriel(n-2)*factoriel(2)))
    
    }
    
    print(count(n:6))

## Twins

## Intervals

## Summer sales

## Duplicates removal

    var arr:[Int]  =  [1,3,3,3,2,5]
    
    arr.sort{ $0  < $1  }
    
      
    
    func duplicateremoval(arr:[Int],n:Int)
    
    {
    
    var arrr = arr
    
    var temp =  [0,0,0,0]
    
    var j =  0;
    
    var s =  (n-1)
    
    var i =  0
    
    while(i < s)  {
    
    var next = i +  1
    
    if  (arrr[i]  != arrr[i+1]  )
    
    {
    
    temp[j]  = arrr[i];
    
    j = j +  1
    
    }
    
    i = i +  1
    
    }
    
    temp[j]  = arrr[s];
    
    j = j +  1
    
    for i in  0..<j {
    
    arrr[i]  = temp[i]
    
    print(arrr[i])
    
    }
    
      
    
    }
    
      
    
    duplicateremoval(arr:arr,n:arr.count)

## Summing based on factors
  

    func sumFactor(_ n:Int)  ->  Int
    
    {
    
    var res=0;
    
    var i=2
    
    var s =  Int(sqrt(Double(n)))
    
    while(i <= s )
    
    {
    
    if(n%i==0)
    
    {
    
    if(i==n/i){
    
    res+=i;
    
    }else
    
    {
    
    res+=(i+n/i)
    
    }
    
    }
    
    i=i+1
    
    }
    
    return  1+n+res;
    
    }
    
    var x = sumFactor(15)
    
    print(x);

## Array index


    let arr:Array = ["a","b","c"]
    find(arr, "c")!              // 2
    find(arr, "d")               // nil

Update for Swift 2.0:

    let arr = ["a","b","c"]
    
    let indexOfA = arr.indexOf("a") // 0
    let indexOfB = arr.indexOf("b") // 1
    let indexOfD = arr.indexOf("d") // nil


Update for Swift 3.0:

    let indexOfA = arr.index(of: "a")

Update for Swift 4.2:

    let arr = ["a","b","c","a"]
    
    let indexOfA = arr.firstIndex(of: "a") // 0
    let indexOfB = arr.lastIndex(of: "a") // 3

## Range sum

    var arr:[Int]=[1,1,1,1];
    
      
    
    func rangeSum(_ arr:[Int]  ,_ start:Int  ,_ end:Int)  ->  Int
    
    {
    
    if(start>end)
    
    {
    
    return  0;
    
    }else
    
    {
    
    return arr[start]+rangeSum(arr,start+1,end);
    
    }
    
    }
    
    var x=rangeSum(arr,1,3);
    
    print(x);

## Average

    var somme =  0
    
    var moyenne =  0
    
    var tab =  [1,  4,  6,  6,  3,  9,  3,  0,  3]
    
    //nombre d'elements
    
    var n = tab.count
    
    //somme
    
    var j=0
    
    while(j<n)  {
    
    somme += tab[j]
    
    j = j +  1
    
    }
    
    //moyenne = somme/nombre
    
    moyenne = somme / n;

## Simple Boolean expression

    func valid (_ i:Int,_ j:Int)  ->  Bool
    {  
    return i ==  1  || j ==  1  || i+j  ==  5 
    }

## Simple fix

## Failable Initializers


An initializer defined with init can be made failable by adding a ? or a ! after the init, which indicates the form of optional that will be produced by constructing an object with that initializer. For example, one could add a failable initializer to Int that attempts to perform a conversion from a String:

    extension Int {
        init?(fromString: String) { 
            if let i = fromString.toInt() {
                // Initialize
                self = i
            } else { 
                // return nil, discarding self is implied
                return nil
            }
        }
    }

In a failable initializer, return nil indicates that initialization has failed; no other value can be returned. In the example, failure occurs when the string could not be parsed as an integer. Otherwise, self is initialized to the parsed value.


## Range operators
 1. Closed Range Operator (lowerBound...upperBound)

It is declared using  `…`  (3 dots)operator.

**E.g:**  `1...3`  Defines range containing values 1,2,3

2. Half Open Range 

 It is declared using  `..<`  operator.

**E.g:**  `1..<3`  Defines range containing values 1 and 2

#### Example 3: One-sided range less than 2

1.  `let range =  ..<2`
2.  `print(range.contains(-1))`
3.  `print(range.contains(2))`

When you run the program, the output will be:

true
false

#### Example 4:One-sided range starting from 2

1.  `let range =  2...`
2.  `print(range.contains(100))`
3.  `print(range.contains(1))`

When you run the program, the output will be:

true
false
## Using extensions


With an extension you can add new functionality to an existing Swift class, structure, enumeration or protocol type. You can literally add on new functions to an existing class, even if you don’t have access to the original source code of that class.

    class Airplane
    {
        var altitude: Double = 0
    
        func setAltitude(feet: Double) {
            altitude = feet
        }
    }
    
    extension Airplane
    {
        func setAltitude(meter: Double) {
            altitude = meter * 3.28084
        }
    }

You can now use the setAltitude(meter:) function on an instance of class Airplane as an ordinary function, like this:

    let boeing = Airplane()
    boeing.setAltitude(meter: 12000)
    print(boeing.altitude)
    // Output: 39370.08

## Initializing tuples


    var point = (0, 0)
    
    point.0 = 10
    point.1 = 15

point // (10, 15)
Note: Tuple are value types. When you initialize a variable tuple with another one it will actually create a copy.

    var origin = (x: 0, y: 0)
     var point = origin 
     point.x = 3 
     point.y = 5


    var person = (firstName: "John", lastName: "Smith")
    var firstName = person.firstName // John
    var lastName = person.lastName // Smith

## Storyboard

## Initilisazion dictionaries

    var dict5 : [String:Double] = [String:Double]()

And of course in real life you are liable to do none of these things, but just assign an actual dictionary to your variable:

    var dict6 = ["howdy":1.0]

## Language syntax

## Operationals control flow

## Initialisaziong opitinals

## Array type


    var someArray = [SomeType]()
    var someArray = [SomeType](count: NumbeOfElements, repeatedValue: InitialValue)
    var someInts = [Int](count: 3, repeatedValue: 0)
    var someInts:[Int] = [10, 20, 30]

## Iterating Over an Array


    var someStrs = [String]()
    
    someStrs.append("Apple")
    someStrs.append("Amazon")
    someStrs += ["Google"]
    for item in someStrs {
       print(item)
    }

result −

    Apple
    Amazon
    Google

 h

    var someStrs = [String]()
    
    someStrs.append("Apple")
    someStrs.append("Amazon")
    someStrs += ["Google"]
    
    for (index, item) in someStrs.enumerated() {
       print("Value at index = \(index) is \(item)")
    }

 result 

    Value at index = 0 is Apple
    Value at index = 1 is Amazon
    Value at index = 2 is Google

## Iterating through dictionary

    let interestingNumbers = [
    "Prime": [2, 3, 5, 7, 11, 13],
    "Fibonacci": [1, 1, 2, 3, 5, 8],
    "Square": [1, 4, 9, 16, 25],
    ]
    
    var largest = 0
    var whichKind: String? = nil
    
    for (kind, numbers) in interestingNumbers {
        for number in numbers {
        if number > largest {
            whichKind = kind
            largest = number
        }
      }
    }
    
    print(whichKind)
    print(largest)

OUTPUT:

    Optional("Square")
    25

## Optional binding



## Uiviewcontroller lifecycle


**1. loadView**
This event creates the view that the controller manages. It is only called when the view controller is created programmatically. 

**2. loadViewIfNeeded**
Loads the view controller's view if it has not already been set.

**3. viewDidLoad**
The viewDidLoad event is only called when the view is created and loaded into memory but the bounds for the view are not defined yet. 

**4. viewWillAppear**
This event notifies the viewController whenever the view appears on the screen. In this step the view has bounds that are defined but the orientation is not set.
Called when the view is about to made visible. Default does nothing.

**5. viewWillLayoutSubviews**
This is the first step in the lifecycle where the bounds are finalised. If you are not using constraints or Auto Layout you probably want to update the subviews here.

**6. viewDidLayoutSubviews**
This event notifies the view controller that the subviews have been setup. It is a good place to make any changes to the subviews after they have been set. 

**7. viewDidAppear**
The viewDidAppear event fires after the view is presented on the screen. 

**8. viewWillDisappear**
The viewWillDisappear event fires when the view of presented viewController is about to disappear, dismiss, cover or hide behind other viewController. 

**9. viewDidDisappear**
This is the last step of the lifecycle that anyone can address as this event fires just after the view of presented viewController has been disappeared, dismissed, covered or hidden.


## Memory management

Just like modern versions of Objective-C, Swift uses the ARC (Automatic Reference Counting) memory management model. The core concept of ARC is actually quite simple — an object is retained in memory by incrementing its reference count, and then released by decrementing that same count. Once an object’s retain count reaches zero — that object is deallocated from memory.


## Initializiong arrays


    let names = ["Arthur", "Ford", "Trillian", "Zaphod", "Marvin"]
    print(names)

 
 
let months:[String]     = ["January", "February", "March"]
let scores:[Int]        = [1, 5, 11, 18]
let fractions:[Double]  = [1/2, 2/3, 3/4, 4/5, 5/6]

## Data modeling

## Type conversion

## Application states


**Not Running** App was either terminated or just hasn’t been launched.
**Suspended**   App is still in memory.
**Background**  App is running in background.  Can be launched to this mode by system.
**Inactive**     App is either going to or coming from Active State.
**Active**  App is onscreen and running.

## Tableviews

## Access modifier

**Public** 
Like open access level, public access level enable an entity to be used outside the defining module (target). 

**internal (default access level)**
internal is the default access level. Internal classes and members can be accessed anywhere within the same module(target) they are defined. You typically use internalaccess when defining an app’s or a framework’s internal structure.

**fileprivate**
Restricts the use of an entity to its defining source file. You typically use fileprivate access to hide the implementation details of a specific piece of functionality when those details are used within an entire file. ie; 

**private — (most restrictive)**
Private access restricts the use of an entity to the enclosing declaration, and to extensions of that declaration that are in the same file. 

## Control transfer

    1.  Continue
        
    2.  Break
        
    3.  Fallthrough
        
    4.  Return

## Unit testing

    XCTest


## Application structure

## Find temperature

## Object comparision

## What’s the difference between == and ===?


 **==** is the equality operator, which tests that two things are equal for whatever definition of “equal” those things use. 
**For example, 5 == 5 is true because there == means an integer comparison, and the same is true for other built-in value types such as strings, booleans, and doubles.**

 **===** is the identity operator, which checks whether two instances of a class point to the same memory. This is different from equality, because two objects that were created independently using the same values will be considered equal using == but not === because they are different objects.

## Joining point

## Loop detection

## Approximation of pi

## Combinaition options in a tourments

    func factoriel(_ n:Int)  ->  Int
    
    {
    
    var i:Int  =  1
    
    var f:Int  =  1
    
    while i <= n {
    
    f = f * i
    
    i = i +  1
    
    }
    
    return f
    
    }
    
    func count(n:Int)  ->  Int
    
    {
    
    return  (factoriel(n)/(factoriel(n-2)*factoriel(2)))
    
    }
    
    print(count(n:6))

## Twins

## Intervals

## Summer sales

## Duplicates removal

    var arr:[Int]  =  [1,3,3,3,2,5]
    
    arr.sort{ $0  < $1  }
    
      
    
    func duplicateremoval(arr:[Int],n:Int)
    
    {
    
    var arrr = arr
    
    var temp =  [0,0,0,0]
    
    var j =  0;
    
    var s =  (n-1)
    
    var i =  0
    
    while(i < s)  {
    
    var next = i +  1
    
    if  (arrr[i]  != arrr[i+1]  )
    
    {
    
    temp[j]  = arrr[i];
    
    j = j +  1
    
    }
    
    i = i +  1
    
    }
    
    temp[j]  = arrr[s];
    
    j = j +  1
    
    for i in  0..<j {
    
    arrr[i]  = temp[i]
    
    print(arrr[i])
    
    }
    
      
    
    }
    
      
    
    duplicateremoval(arr:arr,n:arr.count)

## Summing based on factors
  

    func sumFactor(_ n:Int)  ->  Int
    
    {
    
    var res=0;
    
    var i=2
    
    var s =  Int(sqrt(Double(n)))
    
    while(i <= s )
    
    {
    
    if(n%i==0)
    
    {
    
    if(i==n/i){
    
    res+=i;
    
    }else
    
    {
    
    res+=(i+n/i)
    
    }
    
    }
    
    i=i+1
    
    }
    
    return  1+n+res;
    
    }
    
    var x = sumFactor(15)
    
    print(x);

## Array index


    let arr:Array = ["a","b","c"]
    find(arr, "c")!              // 2
    find(arr, "d")               // nil

Update for Swift 2.0:

    let arr = ["a","b","c"]
    
    let indexOfA = arr.indexOf("a") // 0
    let indexOfB = arr.indexOf("b") // 1
    let indexOfD = arr.indexOf("d") // nil


Update for Swift 3.0:

    let indexOfA = arr.index(of: "a")

Update for Swift 4.2:

    let arr = ["a","b","c","a"]
    
    let indexOfA = arr.firstIndex(of: "a") // 0
    let indexOfB = arr.lastIndex(of: "a") // 3

## Range sum

    var arr:[Int]=[1,1,1,1];
    
      
    
    func rangeSum(_ arr:[Int]  ,_ start:Int  ,_ end:Int)  ->  Int
    
    {
    
    if(start>end)
    
    {
    
    return  0;
    
    }else
    
    {
    
    return arr[start]+rangeSum(arr,start+1,end);
    
    }
    
    }
    
    var x=rangeSum(arr,1,3);
    
    print(x);

## Average

    var somme =  0
    
    var moyenne =  0
    
    var tab =  [1,  4,  6,  6,  3,  9,  3,  0,  3]
    
    //nombre d'elements
    
    var n = tab.count
    
    //somme
    
    var j=0
    
    while(j<n)  {
    
    somme += tab[j]
    
    j = j +  1
    
    }
    
    //moyenne = somme/nombre
    
    moyenne = somme / n;

## Simple Boolean expression

    func valid (_ i:Int,_ j:Int)  ->  Bool
    {  
    return i ==  1  || j ==  1  || i+j  ==  5 
    }

## Simple fix

## Failable Initializers


An initializer defined with init can be made failable by adding a ? or a ! after the init, which indicates the form of optional that will be produced by constructing an object with that initializer. For example, one could add a failable initializer to Int that attempts to perform a conversion from a String:

    extension Int {
        init?(fromString: String) { 
            if let i = fromString.toInt() {
                // Initialize
                self = i
            } else { 
                // return nil, discarding self is implied
                return nil
            }
        }
    }

In a failable initializer, return nil indicates that initialization has failed; no other value can be returned. In the example, failure occurs when the string could not be parsed as an integer. Otherwise, self is initialized to the parsed value.


## Range operators
 1. Closed Range Operator (lowerBound...upperBound)

It is declared using  `…`  (3 dots)operator.

**E.g:**  `1...3`  Defines range containing values 1,2,3

2. Half Open Range 

 It is declared using  `..<`  operator.

**E.g:**  `1..<3`  Defines range containing values 1 and 2

#### Example 3: One-sided range less than 2

1.  `let range =  ..<2`
2.  `print(range.contains(-1))`
3.  `print(range.contains(2))`

When you run the program, the output will be:

true
false

#### Example 4:One-sided range starting from 2

1.  `let range =  2...`
2.  `print(range.contains(100))`
3.  `print(range.contains(1))`

When you run the program, the output will be:

true
false
## Using extensions


With an extension you can add new functionality to an existing Swift class, structure, enumeration or protocol type. You can literally add on new functions to an existing class, even if you don’t have access to the original source code of that class.

    class Airplane
    {
        var altitude: Double = 0
    
        func setAltitude(feet: Double) {
            altitude = feet
        }
    }
    
    extension Airplane
    {
        func setAltitude(meter: Double) {
            altitude = meter * 3.28084
        }
    }

You can now use the setAltitude(meter:) function on an instance of class Airplane as an ordinary function, like this:

    let boeing = Airplane()
    boeing.setAltitude(meter: 12000)
    print(boeing.altitude)
    // Output: 39370.08

## Initializing tuples


    var point = (0, 0)
    
    point.0 = 10
    point.1 = 15

point // (10, 15)
Note: Tuple are value types. When you initialize a variable tuple with another one it will actually create a copy.

    var origin = (x: 0, y: 0)
     var point = origin 
     point.x = 3 
     point.y = 5


    var person = (firstName: "John", lastName: "Smith")
    var firstName = person.firstName // John
    var lastName = person.lastName // Smith

## Storyboard

## Initilisazion dictionaries

    var dict5 : [String:Double] = [String:Double]()

And of course in real life you are liable to do none of these things, but just assign an actual dictionary to your variable:

    var dict6 = ["howdy":1.0]

## Language syntax

## Operationals control flow

## Initialisaziong opitinals

## Array type


    var someArray = [SomeType]()
    var someArray = [SomeType](count: NumbeOfElements, repeatedValue: InitialValue)
    var someInts = [Int](count: 3, repeatedValue: 0)
    var someInts:[Int] = [10, 20, 30]

## Iterating Over an Array


    var someStrs = [String]()
    
    someStrs.append("Apple")
    someStrs.append("Amazon")
    someStrs += ["Google"]
    for item in someStrs {
       print(item)
    }

result −

    Apple
    Amazon
    Google

 h

    var someStrs = [String]()
    
    someStrs.append("Apple")
    someStrs.append("Amazon")
    someStrs += ["Google"]
    
    for (index, item) in someStrs.enumerated() {
       print("Value at index = \(index) is \(item)")
    }

 result 

    Value at index = 0 is Apple
    Value at index = 1 is Amazon
    Value at index = 2 is Google

## Iterating through dictionary

    let interestingNumbers = [
    "Prime": [2, 3, 5, 7, 11, 13],
    "Fibonacci": [1, 1, 2, 3, 5, 8],
    "Square": [1, 4, 9, 16, 25],
    ]
    
    var largest = 0
    var whichKind: String? = nil
    
    for (kind, numbers) in interestingNumbers {
        for number in numbers {
        if number > largest {
            whichKind = kind
            largest = number
        }
      }
    }
    
    print(whichKind)
    print(largest)

OUTPUT:

    Optional("Square")
    25

## Optional binding



## Uiviewcontroller lifecycle


**1. loadView**
This event creates the view that the controller manages. It is only called when the view controller is created programmatically. 

**2. loadViewIfNeeded**
Loads the view controller's view if it has not already been set.

**3. viewDidLoad**
The viewDidLoad event is only called when the view is created and loaded into memory but the bounds for the view are not defined yet. 

**4. viewWillAppear**
This event notifies the viewController whenever the view appears on the screen. In this step the view has bounds that are defined but the orientation is not set.
Called when the view is about to made visible. Default does nothing.

**5. viewWillLayoutSubviews**
This is the first step in the lifecycle where the bounds are finalised. If you are not using constraints or Auto Layout you probably want to update the subviews here.

**6. viewDidLayoutSubviews**
This event notifies the view controller that the subviews have been setup. It is a good place to make any changes to the subviews after they have been set. 

**7. viewDidAppear**
The viewDidAppear event fires after the view is presented on the screen. 

**8. viewWillDisappear**
The viewWillDisappear event fires when the view of presented viewController is about to disappear, dismiss, cover or hide behind other viewController. 

**9. viewDidDisappear**
This is the last step of the lifecycle that anyone can address as this event fires just after the view of presented viewController has been disappeared, dismissed, covered or hidden.


## Memory management

Just like modern versions of Objective-C, Swift uses the ARC (Automatic Reference Counting) memory management model. The core concept of ARC is actually quite simple — an object is retained in memory by incrementing its reference count, and then released by decrementing that same count. Once an object’s retain count reaches zero — that object is deallocated from memory.


## Initializiong arrays


    let names = ["Arthur", "Ford", "Trillian", "Zaphod", "Marvin"]
    print(names)

 
 
let months:[String]     = ["January", "February", "March"]
let scores:[Int]        = [1, 5, 11, 18]
let fractions:[Double]  = [1/2, 2/3, 3/4, 4/5, 5/6]

## Data modeling

## Type conversion

## Application states


**Not Running** App was either terminated or just hasn’t been launched.
**Suspended**   App is still in memory.
**Background**  App is running in background.  Can be launched to this mode by system.
**Inactive**     App is either going to or coming from Active State.
**Active**  App is onscreen and running.

## Tableviews

## Access modifier

**Public** 
Like open access level, public access level enable an entity to be used outside the defining module (target). 

**internal (default access level)**
internal is the default access level. Internal classes and members can be accessed anywhere within the same module(target) they are defined. You typically use internalaccess when defining an app’s or a framework’s internal structure.

**fileprivate**
Restricts the use of an entity to its defining source file. You typically use fileprivate access to hide the implementation details of a specific piece of functionality when those details are used within an entire file. ie; 

**private — (most restrictive)**
Private access restricts the use of an entity to the enclosing declaration, and to extensions of that declaration that are in the same file. 

## Control transfer

    1.  Continue
        
    2.  Break
        
    3.  Fallthrough
        
    4.  Return

## Unit testing

    XCTest


## Application structure

## Find temperature

## Object comparision

## What’s the difference between == and ===?


 **==** is the equality operator, which tests that two things are equal for whatever definition of “equal” those things use. 
**For example, 5 == 5 is true because there == means an integer comparison, and the same is true for other built-in value types such as strings, booleans, and doubles.**

 **===** is the identity operator, which checks whether two instances of a class point to the same memory. This is different from equality, because two objects that were created independently using the same values will be considered equal using == but not === because they are different objects.

## Iteration functions

## giving change

    import  Foundation
    
      
    
    var euros=[50,20,10,5];
    
    func rendreMonnaie(_ montant:Int)  ->  [Int]
    
    {
    
    var rendu =  [Int](repeating:  0, count: euros.count)
    
    var i=0
    
    var montant=montant
    
    while(i<euros.count)
    
    {
    
    rendu[i]  =  (montant/euros[i])
    
    montant %= euros[i]
    
    i = i +  1
    
    }
    
    return rendu;
    
    }
    
    var rendu=rendreMonnaie(55)
    
    var j=0
    
    while  (j<rendu.count)
    
    {
    
    if(rendu[j]>=1)
    
    {
    
    print("\(rendu[j])pieces de \(euros[j]) euro")
    
    }
    
    j = j +  1
    
    }




