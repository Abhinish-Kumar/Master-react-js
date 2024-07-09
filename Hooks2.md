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




























