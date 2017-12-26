# AngularBootstrap4 - A angular 5 and bootstrap 4 Example

Reference: https://medium.com/codingthesmartway-com-blog/building-an-angular-5-project-with-bootstrap-4-and-firebase-4504ff7717c1

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 1.6.2.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `-prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

## Initiate the project

npm install -g @angular/cli@latest

ng new project-name --skip-install

cd project-name

npm install

## Adding Bootstrap 4

npm install --save bootstrap@next

We need to add @next to the package name because at the time of writing this post Bootstrap 4 is still in beta. The @next addition makes sure that version 4 of Bootstrap is installed, not version 3.

The NPM command installs Bootstrap 4 into the folder node_modules/bootstrap and at the same time makes sure that the dependency is added into the package.json file.

Change styles in .angular-cli.json by
        "styles": [
            "styles.css",
            "../node_modules/bootstrap/dist/css/bootstrap.css"
        ],

### BootStrap Starter Template        

To add a Bootstrap user interface to our sample application we’ll make use of the Bootstrap Starter Template which is available at https://getbootstrap.com/docs/4.0/examples/: To setup a basic user interface with Bootstrap elements we’re going to use code from the Bootstrap Starter Template which can be found on the Examples page:
<image here>
Clicking on the link Starter template opens up the starter template website in a new browser window. To access the HTML markup code of the starter template just open the browser’s source code view.

From the source code view we can copy and paste the needed code parts into our application. First let’s copy the following code from the <body>-section to the template code in app.component.html:

<div class="container">
    <div class="starter-template">
        <h1>Bootstrap starter template</h1>
        <p class="lead">Use this document as a way to quickly start any new project.<br> All you get is this text and a mostly barebones HTML document.</p>
    </div>
</div>
Furthermore we’d like to include the navigation bar from the starter template as well. We do that by first adding a new component to out application by using Angular CLI again:

$ ng g component app-navbar

This command creates a new folder src/app/app-navbar/. Within that folder you’ll find the following four files:

app-navbar.component.html
app-navbar.component.ts
app-navbar.component.css
The component’s template code can be found in file app-navbar.component.html. Delete the default markup code from that file and copy and paste the following code excerpt from the Bootstrap starter template:

<nav class="navbar navbar-expand-md navbar-dark bg-dark fixed-top">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarsExampleDefault" aria-controls="navbarsExampleDefault" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarsExampleDefault">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active">
          <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled" href="#">Disabled</a>
        </li>
        <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="http://example.com" id="dropdown01" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Dropdown</a>
          <div class="dropdown-menu" aria-labelledby="dropdown01">
            <a class="dropdown-item" href="#">Action</a>
            <a class="dropdown-item" href="#">Another action</a>
            <a class="dropdown-item" href="#">Something else here</a>
          </div>
        </li>
      </ul>
      <form class="form-inline my-2 my-lg-0">
        <input class="form-control mr-sm-2" type="text" placeholder="Search" aria-label="Search">
        <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
      </form>
    </div>
  </nav>
Next, let’s open app-navbar.component.ts and adapt the string value which is assigned to the selector property of the @Component directive from app-app-navbar to app-navbar:

@Component({
  selector: 'app-navbar',
  templateUrl: 'app-navbar.component.html',
  styles: []
})
Now add the <app-navbar> element to the template code of AppComponent:

<app-navbar></app-navbar> 
<div class="container">
    <div class="starter-template">
        <h1>Bootstrap starter template</h1>
        <p class="lead">Use this document as a way to quickly start any new project.<br> All you get is this text and a mostly barebones HTML document.</p>
    </div>
</div>
Finally some CSS code needs to be added to styles.css

body {
   padding-top: 80px; 
}
.starter-template {
    padding: 3rem 1.5rem;
    text-align: center;
}
The result of the application in the browser should now comply with the Bootstrap starter template’ output:
