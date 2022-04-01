creating the component class

our Class:

```TSX
export class AppComponent {
    pageTitle: string = 'Acme Product Management';    
}
```

* defines our properties and methods needed by our view.

a class is a construct that allows us to reate a type, with properties that define the data elements and methods that provide functionality

a common Angular convention is to name each component class with the feature name, and then the word `component` as the suffix.

example:

`AppComponent`

`<featureName>Component`

also by convention, the root component for an application is called `AppComponent`

the export keyword exports this class to make it usable by other components in the application.

in our example, we only have one property and no methods.

a property defines a data element associated with the class.

in our example, we are assigning a default value to the pageTitle string property. this is optional.

methods are normally defined in the class body after the properties.

method names are often verbs that describe the action the method performs.