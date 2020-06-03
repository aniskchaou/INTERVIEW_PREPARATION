## Angular Reactive Forms

**AppComponent.ts**
 

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

**AppComponent.html**

    <input formControlName="name" />
    <select formControlName="sex">
      <option *ngFor="let s of sex" [value]="s">{{s}}</option>
    </select>  
    <button type="submit" [disabled]="personForm.pristine">Save</button>

## Template-driven Forms
**Person.ts**

    export class Person {
        constructor(
        public id: number,
        public name: string,
        public sex: string,
        ) { }
        }

**AppComponent.ts**

     export class AppComponent {
    
      sex = ['','Male', 'Female'];
      
      model = new Person(1, '', this.sex[0]);
        submitted = false;
       
        onSubmit() { 
       this.submitted = true; 
       console.log(this.model);
       }
    
       
    }

**AppComponent.html**

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
        <option *ngFor="let s of sex" [value]="s">{{s}}  </option>
      </select>
      
      <button type="button"  (click)="onSubmit()">New Hero</button>
    </div>
