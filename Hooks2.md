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


3. Basic Component Setup:

```javascript
function App() {
    return (
        <button>-</button>
        <span>0</span>
        <button>+</button>
    );
}

```


4. Explanation of "useState":
useState is a function that takes an initial state value as an argument and returns an array with two elements:

a. The current state value.
b. A function to update the state.

5. Updating State Incorrectly:

```Javascript

function decrementCount() {
    setCounter(counter - 1);
    setCounter(counter - 1);
}

```

This code tries to decrement the counter twice but only decreases it by one because the updates are not batched correctly and the state updates override each other.

6. Updating State Correctly:

```javascript

function decrementCount() {
    setCounter(prevCount => prevCount - 1);
}

function incrementCount() {
    setCounter(prevCount => prevCount + 1);
}

```

Using the previous state value (prevCount), the state is updated correctly. This ensures that each update is based on the latest state value, avoiding conflicts.

7. Component Rendering with Updated State

```javascript
function App() {
    const [counter, setCounter] = useState(5);

    function decrementCount() {
        setCounter(prevCount => prevCount - 1);
    }

    function incrementCount() {
        setCounter(prevCount => prevCount + 1);
    }

    return (
        <>
            <button onClick={decrementCount}>-</button>
            <span>{counter}</span>
            <button onClick={incrementCount}>+</button>
        </>
    );
}

```

The component renders a button to decrement the counter, a span to display the current counter value, and a button to increment the counter.

When you click a button, the corresponding function updates the state, causing React to re-render the component with the new counter value.



Key points

- State Updates Trigger Re-Renders:- When you update the state using setCounter, React re-renders the component with the new state value. This ensures that the UI always reflects the current state.
- Using Previous State:- Using a function with prevCount inside setCounter ensures that the state updates are based on the most recent state, avoiding conflicts and ensuring accurate updates.


### Optimizing useState Initialization

When you initialize state with a value, like useState(4), this initialization runs every time the component re-renders, which can be inefficient if the initialization is complex.

Solution :- To avoid running the initialization code multiple times, you can pass a function to useState. This function runs only once when the component mounts(render)

```javascript
 const [counter, setCounter] = useState(()=>{
console.log("running");
return 4;
});
```


Here, the initialization function only runs once, improving performance.



Another way: You can define the initialization function separately and pass it to useState.

```javascript
function countInitial() {
    console.log("running");
    return 4;
}

//run every time component re-render
const [counter, setCounter] = useState(countInitial());

//run once only
const [counter, setCounter] = useState(() => countInitial());

```


Full Example with Optimization

```javascript

function countInitial() {
    console.log("running");
    return 4;
}

function App() {
    const [counter, setCounter] = useState(() => countInitial());

    function decrementCount() {
        setCounter(prevCount => prevCount - 1);
    }

    function incrementCount() {
        setCounter(prevCount => prevCount + 1);
    }

    return (
        <>
            <button onClick={decrementCount}>-</button>
            <span>{counter}</span>
            <button onClick={incrementCount}>+</button>
        </>
    );
}

```


### useState with an object.
Sometimes, you have multiple pieces of state that you want to group together. Instead of creating multiple useState hooks, you can use a single hook with an object.

```javascript
function App() {
    const [state, setState] = useState({ count: 4, theme: "blue" });

    function decrementCount() {
        setState(prevState => {
            return { ...prevState, count: prevState.count - 1 };
        });
    }

    function incrementCount() {
        setState(prevState => {
            return { ...prevState, count: prevState.count + 1 };
        });
    }

    return (
        <>
            <button onClick={decrementCount}>-</button>
            <span>{state.count}</span>
            <span>{state.theme}</span>
            <button onClick={incrementCount}>+</button>
        </>
    );
}

```

Here, state is an object containing both count and theme. When you update the state, you use the spread operator ...prevState to keep the other properties intact.

### Key Points:
1. Optimization: Use a function to initialize state to ensure it runs only once.
2. Grouping State: Use an object in useState to manage multiple pieces of state together, reducing the number of hooks and simplifying updates.





# useEffect()



















