Here’s a brief overview of each React performance optimization strategy along with examples:

### 1. List Virtualization or Windowing
To reduce memory usage and server load, list virtualization renders only the visible list items, recycling the components as the user scrolls.
- **Example**: Using `react-virtualized`
   ```jsx
   import { List } from 'react-virtualized';

   function VirtualizedList({ items }) {
     return (
       <List
         width={300}
         height={300}
         rowCount={items.length}
         rowHeight={20}
         rowRenderer={({ index, key, style }) => (
           <div key={key} style={style}>{items[index]}</div>
         )}
       />
     );
   }
   ```

### 2. Lazy Loading Images
Lazy loading loads low-resolution images first and full quality when the placeholder is in view.
- **Example**:
   ```jsx
   import { LazyLoadImage } from 'react-lazy-load-image-component';

   function ImageComponent() {
     return <LazyLoadImage src="image.jpg" alt="Example Image" />;
   }
   ```

### 3. Memoization
Memoization stores results of expensive calculations and reuses them for the same inputs.
- **Example**:
   ```jsx
   import React, { useMemo } from 'react';

   function ExpensiveComponent({ value }) {
     const result = useMemo(() => calculateExpensiveValue(value), [value]);
     return <div>{result}</div>;
   }
   ```

### 4. Throttling and Debouncing Events
Throttle and debounce limit how often events are triggered to avoid performance hits from frequent events like scrolling.
- **Example**:
   ```javascript
   const throttledFn = throttle(() => console.log("Throttled"), 1000);
   const debouncedFn = debounce(() => console.log("Debounced"), 1000);
   ```

### 5. Code Splitting
Code splitting loads only the required parts of the app, reducing initial load time.
- **Example**:
   ```jsx
   import React, { lazy, Suspense } from 'react';

   const LazyComponent = lazy(() => import('./Component'));

   function App() {
     return (
       <Suspense fallback={<div>Loading...</div>}>
         <LazyComponent />
       </Suspense>
     );
   }
   ```

### 6. React Fragments
Fragments allow grouping of elements without adding extra nodes to the DOM.
- **Example**:
   ```jsx
   function FragmentComponent() {
     return (
       <>
         <p>First element</p>
         <p>Second element</p>
       </>
     );
   }
   ```

### 7. Web Workers
Web Workers handle long-running tasks in a separate thread, preventing UI blocking.
- **Example**:
   ```javascript
   const worker = new Worker('worker.js');
   worker.postMessage('start');
   worker.onmessage = (e) => console.log(e.data);
   ```

### 8. `useTransition` Hook
`useTransition` allows transitions without blocking the UI, often used to defer state updates.
- **Example**:
   ```jsx
   import React, { useState, useTransition } from 'react';

   function TransitionComponent() {
     const [isPending, startTransition] = useTransition();
     const [count, setCount] = useState(0);

     const handleClick = () => {
       startTransition(() => setCount(count + 1));
     };

     return (
       <div>
         <button onClick={handleClick}>Increment</button>
         {isPending ? 'Loading...' : count}
       </div>
     );
   }
   ``` 

