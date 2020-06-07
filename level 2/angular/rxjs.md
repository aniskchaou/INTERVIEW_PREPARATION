## RXJS

RxJS (Reactive Extensions for JavaScript) is a library for reactive programming using observables that makes it easier to compose asynchronous or callback-based code.
**Operators**
Operators are functions that build on the observables foundation to enable sophisticated manipulation of collections. For example, RxJS defines operators such as map(), filter(), concat(), and flatMap().


**Map operator**

    import { map } from 'rxjs/operators';
    
    const nums = of(1, 2, 3);
    
    const squareValues = map((val: number) => val * val);
    const squaredNums = squareValues(nums);
    
    squaredNums.subscribe(x => console.log(x));
    
    // Logs
    // 1
    // 4
    // 9
**Filter operator**

    import { from } from 'rxjs';
    import { filter } from 'rxjs/operators';
    
    //emit (1,2,3,4,5)
    const source = from([1, 2, 3, 4, 5]);
    //filter out non-even numbers
    const example = source.pipe(filter(num => num % 2 === 0));
    //output: "Even number: 2", "Even number: 4"
    const subscribe = example.subscribe(val => console.log(`Even number: ${val}`));
