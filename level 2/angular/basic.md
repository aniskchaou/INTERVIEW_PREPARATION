
 Angular 7 is completely ***based on components***. It consists of several components which forms a tree structure with parent and child components.

## SPA (Single Page Application)

***rewrites the current page rather than loading entire new pages from a server.*** That's the reason behind its reactive fast speed.

## Heading App files explanation
## Files used in Angular 7 App folder

Angular 7 App files which are mainly used in your project are given below:

-   **src folder:**  This is the folder which **contains the main code files related to your angular application.**
-   **app folder:**  The app folder contains the files, you have created for app components.
-   **app.component.css:**  This file **contains the cascading style sheets** code for your app component.
-   **app.component.html:**  This file **contains the html file** related to app component. This is the template file which is used by angular to do the data binding.
-   **app.component.spec.ts:**  **This file is a unit testing file related to app component**. This file is used along with other unit tests. It is run from **Angular CLI by the command ng test.**
-   **app.component.ts:**  This is the most important typescript file which includes the view logic behind the component.
-   **app.module.ts:**  This is also a typescript file which **includes all the dependencies for the website.** This file is used to define the needed modules to be imported, the components to be declared and the main component to be bootstrapped.

## Other Important files

-   **package.json:**  This is npm configuration file. **It includes details about your website's package dependencies** along with details about your own website being a package itself.
-   **package-lock.json :**  This is an auto-generated and modified file that gets updated ***whenever npm does an operation related to node_modules or package.json***
-   **angular.json:**  It is very important configuration file related to your angular application.  **It defines the structure of your app and includes any settings associated with your application.**  
-   **assets folder:**  This folder is a placeholder for resource files which are used in the application such as images, locales, translations etc.

-   **index.html:**  This is the entry file which holds the high level container for the angular application.
-   **main.ts:**  As defined in angular.json file, this is the main ts file that will first run. **This file bootstraps (starts) the AppModule from app.module.ts , and it can be used to define global configurations.**
-   **styles.css:/**  This is a global css file which is used by the angular application.

## CLI commands
**add**

It is used to add support for an external library to your project.

**build**

It compiles an Angular app into an output directory named dist/ at the given output path. Must be executed from within a workspace directory.

**config**

It retrieves or sets Angular configuration values in the angular.json file for the workspace.

**doc**

It opens the official Angular documentation (angular.io) in a browser, and searches for a given keyword.

**e2e**


It builds and serves an Angular app, then runs end-to-end tests using Protractor.

**generate**


It generates and/or modifies files based on a schematic.

**help**

It provides a list of available commands and their short descriptions.

**lint**


It is used to run linting tools on Angular app code in a given project folder.

**new**


It creates a new workspace and an initial Angular app.

**run**

It runs an Architect target with an optional custom builder configuration defined in your project.

**serve**


It builds and serves your app, rebuilding on file changes.

**test**


It runs unit tests in a project.

**update**

It updates your application and its dependencies. See https://update.angular.io/

**version**


It utputs Angular CLI version.

**xi18n**

It extracts i18n messages from source code.



## Installing libraries

Libraries are published as npm packages and integrated with Angular CLI. 

### Syntax

    1.  ng add <lib_name>



(https://www.javatpoint.com/angular-7-components)

![Angular 7 Architecture](https://static.javatpoint.com/tutorial/angular7/images/angular-7-architecture.png)

## Modules

Angular 7 NgModules are different from other JavaScript modules. **Every Angular 7 app has a root module known as AppModule. It provides the bootstrap mechanism that launches the application.**

**Generally, every Angular 7 app contains many functional modules.**

## Routing

In Angular 7,  **Router**  is an NgModule which provides a service that facilitates developers to define a navigation path among the different application states and view hierarchies in their app.

# Use of *ngIf directive to change the output conditionally

## Example:

**component.ts file:**

      import { Component } from '@angular/core';
    
    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
      styleUrls: ['./app.component.css']
    })
    export class AppComponent {
      people: any[] = [
        {
          "name": "Douglas  Pace",
          "age": 35
        },
        {
          "name": "Mcleod  Mueller",
          "age": 32
        },
        {
          "name": "Day  Meyers",
          "age": 21
        },
        {
          "name": "Aguirre  Ellis",
          "age": 34
        },
        {
          "name": "Cook  Tyson",
          "age": 32
        }
      ];
    }
    }

**component.html file:**

    <h4>NgIf</h4>
    <ul *ngFor="let person of people">
      <li *ngIf="person.age < 30"> (1)
      {{ person.name }} ({{ person.age }})
      </li>
    </ul>

# Angular 7 String Interpolation

In Angular, String interpolation is used to display dynamic data on HTML template (at user end). It facilitates you to make changes on component.ts file and fetch data from there to HTML template (component.html file).

### For example:

**component.ts file:**

    export  class  AppComponent {
    
    name  =  "hello world !"
    
    }


**component.html file:**

    <b>{{name}}</b>

# Angular 7 Event Binding

Angular facilitates us to bind the events along with the methods. This process is known as event binding. Event binding is used with parenthesis ().

Let's see it by an example:

    export class AppComponent {
      clickMessage = '';
    
      onClickMe() {
        this.clickMessage = 'You are my hero!';
      }
    }

**component.html file:**

 

     <button (click)="onClickMe()">Click me!</button>

# Angular 7 Property Binding



**For example**

We are going to add a button to  **"component.html"**  page.

 

      <img [alt]="bookName" [src]="bookPictureUrl">
    <button type="button" [disabled]="!isAvailable">BUY</button>

**component.ts file:**

       export class AppComponent {
      bookName = 'eXtreme Programming Explained';
      bookPictureUrl = 'https://robohash.org/xp?set=set4';
      isAvailable = false;
    }


## Two way Data Binding
**component.ts**

    export  class  AppComponent {
    
    fullName:  string  =  "Hello JavaTpoint";
    
    }
**component.html**

    <h2>Two-way Binding Example</h2>    
       <input [(ngModel)]="fullName" /> <br/><br/>    
    <p> {{fullName}} </p>  

# Angular 7 Pipes

In Angular 1, filters are used which are later called Pipes onwards Angular2. **In Angular 7, it is known as pipe and used to transform data. It is denoted by symbol |**

### Syntax:

    1.  {{title | uppercase}}



### Example:

Define a variable named "title" in component.ts file.

    1.  import { Component } from '@angular/core';
    
    3.  @Component({
    4.  selector: 'app-root',
    5.  templateUrl: './app.component.html',
    6.  styleUrls: ['./app.component.css']
    7.  })
    8.  export class AppComponent {
    9.  title = 'my-first-app';
    10.  }

Use the pipe symbol in component.html file:

    1.  <h1>
    2.  {{ title | uppercase }} <br/></h1>
    3.  <h1>
    4.  {{ title | lowercase }} <br/></h1>

**Output:**

Run ng serve and see the result. You will see the following result.

![Angular 7 Pipes](https://static.javatpoint.com/tutorial/angular7/images/angular7-pipes-output1.png)  

Here, you can see that pipes have changed the tittle in upper and lowercase.

## Angular 7 Built-in Pipes

Angular 7 provides some built-in pipes:

-   Lowercasepipe
-   Uppercasepipe
-   Datepipe
-   Currencypipe
-   Jsonpipe
-   Percentpipe
-   Decimalpipe
-   Slicepipe

You have seen the lowercasepipe and uppercasepipe examples. Now, let's take some examples to see how the other pipes work.

### Example:

Define the required variables in component.ts file.

**component.ts file:**

        export class AppComponent {
    
      title = 'my-first-app';
      todaydate = new Date();
      jsonval = {name: 'Alex', age: '25', address:{a1: 'Paris', a2: 'France'}};
      months = ['Jan', 'Feb', 'Mar', 'April', 'May', 'Jun','July', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec'];
      
    }

Use the different built-in pipe symbols in component.html file:

**component.html file:**

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

**Output:**

You can see the use of all built-in pipes here:

![Angular 7 Pipes](https://static.javatpoint.com/tutorial/angular7/images/angular7-pipes-output2.png)

## How to create a custom pipe?


**sqrt.pipe.ts file:**

      import {Pipe, PipeTransform} from '@angular/core';
     @Pipe ({
     name : 'sqrt'
    })
    
     export class SqrtPipe implements PipeTransform {
      transform(val : number) : number {
      return Math.sqrt(val);
     }
    }
    
**component.html file:**



    <h1>Example of Custom Pipe</h1>
    2.  <h2>Square root of 625 is: {{625 | sqrt}}</h2><br/>
    3.  <h2>Square root of 169 is: {{169 | sqrt}}</h2>



# Angular Reactive Forms



    1.  import { ReactiveFormsModule } from '@angular/forms';
    2.  @NgModule({
    3.  imports: [
    4.  // other imports ...
    5.  ReactiveFormsModule
    6.  ],
    7.  })
    8.  export class AppModule { }

**2. Generate and Import a new form control**

    export class AppComponent {
    
      personForm: FormGroup
    
      sex = ['', 'Male', 'Female']
    
      constructor() {
        this.personForm = this.createFormGroup()
      }
    
      createFormGroup() {
        return new FormGroup({
          name: new FormControl(''),
          sex : new FormControl()
        })
      }
       
      onSubmit(){
        console.log(this.personForm.value)
      }
    }

**3. Now, register the control in the template**

<form [formGroup]="personForm" (ngSubmit)="onSubmit()" novalidate>

    <input formControlName="name" />
    <select formControlName="sex">
      <option *ngFor="let s of sex" [value]="s">{{s}}</option>
    </select>
  
    <button type="submit" [disabled]="personForm.pristine">Save</button>
   
  </form>

# Template-driven Forms



    export class Person {
        constructor(
        public id: number,
        public name: string,
        public sex: string,
        ) { }
        }


#### Create a Form component


     export class AppComponent {
    
      sex = ['','Male', 'Female'];
      
      model = new Person(1, '', this.sex[0]);
        submitted = false;
       
        onSubmit() { 
       this.submitted = true; 
       console.log(this.model);
       }
    
       
    }


Use the following code in hero-form.component.html

    <div>
      <label for="name">Name</label>
      <input type="text"  id="name"
             required
             [(ngModel)]="model.name" name="name">
    </div>
    
    
    <div >
      <label for="sex">Sex</label>
      <select  id="sex"
              required
              [(ngModel)]="model.sex" name="sex">
        <option *ngFor="let s of sex" [value]="s">{{s}}</option>
      </select>
      
      <button type="button"  (click)="onSubmit()">New Hero</button>
    
      
    </div>




