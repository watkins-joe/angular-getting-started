file naming convention:

```
app.component.ts
```

1. start with feature name
    - for our root application component, we would call it `app`
2. followed by a dot, with the type of the file
    - in our case, this is a component file
3. followed by another dot, and then the extension
    - since we are using typescript, we'll use `ts` as the extension.

---

when we start building a component, we can begin by writing the class definition

```TSX
export class AppComponent {
    pageTitle: string = 'Acme Product Management';
}
```

then, above that, we can write our decorator. since the AppComponent class is a component, we use the Component decorator.

```TSX
@Component({
    ...
})
```

when writing our decorator, we may notice a red underlined error under `Component`. the error may state that we cannot find the name `Component`.

when writing my decorator function, VSCode automatically imported `Component` from @angular/core without me having to type out the import statement.

in the component metadata, we define a selector for the name of the component when used as a directive in the HTML.

```TSX
@Component({
    selector: 'pm-root';
})
```

a common convention in selector naming is to prefix each selector with something to identify it as part of our application.

for our example, we are using the prefix of `pm` for `product management`.

the selector ends with a name that represents this component.

remember? this was the prefix we used when creating our application with the Angular CLI.

`npm new apm --prefix pm`

then, we define the template.

any valid HTML can be specified in the template. our template begins and ends with backticks (\` \`), not quotation marks.

these backticks are also used in template literal strings from vanilla JavaScript.

```TSX
@Component({
    selector: 'pm-root';
    template: `
    <div><h1>{{pageTitle}}</h1>
        <div>My First Component</div>
    </div>
    `
})
```
