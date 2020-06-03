### What is Angular Framework?

Angular is a  **TypeScript-based open-source**  front-end platform that makes it easy to build applications with in web/mobile/desktop.

### What is the difference between AngularJS and Angular?
**AngularJS**


It is based on MVC architecture
This uses use JavaScript to build the application
Based on controllers concept
Not a mobile friendly framework

**Angular**
This is based on Service/Controller
Introduced the typescript to write the application
This is a component based UI approach
Developed considering mobile platform

### What are the key components of Angular?



1.  **Component:**  These are **the basic building** blocks of angular application
2.  **Modules:**  An application is divided into **logical pieces** and each piece of code is called as "module" which perform a single task.
3.  **Templates:**  **This represent the views** of an Angular application.
4.  **Services:**  It is used to create **components which can be shared across the entire application.**
5.  **Metadata:**  This can be used to add **more data to an Angular class.**

### What are directives?

Directives add **behaviour to an existing DOM element** or an existing component instance.

    import { Directive, ElementRef, Input } from '@angular/core';
    
    @Directive({ selector: '[myHighlight]' })
    export class HighlightDirective {
        constructor(el: ElementRef) {
           el.nativeElement.style.backgroundColor = 'yellow';
        }
    }

Now this directive extends HTML element behavior with a yellow background as below

    <p myHighlight>Highlight me!</p>

### What are components?

Components are the most basic UI building block of an Angular app 

    import { Component } from '@angular/core';
    
    @Component ({
       selector: 'my-app',
       template: ` <div>
     <h1>{{title}}</h1>
     <div>Learn Angular6 with examples</div>
     </div> `,
    })

    export class AppComponent {
       title: string = 'Welcome to Angular world';
    }
### What is a template?

A template is a HTML view where you **can display data by binding controls to properties of an Angular component.** 

    import { Component } from '@angular/core';
    
    @Component ({
       selector: 'my-app',
       template: '
     <div>
             <h1>{{title}}</h1>
             <div>Learn Angular</div>
          </div>
       '
    })
    
    export class AppComponent {
       title: string = 'Hello World';
    }
### What is a module?

Modules are **logical boundaries in your application and the application is divided into separate modules** to separate the functionality of your application.

    import { NgModule }      from '@angular/core';
    import { BrowserModule } from '@angular/platform-browser';
    import { AppComponent }  from './app.component';
    
    @NgModule ({
       imports:      [ BrowserModule ],
       declarations: [ AppComponent ],
       bootstrap:    [ AppComponent ]
    })
    export class AppModule { }
## What is a data binding?

Data binding is a core concept in Angular and allows to define communication between a component and the DOM, 

1.  **From the Component to the DOM:**  **Interpolation:**  {{ value }}: Adds the value of a property from the component

    < li >Name: {{ user.name }}</ li >
    < li >Address: {{ user.address }}</ li >

**Property binding:** [property]=”value”: The value is passed from the component to the specified property or simple HTML attribute

    < input type="email" [value]="user.email">

2.  **From the DOM to the Component:**  **Event binding: (event)=”function”:**  When a specific DOM event happens (eg.: click, change, keyup), call the specified method in the component

    < button (click)="logout()"></button>

3.  **Two-way binding:**  **Two-way data binding:**  [(ngModel)]=”value”: Two-way data binding allows to have the data flow both ways. For example, in the below code snippet, both the email DOM input and component email property are in sync

    < input type="email" [(ngModel)]="user.email">

### What is the difference between constructor and ngOnInit?

TypeScript classes has a default method called constructor which is normally used for the initialization purpose. 

    export class App implements OnInit{
      constructor(){
         //called first time before the ngOnInit()
      }
    
      ngOnInit(){
         //called after the constructor and called  after the first ngOnChanges()
      }
    }
### What is a service?

A service is used when **a common functionality needs to be provided to various modules**. 

    import { Injectable } from '@angular/core';
    import { Http } from '@angular/http';
    
    @Injectable({ // The Injectable decorator is required for dependency injection to work
      // providedIn option registers the service with a specific NgModule
      providedIn: 'root',  // This declares the service with the root app (AppModule)
    })
    export class RepoService{
      constructor(private http: Http){
      }

      fetchAll(){
        return this.http.get('https://api.github.com/repositories');
      }
    }

 ### What is the purpose of ngFor directive?


    < li *ngFor="let user of users">
      {{ user }}
    < /li>

 ### What is the purpose of ngIf directive?

    < p *ngIf="user.age > 18">You are not eligible for student pass!< /p>
### What are pipes?

A pipe takes in data as **input and transforms it to a desired output.** 

    import { Component } from '@angular/core';
    
    @Component({
      selector: 'app-birthday',
      template: `<p>Birthday is {{ birthday | date }}</p>`
    })
    export class BirthdayComponent {
      birthday = new Date(1987, 6, 18); // June 18, 1987
    }
### What is HttpClient and its benefits?

Most of the Front-end applications communicate with backend services over HTTP protocol using either XMLHttpRequest interface or the fetch() API. Angular provides a simplified client HTTP API known as  **HttpClient**  which is based on top of XMLHttpRequest interface. This client is avaialble from  `@angular/common/http`  package. You can import in your root module as below,

    import { HttpClientModule } from '@angular/common/http';
### Explain on how to use HttpClient with an example?

Below are the steps need to be followed for the usage of HttpClient.

      Import HttpClient into root module:
    
    import { HttpClientModule } from '@angular/common/http';
    @NgModule({
      imports: [
        BrowserModule,
        // import HttpClientModule after BrowserModule.
        HttpClientModule,
      ],
      ......
      })
     export class AppModule {}

 Inject the HttpClient into the application: Let's create a userProfileService(userprofile.service.ts) as an example.

    import { Injectable } from '@angular/core';
    import { HttpClient } from '@angular/common/http';
    
    const userProfileUrl: string = 'assets/data/profile.json';
    
    @Injectable()
    export class UserProfileService {
      constructor(private http: HttpClient) { }
    
      getUserProfile() {
        return this.http.get(this.userProfileUrl);
      }
    }

Create a component for subscribing service: Let's create a component called UserProfileComponent(userprofile.component.ts) which inject UserProfileService and invokes the service method,

 

       fetchUserProfile() {
          this.userProfileService.getUserProfile()
            .subscribe((data: User) => this.user = {
                id: data['userId'],
                name: data['firstName'],
                city:  data['city']
            });
        }

