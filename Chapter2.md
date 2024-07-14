# Components

Components are the functions that return UI.
we can change UI functionality like a normal functions.


```javascript

//App.js

//Upper case if possible
function app(){
return <h1>Hello World</h1>
}

export default app;
//you can change its name at the time of importing it because its default.

```

```javascript
import App from "./App.js"

</App>
//Always be in capital case

```


- Whenever we use a functional component, the function simply returns a value that gets displayed where it's used and then it terminates itself.


## Project

### Folder structure

```javascript
my-react-app/
├── node_modules/
├── public/
│   ├── index.html
│   └── ...
├── src/
│   ├── components/
│   │   └── Video.js
│   ├── App.js
│   ├── App.css
│   ├── index.js
│   └── index.css
├── .gitignore
├── package.json
├── package-lock.json
└── README.md

```

1. Index.js

```javascript
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

```

2. App.js

```javascript

import './App.css';
import Video from './components/Video';
//by default file imported file name is .js


//Must return one JSX element. (use div or fragment tag)
function App() {
  return ( // because return same line value
    <div className="App">
        <Video />
    </div>
  );
}

export default App;

```


3. Video.js

```javascript


const Video = () => {
  return (
    <div>Video</div>
  );
}

const Thumb = () => {
  return (
    <div>Thumb</div>
  );
}


export default Video;

//export {Video,Thumb};
//import {Video,Thumb} from "./COmponents/Video
//Not a good way
//One file must have one Component and exported as default

```

3.3 

```javascript
function Video(){
return (
<div>
<img src="http://placeing.com/160/90/any" alt="" />
<div>Master React js</div>
</div>
)
}
```

Note:- Fragment Tag <></> is used to contain our component code and does not create a new block in our web page.





# Writing Markoup with JSX

JSX is a JavaScript object and part of JavaScript. Previously, it was challenging to target an element and write a function in a separate file, making the connection difficult.

Now, with JSX, you can directly write the onClick() function within the <form> element.



## HTML + JS = JSX

```javascript

import React, { useState } from 'react';
import Sidebar from './Sidebar';

const App = () => {
    const [isLoggedIn, setIsLoggedIn] = useState(false);

    // Function to toggle login state for demonstration purposes
    const toggleLogin = () => {
        setIsLoggedIn(!isLoggedIn);
    };

    return (
        <div>
            <button onClick={toggleLogin}>
                {isLoggedIn ? 'Log Out' : 'Log In'}
            </button>
            <Sidebar isLoggedIn={isLoggedIn} />
        </div>
    );
};

export default App;

```

Sidebar.js -- React Component


```javascript

Form(){

onClick(){...}
onSubmit(){...}

<form onSubmit={}>
<input onChange/>
<input onChange/>
</form>
}
```

Form.js -- React Component



With JSX, we can define a component separately and manage its internal functionality within the same component.


JSX support all html tags + other




# Rule to convert HTML to JSX


## Rule 1

A React component must return a single element, acting as a parent object. Avoid creating unnecessary tags.


Solution: Use `<> </>` fragments.

Fragments follow the rule of having one parent component without adding extra elements, preventing CSS styling issues.





## Rule 2

Because JSX is JavaScript, we can't use `class` as an attribute for HTML elements since `class` is a reserved word in JavaScript. Instead, we use `className`



JSX follows camelCase convention for attributes. For example, use `backgroundColor`,`onClick()`.


```javascript

// style={{}}

style={{ backgroundColor: "red" }}

// {} allows us to pass a variable to React, and React ...

```

In JSX, we use double curly braces {{}} for inline styles. For example, `style={{ backgroundColor: "red" }}`. The outer `{}` lets us write JavaScript expressions, and the inner `{}`defines an object. This way, we can pass a variable to React, and React applies the style.


Inline CSS in React takes an object because it aligns with the way JavaScript handles styles, allowing for dynamic and programmatic styling. By using objects, we can easily define styles using JavaScript's camelCase syntax and leverage the full power of JavaScript to compute styles, manage state, and pass variables.

```javascript
const myStyle = {
    backgroundColor: "red",
    color: "white"
};

<div style={myStyle}>Hello, world!</div>

```
This approach provides a more seamless and powerful way to handle styles within components.


How JSX use variable

In JSX, we can use variables directly within our components. We can create variables for anything inside a component and use them in the JSX markup.


```javascript
function Video() {
    // Define variables for use in the component
    let title = "React JS Mastery Course";
    let bg = "dark";

    return (
        <>
            {/* Use the variables within JSX */}
            <div className={bg} style={{ backgroundColor: "red" }}>
                {title}
            </div>
        </>
    );
}

```

This demonstrates how to dynamically use JavaScript variables within JSX for classes, styles, and content.

We can use any attribute as variable.

CSS property act as object because JSX is Javascript
Some time we pass object for style a component


## Rule 3

In React, all elements must be properly closed. While HTML accepts `<img>`, React requires it to be self-closed as `<img />`.

Tip: Use an HTML to JSX converter to help with the syntax.


```html
<!-- Incorrect in React -->
<img>

<!-- Correct in React -->
<img />

```

React enforces this rule to ensure that all components and elements follow the XML-like syntax.


## Rule 4

In React, to associate a `<label>` with a form element using the `for` attribute as in HTML, you should use `htmlFor` instead. Here's the correct way to write it in JSX:


```html

<label htmlFor="name">Label Text</label>

```
In this example, `htmlFor` is used to specify the ID of the form element that this `<label>` is associated with, similar to the for attribute in HTML. This ensures accessibility and proper behavior in React applications.










# Continue cour project

```javascript
function Video() {
  return (
    <div>
      <img
        src="https://graphicsfamily.com/wp-content/uploads/edd/2021/02/Digital-marketing-agency-banner-template-design-2048x1152.jpg"
        alt=""
      />
      <div>React js mastery course</div>
    </div>
  );
}

export default Video;
```


```javascript
import Video from "./Video";
import "./App.css";

function App() {
  return (
    <>
      <h1>Hello World</h1>
      <Video />
      <Video />
    </>
  );
}

export default App;

```


<img src="image/image.png" />




### Both `Video` tag are showing the same content. 

Both <Video> tags currently display identical content. In real-world scenarios, they should be unique. To achieve dynamic content changes based on function interactions, simply modify the function to update the UI accordingly.
This capability allows you to adjust the impact of any function as needed.


For this we have to pass the different content for both the function with `props` . Because one function give different output when we change the prop.


To ensure each <Video> tag displays different content dynamically, you need to pass unique props to each function instance. This approach allows each function to produce distinct outputs based on the prop values you provide.


```javascript

import Video from "./Video";
import "./App.css";

function App() {
  return (
    <>
      <h1>Hello World</h1>
      <Video title="React js" />
      <Video title="Node js" />
    </>
  );
}

export default App;


```


```javascript
function Video(props) {
  return (
    <div>
      <img
        src="https://graphicsfamily.com/wp-content/uploads/edd/2021/02/Digital-marketing-agency-banner-template-design-2048x1152.jpg"
        alt=""
      />
      <div>{props.title} mastery course</div>
    </div>
  );
}

export default Video;
```

<img src="" />






















