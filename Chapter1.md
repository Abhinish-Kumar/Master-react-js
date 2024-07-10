## Why React?

- For SPAs: React is ideal for creating highly interactive and dynamic user interfaces with a heavy reliance on JavaScript.
- For MPAs: React can be used selectively to improve specific components or sections, allowing for incremental enhancement and interoperability with existing technologies.

## What is React?

- It is a UI library focused on creating components.
- It uses a component-based approach for elements like the sidebar, header, and footer.

## Why Component?

- Simple structure :- It has a simple and easy-to-understand structure.
- Easy to reuse and update: create once, change once

<img src="./tree.png" />

- In React, any component is essentially a combination of HTML, CSS, and JavaScript.
-  React combines the HTML-like syntax and JavaScript to create JSX, a syntax extension that allows you to write HTML elements directly within JavaScript code.
- JSX makes it easier to create and manage the UI by allowing you to write markup directly in your JavaScript files.


## Installation

1. CRA :- Its a tool chain , help to install react easily for using this tool we need node js and command that can run with node .
2. Node.js provides the runtime environment necessary for React development, and CLI tools facilitate the installation, management, and execution of React applications and related dependencies. This combination forms the foundation for building modern, scalable web applications with React.

```javascript
>>> npx create-react-app my-app
```
npx: A Node.js package runner used to execute packages from the npm registry without needing to install them globally.
create-react-app: The toolchain for setting up a new React application.

This command sets up a new React project named my-app and automatically installs a development server and other necessary dependencies. React itself is based on Node.js, so the installation includes Node.js-related tools.




Note:- vite, parcel are other tool chain to install react.

Note:- Install (React-developer-tool) in chrome , and set it and when ever you visit any react site it will shine.

<img src="./devTool1.png" />

<img src="./devTool2.png" />

<img src="./devTool3.png" />




```javascript
>>> npm start
```


To start your React app using CRA, you can access it via:

1. Local Server:

```javascript

http://localhost:3000

```

2. On Your Network:


```javascript

http://192.128.1.3:3000

```

These URLs allow you to access your React application locally and on your network, respectively, after starting the development server with "npm start" or "yarn start".



## Index.html 


In a single-page application, this is the singular page where our React application will be attached.

## Error

Whenever you delete a file, React will show an error because it can't find the reference to that file anymore.

```javascript
>>> CTRL + Click to file 
```


## NPM start

"start" is a script defined in package.json that specifies the command to start your application.
It's commonly used for starting development servers, running build processes, or initiating any necessary tasks to launch your application.

```javascript
{
  "name": "my-react-app",
  "version": "1.0.0",
  "private": true,
  "dependencies": {
    "react": "^17.0.2",
    "react-dom": "^17.0.2",
    "react-scripts": "4.0.3"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}

```


```javascript

  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test"
  }

```
With "npm" you can run any script.

```javascript
>>> npm run start
Its a special case
>>> npm start


>>> npm run build
>>> npm run test
```



## Folder structure of react app

```javascript
my-react-app/
├── node_modules/       # Installed npm packages (not shown in detail)
├── public/             # Static files
│   ├── favicon.ico     # Favicon icon
│   ├── index.html      # Main HTML file
│   └── ...
├── src/                # Source files
│   ├── assets/         # Images, fonts, and other assets
│   ├── components/     # React components
│   │   ├── Header.js   # Example component
│   │   ├── Sidebar.js  # Example component
│   │   └── ...
│   ├── App.js          # Main component
│   ├── index.js        # Entry point for React rendering
│   └── ...
├── .gitignore          # Git ignore file
├── package.json        # Project configuration and dependencies
├── README.md           # Project documentation
└── ...

```

## index.html

```html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>React App</title>
</head>
<body>
  <div id="root"></div>
</body>
</html>

```
This <div> serves as the mounting point for the React application. React will inject and manage its components within this element.
It will work as a root node in a vertual dom tree in react or first and top component.



## Index.js

It serves as the entry point for rendering the React components into the DOM.

```Javascript
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';


const root = ReactDOM.createRoot(document.getElementById('root');
//create a root node of tree

root.render(<App/>);
//render our app component in the root node


```

Explanation:- "root" is the entry point of index.js , ReactDOM.createRoot methd takes an html element and make it a root node. 
We are rendering the <App/> component in the root node. 

Note:- We created an HTML node and designated it as the root node. Then, we used the render method to attach the App component to this root node.

Note:- Onle html file is required always to render the react appliaction. This act as a single page where we render different components with javascript dynamically without page reload.


## Flow

1. npm start
2. npm start will run index.js file
3. In index.js file "react script" loaded and then "ReactDom" loads.
4. With the help of react dom we will create a root node by capturing a node from index.html file.
5. And at last <App/> component will be rendered.


## What is App component

Its a function  used to create components.

We can use it as a html element.

It replaces the name of react Component to the actual value of the component that we define in the function body or component body.

```javascript
import React from 'react';

function App() {
  return (
    <div>
      <h1>Hello, React!</h1>
      <p>This is the App component.</p>
      {/* Other components or JSX elements */}
    </div>
  );
}

export default App;

```

Component is nothing but a function that returns UI



## JSX

Accept any HTML tag and create new tags that represent component , It combines the HTML and Javascript.

```javascript
import React from 'react';

function App() {
  return (
    <div>
      <h1>Hello, React!</h1> //JSX
      <p>This is the App component.</p>
      {/* Other components or JSX elements */}
   {/* write any valid javascript expression*/ }
    </div>
  );
}

export default App;
```

{} is renders the thing that is return by a function. 

1. Used to write any attribute dynmically.


```javascript
import React from 'react';

function App() {
let name="header";
  return (
    <div>
      <h1 className={name}>Hello, React!</h1>
{console.log("hello")}
    </div>
  );
}

export default App;
```

2. Atleast every thing is modify able.
3. No HTML is there
4. {console.log("hello")} it will print the ans 2 time because of strict mode.








































