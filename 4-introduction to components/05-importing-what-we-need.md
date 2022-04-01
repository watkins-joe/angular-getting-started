before we can use a functino or class, we need to define where to find it

we use an `import` statement for that, implemented from ES2015, or ES6.

similar to the `import` statement in Java or the C# `using` statement

the import statement allows us to tuse exported members from:
- other files in our application
- Angular framework
- External JS libraries

we use the Component decorator function from Angular to define our class as a component

we need to tell angular where to find this Component function, so we add an import statement to do so:

```TS
import { Component } from '@angular/core`
```

we use the import keyword, the member name, and then the path to the library or file containing that member.
- in this case, that would be the angular core library

if we were importing multiple items from the same library, we would import them in the same list, each separated by a comma

```TS
import { Component, Component2, Component3 } from '@angular/core`
```

