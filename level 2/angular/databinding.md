## Angular 7 String Interpolation

 **component.ts**

    export  class  AppComponent {
    
    name  =  "hello world !"
    
    }

**component.html** 

    {{name}}

## Angular  Event Binding

 **component.ts**

    export class AppComponent {
      clickMessage = '';
    
      onClickMe() {
        this.clickMessage = 'You are my hero!';
      }
    }

**component.html** 

    <button (click)="onClickMe()">Click me!</button>

## Angular  Property Binding

**component.html** 

      <img [alt]="bookName" [src]="bookPictureUrl">
    <button type="button" [disabled]="!isAvailable">BUY</button>

**component.ts** 

       export class AppComponent {
      bookName = 'eXtreme Programming Explained';
      bookPictureUrl = 'https://robohash.org/xp?set=set4';
      isAvailable = false;
    }

## Two way Data Binding

**component.ts**

    export  class  AppComponent {
    
    fullName:string = "Hello JavaTpoint";
    
    }

**component.html**
  

       <input [(ngModel)]="fullName" /> <br/><br/>    
    <p> {{fullName}} </p>  
