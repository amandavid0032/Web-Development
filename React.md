## 📔 ES5
---
## 📘 Developer Responsibility

---
## 📘 Javascript
**What is React**
React is a JavaScript library that allows developers to build user interfaces (UIs) for web and mobile applications

React is primarily used to build web applications, but it can also be used to create mobile and desktop apps, images, PDFs, and more

---
## 📘  Props and PropTypes in React 
In React, props (short for properties) are a way to pass data from a parent component to a child component. They enable you to make components dynamic and reusable. 
```react
import './App.css';
import Navbar from './components/Navbar';

function App() {

  return (
    <>
 <Navbar title="ReactLearning"/>
  </>
  );
}

export default App;

```

```react
import React from 'react'
import PropTypes from 'prop-types'

export default function Navbar(props) {
  return (
    <nav className="navbar navbar-expand-lg bg-body-tertiary">
    <div className="container-fluid">
      <a className="navbar-brand" href="/">{props.title}</a>
// many more code
</div>
    </div>
  </nav>
  )
}
 
Navbar.propTypes = {
  title: PropTypes.string.isRequired
}
```
**PropTypes**  In this it only accpet String type this is call propTypes
```react

Navbar.propTypes = {
  title: PropTypes.string.isRequired
}


Navbar.defaultProps = {
  title: 'My Website'
}
```
