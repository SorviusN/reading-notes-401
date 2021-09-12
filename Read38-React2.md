# Reading Notes 38 - React 2

### React - A library used for developing web applications in Javascript.

Functional vs  OOP Components.

Components are the bulding blocks of React. If you're coming from an Angular background, components are similar to Directives. They are a collection of HTML, CSS and JS. Generally, these components are built from something named "JSX" which eventually gets compiled into normal Javascript for the web.

A basic JSX File would look something like this. Notice that this is a class and not a functional component.

``` js
import React from 'react'
import ReactDOM from 'react-dom'

class HelloWorld extends React.Component {
   render() {
     return (
       <div>Hello World!</div>
     )
   }
}
```

A functional component would look something like this:

``` js
import React from 'react'
import ReactDOM from 'react-dom'

function Head() {
    return (
        <div>Hello World!</div>
    )
}
```

important articles: https://reactjs.org/docs/lists-and-keys.html
https://reactjs.org/docs/forms.html
https://reactjs.org/docs/composition-vs-inheritance.html
https://reactjs.org/docs/conditional-rendering.html
https://reactjs.org/docs/lifting-state-up.html