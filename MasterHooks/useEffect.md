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




















