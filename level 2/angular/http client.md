## Http Client
**app.component.ts**.


    export class AppComponent {
       constructor(private http: HttpClient) { }
       httpdata;
       name;
       searchparam = 2;
       ngOnInit() {
          this.http.get("http://jsonplaceholder.typicode.com/users?id="+this.searchparam)
          .subscribe((data) => this.displaydata(data));     
       }
       
       displaydata(data) {this.httpdata = data;}
    }
**app.component.html** 

    <ul *ngFor = "let data of httpdata">
       <li>Name : {{data.name}} Address: {{data.address.city}}</li>
    </ul>
