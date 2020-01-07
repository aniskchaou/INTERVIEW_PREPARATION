
 Angular 7 is completely ***based on components***. It consists of several components which forms a tree structure with parent and child components.

## SPA (Single Page Application)

***rewrites the current page rather than loading entire new pages from a server.*** That's the reason behind its reactive fast speed.

## Heading App files explanation
## Files used in Angular 7 App folder

Angular 7 App files which are mainly used in your project are given below:

-   **src folder:**  This is the folder which contains the main code files related to your angular application.
-   **app folder:**  The app folder contains the files, you have created for app components.
-   **app.component.css:**  This file contains the cascading style sheets code for your app component.
-   **app.component.html:**  This file contains the html file related to app component. This is the template file which is used by angular to do the data binding.
-   **app.component.spec.ts:**  This file is a unit testing file related to app component. This file is used along with other unit tests. It is run from Angular CLI by the command ng test.
-   **app.component.ts:**  This is the most important typescript file which includes the view logic behind the component.
-   **app.module.ts:**  This is also a typescript file which includes all the dependencies for the website. This file is used to define the needed modules to be imported, the components to be declared and the main component to be bootstrapped.

## Other Important files

-   **package.json:**  This is npm configuration file. It includes details about your website's package dependencies along with details about your own website being a package itself.
-   **package-lock.json :**  This is an auto-generated and modified file that gets updated ***whenever npm does an operation related to node_modules or package.json***
-   **angular.json:**  It is very important configuration file related to your angular application.  **It defines the structure of your app and includes any settings associated with your application.**  Here, you can specify environments on this file (development, production). This is the file where we add Bootstrap file to work with Angular 7.
-   **.gitignore:**  This file is related to the source control git.
-   **.editorconfig:**  This is a simple file which is used to maintain consistency in code editors to organize some basics such as indentation and whitespaces.
-   **assets folder:**  This folder is a placeholder for resource files which are used in the application such as images, locales, translations etc.
-   **environments folder:**  The environments folder is used to hold the environment configuration constants that help when building the angular application. The constants are defined in 2 separate .ts files (environment.ts and environment.prod.ts), where these constants are used within the angular.json file by the Angular CLI. For example, if you run the ng build command, it will build the application using the development environment settings, whereas the command ng build ?prod will build the project using the production environment settings.
-   **browserlist:**  This file is used by autoprefixer that adjusts the CSS to support a list of defined browsers.
-   **favicon.ico:**  This file specifies a small icon that appears next to the browser tab of a website.
-   **index.html:**  This is the entry file which holds the high level container for the angular application.
-   **karma.config.js:**  This file specifies the config file for the Karma Test Runner, Karma has been developed by the AngularJS team which can run tests for both AngularJS and Angular 2+
-   **main.ts:**  As defined in angular.json file, this is the main ts file that will first run. This file bootstraps (starts) the AppModule from app.module.ts , and it can be used to define global configurations.
-   **polyfills.ts:**  This file is a set of code that can be used to provide compatibility support for older browsers. Angular 7 code is written mainly in ES6+ language specifications which is getting more adopted in front-end development, so since not all browsers support the full ES6+ specifications, pollyfills can be used to cover whatever feature missing from a given browser.
-   **styles.css:/**  This is a global css file which is used by the angular application.
-   **tests.ts:**  This is the main test file that the Angular CLI command ng test will use to traverse all the unit tests within the application and run them.
-   **tsconfig.json:**  This is a typescript compiler configuration file.
-   **tsconfig.app.json:**  This is used to override the tsconfig.json file with app specific configurations.
-   **tsconfig.spec.json:**  This overrides the tsconfig.json file with app specific unit test configurations.
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

The ng add command uses the npm package manager to install the library package, and invokes schematics that are included in the package to other scaffolding within the project code, such as adding import statements, fonts, themes, and so on.


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

    1.  import { Component, OnInit } from '@angular/core';
    
    3.  @Component({
    4.  selector: 'app-server2',
    5.  templateUrl: './server2.component.html',
    6.  styleUrls: ['./server2.component.css']
    7.  })
    8.  export class Server2Component implements OnInit {
    9.  allowNewServer = false;
    10.  serverCreationStatus = 'No server is created.';
    11.  serverName = 'TestServer';
    12.  serverCreated = false;
    
    14.  /*constructor() {
    15.  setTimeout(() =>{
    16.  this.allowNewServer = true;
    17.  }, 5000);
    18.  }*/
    
    20.  ngOnInit() {
    21.  }
    22.  onCreateServer() {
    23.  this.serverCreated = true;
    24.  this.serverCreationStatus = 'Server is created. Name of the server is' + this.serverName;
    25.  }
    26.  OnUpdateServerName(event: Event) {
    27.  this.serverName = (<HTMLInputElement>event.target).value;
    28.  }
    29.  }

**component.html file:**

    1.  <p>
    2.  Server2 is also working fine.
    3.  </p>
    
    4.  <label>Server Name</label>
    5.  <!--<input  type="text"
    6.  class="form-control"
    7.  (input)="OnUpdateServerName($event)">-->
    8.  <input  type="text"
    9.  class="form-control"
    10.  [(ngModel)]="serverName">
    11.  <!--<p>{{serverName}}</p>-->
    12.  <button
    13.  class="btn btn-primary"
    14.  [disabled]="allowNewServer"
    15.  (click)="onCreateServer()">Add Server</button>
    16.  <p *ngIf="serverCreated"> Server is created. Server name is {{serverName}}</p>
    17. 

# Angular 7 String Interpolation

In Angular, String interpolation is used to display dynamic data on HTML template (at user end). It facilitates you to make changes on component.ts file and fetch data from there to HTML template (component.html file).

### For example:

**component.ts file:**

    1.  import {Component} from '@angular/core';
    2.  @Component(
    3.  {selector: 'app-server',
    4.  templateUrl: 'server.component.html'})
    5.  export class ServerComponent {
    6.  serverID: number = 10;
    7.  serverStatus: string = 'Online';
    8.  }

Here, we have specified serverID and serverStatus with some values. Let's use this in "component.html" file.

**component.html file:**

1.  `<p>Server with ID {{serverID}} is {{serverStatus}}. </p>`
# Angular 7 Event Binding

Angular facilitates us to bind the events along with the methods. This process is known as event binding. Event binding is used with parenthesis ().

Let's see it by an example:

    1.  @Component({
    2.  selector: 'app-server2',
    3.  templateUrl: './server2.component.html',
    4.  styleUrls: ['./server2.component.css']
    5.  })
    6.  export class Server2Component implements OnInit {
    7.  
    8. allowNewServer = false;
    9.  
    10. serverCreationStatus= 'No Server is created.';
    11.  constructor() {
    12.  setTimeout(() =>{
    13.  this.allowNewServer = true;
    14.  }, 5000);
    15.  }
    
    16.  ngOnInit() {
    17.  }
    
    18.  }

**component.html file:**

    1.  <p>
    2.  Server2 is also working fine.
    3.  </p>
    4.  <button  class="btn btn-primary"
    5.  [disabled]="!allowNewServer" >Add Server</button>
    6.  <!--<h3 [innerText]= "allowNewServer"></h3>-->
    
    7.  {{serverCreationStatus}}

# Angular 7 Property Binding



**For example**

We are going to add a button to  **"component.html"**  page.

    1.  <p>
    2.  Server2 is also working fine.
    3.  </p>
    4.  <button  class="btn btn-primary">Add Server</button>

**component.ts file:**

    1.  import { Component, OnInit } from '@angular/core';
    
    3.  @Component({
    4.  selector: 'app-server2',
    5.  templateUrl: './server2.component.html',
    6.  styleUrls: ['./server2.component.css']
    7.  })
    8.  export class Server2Component implements OnInit {
    
    10.  constructor() { }
    
    12.  ngOnInit() {
    13.  }
    
    15.  }

**Output:**

![Angular 7 Property Binding](https://static.javatpoint.com/tutorial/angular7/images/angular7-property-binding-output.png)

## Let's see how property binding works?

First, we are going to disable the button by using disabled attribute.

    1.  <p>
    2.  Server2 is also working fine.
    3.  </p>
    4.  <button  class="btn btn-primary" disabled>Add Server</button>

Now, the button is disabled.

Let's add a new property "allowNewServer" in "component.ts" file which will disable the button automatically but after a specific (settable) time.

**component.ts file:**

    1.  import { Component, OnInit } from '@angular/core';
    
    3.  @Component({
    4.  selector: 'app-server2',
    5.  templateUrl: './server2.component.html',
    6.  styleUrls: ['./server2.component.css']
    7.  })
    8.  export class Server2Component implements OnInit {
    9.  allowNewServer = false;
    
    11.  constructor() {
    12.  setTimeout(() =>{
    13.  this.allowNewServer = true;
    14.  }, 5000);
    15.  }
    
    17.  ngOnInit() {
    18.  }
    
    20.  }

**component.html file:**

    1.  <p>
    2.  Server2 is also working fine.
    3.  </p>
    4.  <button  class="btn btn-primary"
    5.  [disabled]="allowNewServer">Add Server</button>

Here, we set a time of 5000 millisecond or 5 second. After 5 seconds, the button will be disabled automatically.

This is an example of property binding where a property is bound dynamically.

**Output:**

![Angular 7 Property Binding](https://static.javatpoint.com/tutorial/angular7/images/angular7-property-binding-output2.png)

    1.  <p>
    2.  Server2 is also working fine.
    3.  </p>
    4.  <button  class="btn btn-primary"
    5.  [disabled]="!allowNewServer" >Add Server</button>

By using the above code, you can allow the disabled button after 5 seconds automatically.

# Angular 7 Pipes

In Angular 1, filters are used which are later called Pipes onwards Angular2. In Angular 7, it is known as pipe and used to transform data. It is denoted by symbol |

### Syntax:

1.  {{title | uppercase}}

Pipe takes integers, strings, arrays, and date as input separated with |. It transforms the data in the format as required and displays the same in the browser.

Let's see an example using pipes. Here, we display the title text in upper and lower case by using pipes.

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

    1.  import { Component } from '@angular/core';
    
    3.  @Component({
    4.  selector: 'app-root',
    5.  templateUrl: './app.component.html',
    6.  styleUrls: ['./app.component.css']
    7.  })
    8.  export class AppComponent {
    9.  title = 'my-first-app';
    10.  todaydate = new Date();
    11.  jsonval = {name: 'Alex', age: '25', address:{a1: 'Paris', a2: 'France'}};
    12.  months = ['Jan', 'Feb', 'Mar', 'April', 'May', 'Jun',
    13.  'July', 'Aug', 'Sept', 'Oct', 'Nov', 'Dec'];
    14.  }

Use the different built-in pipe symbols in component.html file:

**component.html file:**

    1.  <div  style = "width:100%;">
    2.  <div  style = "width:40%;float:left;border:solid 1px black;">
    3.  <h1>Uppercase Pipe</h1>
    4.  <b>{{title | uppercase}}</b><br/>
    5.  <h1>Lowercase Pipe</h1>
    6.  <b>{{title | lowercase}}</b>
    7.  <h1>Currency Pipe</h1>
    8.  <b>{{6589.23 | currency:"USD"}}</b><br/>
    9.  <b>{{6589.23 | currency:"USD":true}}</b> //Boolean true is used to get the sign of the currency.
    10.  <h1>Date pipe</h1>
    11.  <b>{{todaydate | date:'d/M/y'}}</b><br/>
    12.  <b>{{todaydate | date:'shortTime'}}</b>
    13.  <h1>Decimal Pipe</h1>
    14.  <b>{{ 454.78787814 | number: '3.4-4' }}</b> // 3 is for main integer, 4 -4 are for integers to be displayed.
    15.  </div>
    16.  <div  style = "width:40%;float:left;border:solid 1px black;">
    17.  <h1>Json Pipe</h1>
    18.  <b>{{ jsonval | json }}</b>
    19.  <h1>Percent Pipe</h1>
    20.  <b>{{00.54565 | percent}}</b>
    21.  <h1>Slice Pipe</h1>
    22.  <b>{{months | slice:2:6}}</b>
    23.  // here 2 and 6 refers to the start and the end index
    24.  </div>
    25.  </div>

**Output:**

You can see the use of all built-in pipes here:

![Angular 7 Pipes](https://static.javatpoint.com/tutorial/angular7/images/angular7-pipes-output2.png)

## How to create a custom pipe?

To create a custom pipe, create a new ts file and use the code according to the work you have to do. You have to import Pipe, PipeTransform from Angular/Core. Let's create a sqrt custom pipe.

**component.ts file:**

    1.  import {Pipe, PipeTransform} from '@angular/core';
    2.  @Pipe ({
    3.  name : 'sqrt'
    4.  })
    5.  export class SqrtPipe implements PipeTransform {
    6.  transform(val : number) : number {
    7.  return Math.sqrt(val);
    8.  }
    9.  }

Now, it's turn to make changes in the app.module.ts. Create a class named as SqrtPipe. This class will implement the PipeTransform. The transform method defined in the class will take argument as the number and will return the number after taking the square root.

As, we have created a new file so, we need to add the same in app.module.ts.

**Module.ts file:**

1. 

     import { BrowserModule } from '@angular/platform-browser';
    2.  import { NgModule } from '@angular/core';
    3.  import { AppComponent } from './app.component';
    4.  import { NewCmpComponent } from './new-cmp/new-cmp.component';
    5.  import { ChangeTextDirective } from './change-text.directive';
    6.  import { SqrtPipe } from './app.sqrt';
    7.  @NgModule({
    8.  declarations: [
    9.  SqrtPipe,
    10.  AppComponent,
    11.  NewCmpComponent,
    12.  ChangeTextDirective
    13.  ],
    14.  imports: [
    15.  BrowserModule
    16.  ],
    17.  providers: [],
    18.  bootstrap: [AppComponent]
    19.  })
    20.  export class AppModule { }

Now, use sqrt pipe in component.html file.

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

First, generate a component for the control by using the following syntax:

1.  `ng generate component NameEditor`

To register a single form control, you have to import the FormControl class into your component and create a new instance of the form control to save as a class property. The FormControl class is the basic building block used in reactive forms.

**Write the following code in name-editor.component.ts file:**


    import { Component } from '@angular/core';
    2.  import { FormControl } from '@angular/forms';
    3.  @Component({
    4.  selector: 'app-name-editor',
    5.  templateUrl: './name-editor.component.html',
    6.  styleUrls: ['./name-editor.component.css']
    7.  })
    8.  export class NameEditorComponent {
    9.  name = new FormControl('');
    10.  }

**3. Now, register the control in the template**

After creating the control in the component class, you have to add it to the form control element in the template. Use the formControl binding provided by FormControlDirective to update the template with the form control.

    1.  <label>
    2.  Name:
    3.  <input type="text" [formControl]="name">
    4.  </label>

We have registered the form control to the name input element in the template. Now, the form control and DOM element communicate with each other and the view reflects changes in the model, and the model reflects changes in the view.

**4. Display the component**

Add the form control component to the template to display the form. Add the following code to app.component.html.

1.  <app-name-editor></app-name-editor>

**Output:**

![Angular Reactive Forms](https://static.javatpoint.com/tutorial/angular7/images/angular-reactive-forms-output.png)

# Template-driven Forms



    1.  export class Hero {
    2.  constructor(
    3.  public id: number,
    4.  public name: string,
    5.  public power: string,
    6.  public alterEgo?: string
    7.  ) { }
    8.  }


#### Create a Form component

**An Angular form consists of two parts:**

-   HTML based template
-   A component class to handle data and users

Now, generate a new component named  **HeroForm**  by using the following command:

1.  ng generate component HeroForm

  
![Template-driven Forms](https://static.javatpoint.com/tutorial/angular7/images/angular-template-driven-forms2.png)

Write down the following code in  **hero-form.component.ts**

    1.  import { Component } from '@angular/core';
    2.  import { Hero } from '../hero';
    3.  @Component({
    4.  selector: 'app-hero-form',
    5.  templateUrl: './hero-form.component.html',
    6.  styleUrls: ['./hero-form.component.css']
    7.  })
    8.  export class HeroFormComponent {
    9. 
    10.  powers = ['Really Smart', 'Super Flexible',
    11.  'Super Hot', 'Weather Changer'];
    12.  model = new Hero(18, 'Dr IQ', this.powers[0], 'Chuck Overstreet');
    13.  submitted = false;
    14. 
    15.  onSubmit() { 
    16. this.submitted = true; }
    18.  get diagnostic() { return JSON.stringify(this.model); }
    19.  }


Use the following code inside  **app.module.ts**  file:

    1.  import { NgModule } from '@angular/core';
    2.  import { BrowserModule } from '@angular/platform-browser';
    3.  import { FormsModule } from '@angular/forms';
    4.  import { AppComponent } from './app.component';
    5.  import { HeroFormComponent } from './hero-form/hero-form.component';
    6.  @NgModule({
    7.  imports: [
    8.  BrowserModule,
    9.  FormsModule
    10.  ],
    11.  declarations: [
    12.  AppComponent,
    13.  HeroFormComponent
    14.  ],
    15.  providers: [],
    16.  bootstrap: [ AppComponent ]
    17.  })
    18.  export class AppModule { }
Use the following code in hero-form.component.html

    1.  <div class="container">
    2.  <h1>Hero Form</h1>
    3.  <form>
    4.  <div class="form-group">
    5.  <label for="name">Name</label>
    6.  <input type="text"  class="form-control" id="name" required>
    7.  </div>
    8.  <div class="form-group">
    9.  <label for="alterEgo">Alter Ego</label>
    10.  <input type="text"  class="form-control" id="alterEgo">
    11.  </div>
    12.  <button type="submit"  class="btn btn-success">Submit</button>
    13.  </form>
    14.  </div>


## Add power list by using *ngFor



    1.  <div class="form-group">
    2.  <label for="power">Hero Power</label>
    3.  <select class="form-control" id="power" required>
    4.  <option *ngFor="let pow of powers" [value]="pow">{{pow}}</option>
    5.  </select>
    6.  </div>



**Output:**

![Template-driven Forms](https://static.javatpoint.com/tutorial/angular7/images/angular-template-driven-forms-output.png)

You can check here Hero's power.

![Template-driven Forms](https://static.javatpoint.com/tutorial/angular7/images/angular-template-driven-forms3.png)




