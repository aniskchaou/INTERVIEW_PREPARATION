## Input/Output
**parent.component.ts**

    @Component({
      selector: 'app-parent',
      templateUrl: './parent.component.html',
      styleUrls: ['./parent.component.css']
    })
    export class ParentComponent implements OnInit {
    
      public childData:string
      constructor() { }
    
      ngOnInit() {
      }
    
    }
**parent.component.html**

    Parent component <input  type="text"  #ptext  (keyup)="0"  /><br>
    
    value of child component : <b> {{childData}}</b><br>
    
    <app-child  (childEvent)="childData=$event"  [parentData]="ptext.value"></app-child>
**child.component.ts**

    @Component({
      selector: 'app-child',
      templateUrl: './child.component.html',
      styleUrls: ['./child.component.css'],
      inputs:['parentData'],
      outputs:['childEvent']
    })
    export class ChildComponent implements OnInit {
    
      public parentData:string
      public childEvent=new EventEmitter<string>()
      constructor() { }
    
      ngOnInit() {
      }
    
      onChange(value)
      {
        this.childEvent.emit(value);
      }
    }
**child.component.html**

    Child component <input  type="text"  #childText  (keyup)="onChange(childText.value)"  /><br>
    
    value of parent component :<b> {{parentData}}</b><br>
