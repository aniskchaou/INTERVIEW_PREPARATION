## Angular Pipes

In Angular 1, filters are used which are later called Pipes onwards Angular2. In Angular 7, it is known as pipe and used to transform data. It is denoted by symbol |


**Example:**



     export class AppComponent {
     title = 'my-first-app';
     }
    
    
    <h1>
    {{ title | uppercase }} <br/></h1>
    <h1>
    {{ title | lowercase }} <br/></h1>


## Angular 7 Built-in Pipes

Angular 7 provides some built-in pipes:

Lowercasepipe
Uppercasepipe
Datepipe
Currencypipe
Jsonpipe
Percentpipe
Decimalpipe
Slicepipe

**component.html** 

       <b>Uppercase Pipe</b>
    {{title | uppercase}}
       
    <b>Lowercase Pipe</b>
    {{title | lowercase}}
    
    <b>Currency Pipe</b>
    {{6589.23 | currency:"USD"}}
    {{6589.23 | currency:"USD":true}}
    
    <b>Date pipe</b>
    {{todaydate | date:'d/M/y'}}
    {{todaydate | date:'shortTime'}}
    
    <b>Decimal Pipe</b>
    {{ 454.78787814 | number: '3.4-4' }}
    
    
    <b>Json Pipe</b>
    {{ jsonval | json }}
    
    <b>Percent Pipe</b>
    {{00.54565 | percent}}
    
    <b>Slice Pipe</b>
    {{months | slice:2:6}}


## Create a custom pipe

**sqrt.pipe.ts** 

      import {Pipe, PipeTransform} from '@angular/core';
     @Pipe ({
     name : 'sqrt'
    })

 

    export class SqrtPipe implements PipeTransform {
      transform(val : number) : number {
      return Math.sqrt(val);
     }
    }

**component.html** 

    <h1>Example of Custom Pipe</h1>
    <h2>Square root of 625 is: {{625 | sqrt}}</h2><br/>
    <h2>Square root of 169 is: {{169 | sqrt}}</h2>
