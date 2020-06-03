

## calc.service.ts

import { Injectable } from '@angular/core';
 
@Injectable({
  providedIn: 'root'
})
export class CalcService {
 
  constructor() { }
 
  public add(...params: number[]): number {
    let result = 0;
    for (let val of params) {
        result += val;
    }
    return result;
  }
}

## app.component.ts

    import { Component } from '@angular/core';
    import { CalcService } from './service/calc.service';
     
    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
      styleUrls: ['./app.component.css']
    })
    export class AppComponent {
      title = 'app';
      sum: number = 0;
      constructor(calc:CalcService){
        this.sum = calc.add(1,2,3,4);
      }
    }

## app.component.html

    <h1>
        Welcome to {{ title }}!
        Sum is {{sum}}
    </h1>
