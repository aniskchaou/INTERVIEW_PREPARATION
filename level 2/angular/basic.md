## Angular

Angular 7 is completely  _**based on components**_. It consists of several components which forms a tree structure with parent and child components.

## SPA (Single Page Application)
![enter image description here](https://d2v4zi8pl64nxt.cloudfront.net/optimizing-angularjs-single-page-applications-googlebot-crawlers/592e57b84c1b10.48248066.png)
_**rewrites the current page rather than loading entire new pages from a server.**_  That's the reason behind its reactive fast speed.


## Files used in Angular 7 App folder
![enter image description here](https://lh3.googleusercontent.com/proxy/P9rL1Q50wZHb2A8jOyKQgjdX_AhKJ4JeKDQFFQIuweWSougYIb_bmTT1tJ9dx0WLedGomkwSb8IfkNxYwP7U6U5oV8waugrdmByGyfxwD_u8yxvhNZ_17fUoTSiQgLtb8W556uyUWC2FOREIwHEa-VL2SlWN0WGWTGJjvA)
Angular 7 App files which are mainly used in your project are given below:

-   **src folder:**  This is the folder which  **contains the main code files related to your angular application.**
![enter image description here](https://www.eclipse.org/community/eclipse_newsletter/2017/january/images/cli.png)

## Other Important files
![enter image description here](https://helpmecoder.com/wp-content/uploads/2019/05/AngularFolder_Latest.png)
-   **package.json:**  This is npm configuration file. 
-   **package-lock.json :**  This is an auto-generated and modified file
-   **angular.json:**  **It defines the structure of your app and includes any settings associated with your application.**
-   **assets folder:**  This folder is a placeholder for resource files   
-   **index.html:**  This is the entry file
-   **main.ts:**  **This file bootstraps (starts) the AppModule from app.module.ts , and it can be used to define global configurations.**
-   **styles.css:/**  This is a global css file which **is used by the angular application.**
    

## CLI commands

**new**
`ng new MyApplication`  creates a new angular application.

**serve**

`ng serve`  builds the application and starts a web server.

**generate**

`ng generate [name]`  generates the specified schematic

name : component, directive, module, pipe, service

 **test**
`ng test`  running unit tests

**e2e**
`ng e2e`  serves the application and runs end-to-end tests.

**build**
`ng build`  compiles the application into an output directory.

**version**

`ng version` It utputs Angular CLI version.

**add**
`ng add [external library]` It is used to add support for an external library to your project.
## Angular  Architecture
![enter image description here](https://www.ngdevelop.tech/wp-content/uploads/2017/12/Angular_Architecture.png)
1.  **Component:**  These are  **the basic building**  blocks of angular application
2.  **Modules:**  An application is divided into  **logical pieces**  and each piece of code is called as "module" which perform a single task.
3.  **Templates:**  **This represent the views**  of an Angular application.
4.  **Services:**  It is used to create  **components which can be shared across the entire application.**
5.  **Metadata:**  This can be used to add  **more data to an Angular class**
## Angular Lifecycle hooks
![enter image description here](https://digitalcontrol.me/wp-content/uploads/2017/12/lchooks1.png)
