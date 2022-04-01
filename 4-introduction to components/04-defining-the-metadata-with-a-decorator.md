a class becomes an Angular component when we give it component metadata.

Angular needs this metadata to understand how to instantiate the component, construct the view, and how to interact with the component.

We define a component's metadata with an Angular Component function.

In TypeScript, we attach that function to the class as a decorator.

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

Decorator
* A function that adds metadata to a class, its members, or its method arguments.

a decorator is a javascript language feature that is implemented in typescript.

the scope of the decorator is limited to the feature that it decorates.

a decorator is **always** prefixed with an `@` symbol.

Angular has several built-in decorators we use to provide information to Angular.
* one example is `@Component`

we apply a decorator by positioning it immediately in front of the feature we are decorating.

in the example below, when we are decorating a class, we define the decorator immediately above the class signature.

```TSX
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

notice that there is no semi colon following the closing parenthesis of the decorator function. this is similar to **attributes** used in other programming languages.

we use the `@Component` decorator to identify the class as a component.

because the decorator is a function, we always add parenthesis. we pass an object to the function as indicated by the curly braces.

the object argument we pass in has many properties
* selector
    - if we plan on referencing the component in any HTML, we specify a **selector**.
    - the selector defines the components directive name.
        - a directive is simply a custom HTML tag.
            - whenever this directive is used in HTML, Angular renders this component's template.
* template
    - a component should **always** have a template. `{{data}}` indicate **data-binding**
        - we bind the h1 element value to the `pageTitle` property of the class
            - when the HTML is rendered, the h1 element displays `Acme Product Management`

there is one more key task before our component is complete: importing.