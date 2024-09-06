# useEffect()


```javascript
useEffect(() => {
  // Code to perform the side effect

  return () => {
    // Cleanup code (optional)
  };
}, [dependencies]);

```

Every time we re-render our component useEffect function will run

First parameter it takes a function to run and sencond a dependency array , in this array we pass dependency and when ever the value of dependency changes it will run the function


Start


```javascript

import "./styles.css";
import {useState} from "react";

export default function App() {
  let [resourseType,setResourse] = useState("posts");
  return (
    <div className="App">
     <button onClick={()=>setResourse("posts")}>Posts</button>
     <button onClick={()=>setResourse("users")}>Users</button>
     <button onClick={()=>setResourse("comments")}>Comments</button>
     <h1>{resourseType}</h1>
    </div>
  );
}

```
Call different api on resourse change. this is also called as sideEffect.

For this we have a special hook useEffect 


```javascript

import "./styles.css";
import {useState,useEffect} from "react";

export default function App() {
  let [resourseType,setResourse] = useState("posts");
  useEffect(()=>{
    console.log("efe");
  })
  return (
    <div className="App">
     <button onClick={()=>setResourse("posts")}>Posts</button>
     <button onClick={()=>setResourse("users")}>Users</button>
     <button onClick={()=>setResourse("comments")}>Comments</button>
     <h1>{resourseType}</h1>
    </div>
  );
}

```

Run the useEffect block when ever you re-render the coponent.
But we want specific trigers that trigger useEffect. 
Thats why we need dependency array.

```javascript

import "./styles.css";
import {useState,useEffect} from "react";

export default function App() {
  let [resourseType,setResourse] = useState("posts");
  useEffect(()=>{
    console.log("efe");
  },[resourseType])
  return (
    <div className="App">
     <button onClick={()=>setResourse("posts")}>Posts</button>
     <button onClick={()=>setResourse("users")}>Users</button>
     <button onClick={()=>setResourse("comments")}>Comments</button>
     <h1>{resourseType}</h1>
    </div>
  );
}

```



```javascript

import "./styles.css";
import {useState,useEffect} from "react";

export default function App() {
  let [resourseType,setResourse] = useState("posts");
  useEffect(()=>{
    console.log("efe");
    fetch(`https://jsonplaceholder.typicode.com/${resourseType}`)
      .then(response => response.json())
      .then(json => console.log(json))
  },[resourseType]);
  return (
    <div className="App">
     <button onClick={()=>setResourse("posts")}>Posts</button>
     <button onClick={()=>setResourse("users")}>Users</button>
     <button onClick={()=>setResourse("comments")}>Comments</button>
     <h1>{resourseType}</h1>
    </div>
  );
}

```

Different button call different buton well. 


```javascript

import "./styles.css";
import {useState,useEffect} from "react";

export default function App() {
  let [resourseType,setResourse] = useState("posts");
  let [item,setItem]=useState([]);
  useEffect(()=>{
    console.log("efe");
    fetch(`https://jsonplaceholder.typicode.com/${resourseType}`)
      .then(response => response.json())
      .then(json => setItem(json));
  },[resourseType]);
  return (
    <div className="App">
     <button onClick={()=>setResourse("posts")}>Posts</button>
     <button onClick={()=>setResourse("users")}>Users</button>
     <button onClick={()=>setResourse("comments")}>Comments</button>
     <h1>{resourseType}</h1>
    {item.map((obj)=>{
      return <p>{JSON.stringify(item)}</p>
    })}
    </div>
  );
}
```
















































































