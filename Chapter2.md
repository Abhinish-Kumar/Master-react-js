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




















