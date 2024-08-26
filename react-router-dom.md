## React Router v6
React Router v6 is a tool for React apps that helps organize different parts of the app into different URLs, making it easier for users to navigate around.

```javascript

import { BrowserRouter as Router, Routes, Route, Link } from 'react-router-dom';

function App() {
  return (
    <Router>
      <nav>
        <Link to="/">Home</Link>
        <Link to="/about">About</Link>
        <Link to="/contact">Contact</Link>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
      </Routes>
    </Router>
  );
}

function Home() {
  return <h2>Home</h2>;
}

function About() {
  return <h2>About</h2>;
}

function Contact() {
  return <h2>Contact</h2>;
}

export default App;

```

Explanation:- react-router-dom library provide some methods that helps us to do the routing, 
1. BrowserRouter :- this is the first component of the library that we import in our code to work with routing here we are using BrowserRouter as Router.It wraps your entire application and enables the routing functionality.It's typically used at the root level of your React application.BrowserRouter provides the routing context to the rest of your application, allowing components like Link, Route, and Switch to function properly and manage navigation within the app.BrowserRouter is a component provided by React Router that uses the HTML5 history API to keep your UI in sync with the URL.
2. Routes:- Routes is a component provided by React Router that serves as a container for defining all the routes in your application.Within the Routes component, you define individual Route components, each representing a specific path in your application. These Route components map a URL path to a corresponding React component that should be rendered when the URL matches that path.By organizing your routes within the Routes component, you can create a clear and structured way to manage navigation and handle different views or components based on the URL.

```javascript

<Routes>//this one
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
        <Route path="/contact" element={<Contact />} />
</Routes>//this one

```
3. Route:- Routes define the container where group of route are present. Inside Routes component we have Route. A single route has two things a path and a component and its work is to connect that component to that path. And when the url matches that path react render the coresponding component.

```javascript

<Route path="/about" element={<About />} />

```
In this example, when the URL matches "/about", the About component will be rendered.
But here one thing is missing dynamic routing to change the url of the link to render new component.

4. Link:- Link is a component provided by React Router that creates a clickable link in your application, allowing users to navigate to different pages or views within the app without triggering a full page reload.The Link component renders an <a> element with an href attribute set to the specified to prop value. When a user clicks on the Link, React Router intercepts the click event and updates the URL using client-side routing, rendering the appropriate component associated with the clicked Link.

```javascript

<Link to="/about">About</Link>

```

In this example, clicking on the "About" link will navigate the user to the "/about" URL path, rendering the corresponding component defined by a Route with path="/about".

This is the basic of react-router-dom.




## Nested Routing
Nested routing in React Router lets you create routes within components, useful for organizing different sections of a user interface with their own navigation paths.






# Router Hook for dynamic routing


```javascript
import "./App.css";
import { Routes, Route, Link, useParams } from "react-router-dom";
let users = [
  {
    id: 1,
    name: "Abhinish",
    desc: "lorem this is a story of thirsty corow ",
    study: "Ct university",
  },
  {
    id: 2,
    name: "Vicky",
    desc: "lorem this is a story of thirsty corow ",
    study: "Ct university",
  },
  {
    id: 3,
    name: "Aaditya",
    desc: "lorem this is a story of thirsty corow ",
    study: "Ct university",
  },
];

function Card({ name, study, desc }) {
  return (
    <>
      <div className="card">
        <div id="img"></div>
        <h4>Name:- {name}</h4>
        <h4>Collage:- {study}</h4>
        <p>{desc}</p>
      </div>
    </>
  );
}
function Product() {
  let { id } = useParams();
  let user = users.filter((obj) => +obj.id === +id);
  return (
    <div id="product">
      <h1>{user[0].name}</h1>
      <h1>{user[0].study}</h1>
      <p>{user[0].desc}</p>
    </div>
  );
}

function Contact() {
  return (
    <div className="form">
      <h1>This is a contact page</h1>
      <form>
        <input type="text" placeholder="Enter your name"></input>
        <input type="text" placeholder="Enter your age"></input>
        <input type="text" placeholder="Enter your gmail"></input>
        <button>Submit</button>
      </form>
    </div>
  );
}
function Home() {
  return (
    <div className="home">
      {users.map((u) => (
        // <Route path="/home/:name" Component={Card} />
        <>
          <Link to={`/home/${u.id}`}>
            <Card name={u.name} desc={u.desc} study={u.study} />
          </Link>
        </>
      ))}
    </div>
  );
}
function App() {
  return (
    <>
      <header>
        <ul>
          <Link to="/home">Home</Link>
          <Link to="/contact">Contact</Link>
        </ul>
      </header>
      <div id="main">
        <Routes>
          <Route path="/home" Component={Home} />
          <Route path="/contact" Component={Contact} />
          <Route path="/home/:id" Component={Product} />
        </Routes>
      </div>
    </>
  );
}

export default App;

```









































