## routerConfig.ts

    export const appRoutes: Routes = [
      { path: 'home',
        component: HomeComponent
      },
      {
        path: 'about',
        component: AboutComponent
      },
      { path: 'dashboard',
        component: DashboardComponent
      }
    ];

## app.module.ts

 

       import { appRoutes } from './routerConfig';
        
        @NgModule({
          declarations: [
            AppComponent,
            HomeComponent,
            AboutComponent,
            DashboardComponent
          ],
          imports: [
            BrowserModule, RouterModule.forRoot(appRoutes)
          ],
          providers: [],
          bootstrap: [AppComponent]
        })
        export class AppModule { }

## app.component.ts

    @Component({
      selector: 'app-root',
      templateUrl: './app.component.html',
      styleUrls: ['./app.component.css']
    })
    export class AppComponent {
      title = 'Angular Router Tutorial';
    }

## app.component.html

    <div style="text-align:center">
      <h1>
        Welcome to {{title}}!!
      </h1>
      <nav>
        <a routerLink="home" routerLinkActive="active">Home</a>
        <a routerLink="about">About</a>
        <a routerLink="dashboard">Dashboard</a>
      </nav>
      <router-outlet></router-outlet>
    </div>
