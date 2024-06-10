# Hooks

## What are hooks in react?
React Hooks are functions introduced in React 16.8 that allow you to use state and other React features without writing a class. Previously, managing state and side effects in React required class components. With Hooks, you can handle state, lifecycle methods, and other functionalities directly in functional components, making the code more concise and easier to understand. This means you can use functional components to do everything that you could do with class components, but in a simpler and more efficient way.

## Why we use hooks in react?
React Hooks were introduced to address several limitations and complexities associated with class components.React Hooks provide a more straightforward and powerful way to manage state and side effects in functional components. 

## What are the react features?
React Hooks provide a more straightforward and powerful way to manage state and side effects in functional components. They improve code readability, reusability, and maintainability while avoiding some of the pitfalls of class components. This makes development in React more efficient and enjoyable.

### 1. useState
1. Manages local component state.
2. Returns a state variable and a function to update it.

```javascript

const [count, setCount] = useState(0);

```

### 2. Enhanced Performance

Hooks can optimize performance by allowing more granular updates and reducing unnecessary re-renders. They also make it easier to memoize functions and values with useMemo and useCallback

### 3. Avoidance of this Keyword

Hooks eliminate the use of the this keyword, which can be confusing and error-prone, especially for newcomers to React.

### 4. Cleaner and More Concise Code

Hooks simplify component code by removing the need for lifecycle methods and binding functions to this. This makes the code more readable and maintainable.

### 5. avoid repeated logic
You can write the logic of the component outside the component that protect from rewriting the code again and again. You not need to write the logic of the component within the component.



# Hooks type

## useState(), useEffect()
Both are really very usefull hooks in react.

1. useState()
2. useEffect()

### What is useState?
useState is a hook that lets you add state variables to your functional components. Previously, only class components could have state, but with hooks, functional components can now manage state as well.


### mechanish

```javascript

>> console.log(useState(200));
<< Array(2)
        0:200
        1:f()
```
UseState return the array of two values

1. Value that we pass in the useState().
2. 2nd value is the function.

Note:- to use both we have to extract it by destructuring it.

```javascript

const arr=useState(200);
const state=arr[0];
const useState=arr[1];

```

1. state store the current value.
2. setState is a function that is used to update the state and rerender the state.


Note:- const will show you error in state because constant value we can not change.

```javascript

<h1 onClick={()=>{

     setState(200)

}} {state}</h1>
```





































