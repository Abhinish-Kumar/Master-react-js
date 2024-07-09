We will cover 30 hooks

# Level 1

Must to Know

1. useState
2. useEffect
3. useContext

### useState()

1. Importing Hooks:

When importing a hook from React, you use destructuring to access the specific hook you need. For example:

```javascript

import { useState } from 'react';

```

2. Usage Restrictions:

- Hooks can only be used inside functional components. They cannot be used in class components because class components have a different way of managing state and lifecycle methods.
- Hooks must be called at the top level of a functional component. This means you cannot call hooks inside loops, conditionals (if statements), or nested functions. They must be used in the same order on every render to ensure consistent behavior.otherwise it will show error.
- Why These Rules Matter:-
- Consistent Order of Hooks: React relies on the order of hooks to match up with their previous renders. Changing the order (e.g., by placing them inside conditions) can lead to bugs.
- Top-Level Calls: Ensuring hooks are called at the top level of your component keeps the logic predictable and avoids issues with state and effect dependencies.
- 


```javascript
import React,{useState} from "react";

function App(){
return (
<button>-</button>
<span>0<span>
<button>+</button>
)
}
```

useState:- is a function that accepts the default value of a state, and it reutn an array of values , the first value is the current state and the second value is the function that updates the current state.


```javascript
import React,{useState} from "react";

function App(){
return (
//const arr=useState(5)
const [counter,setCounter]= useState(5)

function decrementCount(){
setCounter(count -1)
setCounter(count -1)
//only decreases by one
//they are over riding each other 
}

//good way to update the state

function decrementCount(){
setCounter(prevCount => prevCount - 1)
//it takes the previous updated state
}

function incrementCount(){
setCounter(prevCount => prevCount + 1)
//it takes the previous updated state
}

<button onClick={decrementCount}>-</button>
<span>{count}<span>
<button onClick={incrementCount}>+</button>
)
}
```

If state updates react re-render the component with the new value od state. When you update the state your component re-renders.




























