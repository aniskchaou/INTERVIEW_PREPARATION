## Angular  Directives

Directives are instructions in the DOM. 

 - **Component Directives:**  Component directives are used in main class.
 - **Structural Directives:**  Structural directives start with a * sign.  **For example, *ngIf and *ngFor.**
 - **Attribute Directives:**  Attribute directives are used to change the look and behavior of the DOM elements.

## For example

**component.ts** 

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
        }
      ];
    }
    }

**component.html** 

    <ul *ngFor="let person of people">
        <li *ngIf="person.age < 30"> 
           {{ person.name }} ({{ person.age }})
        </li>
    </ul>
