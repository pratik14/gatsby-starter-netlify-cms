---
templateKey: blog-post
title: Functional Vs Class Components
date: 2018-12-29T13:04:10.000Z
description: >-
  Why bother writing about functional component if class component has more
  powers. 
tags:
  - components
  - hooks
---
![flavor wheel](/img/flavor_wheel.jpg)

There are two ways to define React component

1. Functional
2. Class

## Functional Component

“Functional components” are simple Javascript functions which accepts props and returns JSX code

```javascript

function Welcome(props) {
    return <h1>Hello, {props.name}</h1>;
}
```

## Class Component

Whereas “Class Component” are ES6 way to create React Components 

```javascript
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

All class components 

1. Have to extend from React.Component
2. have “render” method which returns JX code
3. Has Additional capability such as internal state and lifecycle hooks

The differences above may seem subtle at first glance, but cutting the noise is a big win.

## Advantage of Functional Component

_Reusable Code_\
 A functional stateless component is merely a factory function used to create a React component

_No this Keyword As_ \
You can see above, the stateless component is just a function. Thus, all the annoying and confusing quirks with Javascript’s this keyword are avoided. The entire component becomes easier to understand without the this keyword. Just compare the click handler in each approach:

```javascript
  onClick={this.sayHi.bind(this)}>Say Hi</a>
  onClick={sayHi}>Say Hi</a>
```

Note that the bind keyword isn’t necessary for the stateless component. Dumping classes eliminates the need for calling bind to pass the this context around. Given how confusing JavaScript’s this keyword is to many developers, avoiding it is a nice win.

Easy to Test Since it’s a pure function, your assertions are very straightforward: Given these values for props, I expect it to return this markup. So for the example HelloWorld component, I can assert that when the render function is called with the value of ‘Cory’ for props.name, it returns a div with ‘Hi Cory’ inside.

With React’s stateless functional components, each component can be easily tested in isolation. No mocking, state manipulation, special libraries, or tricky test harnesses are needed.

Equipped with the right number of tests, the use of functional components can help bring peace of mind to developers by ensuring that any scenario that has been tested will not have an unintended result in the application.

Easy to Understand

As we’ve just seen, when you see a stateless functional component, you know it’s simply a function that takes props and spits out HTML. Even if it contains a lot of markup and nested functions inside the render, it’s conceptually simple. It’s a pure function. This leads to the next big win…

Performance

Familiar of OO Developer
