bootstrapping - "self-starting process that loads and goes"

need to tell angular to load our component thru a process called 'bootstrapping'

how to bootstrap our app component
1. set up the index.html file to host our application
2. define our root Angular module to bootstrap our root component

client side web apps work like this:

1. user accesses a specific URL
2. the server associated with the URL is located and sends a request
3. the server responds by sending its default webpage, index.html
4. browser receives and processes the index.html file
5. for an angular app, the index.html file contains script tags referencing the application files that were transpiled and bundled into several JS files
    - these app files are then downloaded to and processed by the browser
        - then, the application's main page appears
single page application (SPA)

- index.html contains the main page for the application
- this is often the only Web page of the application
- hence an Angular application is often called a SPA

we insert bits of HTML into the one HTML page defined in index.html

hosting the application

`app.component.ts`

```TSX
import { Component } from '@angular/core';

@Component({
    selector: 'pm-root',
    template: `
    <div><h1>{{pageTitle}}</h1>
        <div>My First Component</div>
    </div>
    `
})

export class AppComponent {
    pageTitle: string = 'Acme Product Management';
}
```

- selector
    - the name of the component when we use it as a **directive** in HTML
- template
    - defines the HTML that we want to display

`index.html`

```HTML
<body>
    <pm-root></pm-root>
</body>
```

so, in our index.html, we simply add the selector where we want our template to be displayed, like we would with any other default HTML element, like

```HTML
<p></p>

<!-- or -->

<div></div>
```

in the template, we call this a **directive**

- directive
    - a custom element

as soon as the loading is completed, the HTML defined in the component template is inserted between the selector element tags and appears on the page

`app.component.ts`

```TSX
import { Component } from '@angular/core';

@Component({
    selector: 'pm-root',
    template: `
    <div><h1>{{pageTitle}}</h1>
        <div>My First Component</div>
    </div>
    `
})

export class AppComponent {
    pageTitle: string = 'Acme Product Management';
}
```

`index.html` **before** finished loading

```HTML
<body>
    <pm-root></pm-root>
</body>
```

`index.html` **after** finished loading

```HTML
<body>
    <div><h1>Acme Product Management</h1>
        <div>My First Component</div>
    </div>
</body>
```

---

how does the Angular compiler know about this custom HTML element (in our case, `pm-root`)?

answer: it looks in an Angular module

- Angular modules help us organize our application into cohesive blocks of functionality
    - also provides boundaries in our application
    - also provides a template resolution environment
        - when the Angular compiler sees a directive in a template, it looks to the Angular module for the definition
            - we declare the AppComponent in an Angular module so the compiler can find it
                - we also use the module to bootstrap our startup component, which is our AppComponent

- we want our application to work correctly in the browser, so we add Angular's BrowserModule to our Angular modules imports

- defining the Angular Module

here is our application's root Angular module:

`app.module.ts`

```TSX
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';

@NgModule({
    imports: [ BrowserModule ],
    declarations: [ AppComponent ],
    bootstrap: [ AppComponent ]
})
export class AppModule { }
```

- we define an Angular module using a class
    - we identify the class as an Angular module by attaching the NgModule decorator function
        - inside the decorator, we pass in metadata defining the details of the Angular module
        - for the NgModule decorator, the properties are **arrays**
            - in the `declarations` array, we define which of our components belong to this module
                - by convention, our root application component, `AppComponent`, belongs to the applications root Angular module, `AppModule`
                    - we can add other components here as well.
            - in the `imports` array, we define the **external** modules that we want to have available to all of the components that belong to this Angular module
                - external modules could be modules provided by Angular, a third-party, or our own Angular modules
                    - in our example, we import `BrowserModule`, which every browser application must import
                        - BrowserModule registers important application service providers, such as error handling
            - the `bootstrap` array defines the startup component of the application, which is our `AppComponent`
                - the startup component should contain the selector we use in the `index.html` file, which in our case, it does.