# useRef()

1. The useRef Hook persist its value between rendering/ There is no effect on this value of rendering, it act as global variable.
2. IT can be used to store a mutable value thats value can be changed without cause of rerendering/ it is similar to the useState , it changes or updates the value , but on changing th evalue it does not rerenders the component.
3. Its second use is to access the dom element easily.

Problem :- every time we click the buttion it always show 100 
```javascript
import "./styles.css";
import {useRef, useState} from "react";

export default function App() {
   let x=100;
  let [count,setCount]=useState(0);
  function increment(){
    x=x+100;
setCount(count=count+1)
  }
  return (
    <div className="App">
      <h2>{x}</h2>
      <h1>{count}</h1>
      <button onClick={increment}>Increment</button>
    </div>
   
  );
}

```


Solution :- useRef() to define a global value.

```javascript
import "./styles.css";
import {useRef, useState} from "react";

export default function App() {
  let x=useRef(100);
  // let x=100;
  let [count,setCount]=useState(0);
  function increment(){
    x.current=x.current+100;
setCount(count=count+1)
  }
  return (
    <div className="App">
      <h2>{x.current}</h2>
      <h1>{count}</h1>
      <button onClick={increment}>Increment</button>
    </div>
   
  );
}

```











