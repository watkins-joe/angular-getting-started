what is a component?

* component
    - has a template
        - view layout
        - created with HTML
        - includes binding and directives
    - has a class
        - contains properties, which are the data
        - contains methods, which is the logic
        - code supporting the view
        - created with TypeScript
    - has metadata
        - extra data for Angular
        - defined with a decorator
            - decorator is a function that adds metadata to a class, its members, or its method arguments

a component is a view, defined in a template, its associated code defined with a class, and metadata defined with a decorator

example of a Component:

`app.component.ts`

---

```TSX
import { Component } from '@angular/core`;

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

---

our Class:

```TSX
export class AppComponent {
    pageTitle: string = 'Acme Product Management';    
}
```

* defines our properties and methods needed by our view.

our Component Decorator:

```TSX
@Component({
    selector: 'pm-root',
    template: `
    <div><h1>{{pageTitle}}</h1>
        <div>My First Component</div>
    </div>
    `
})
```

* defines our metadata. the metadata includes the template that lays out the view managed by this component.

our import statements:

```TSX
import { Component } from '@angular/core`;
```

* where we import the members that we need in this component.