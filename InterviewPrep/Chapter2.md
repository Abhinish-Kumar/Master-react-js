Here are some React JS logic challenges to test and improve your understanding of key concepts. Each question focuses on logic rather than syntax, so try to think through the underlying principles of React while solving them:

### 1. **Managing State in Components**
   - **Question:** You have a component that renders a list of items. When you click on an item, it should be marked as “selected” and turn bold, but only one item can be selected at a time. How would you implement this?
   - **Hints:** Consider using `useState` to keep track of the selected item’s ID and conditional styling based on that ID.

### 2. **Conditional Rendering with Props**
   - **Question:** You have a component `UserProfile` that takes in a prop called `userStatus`. If `userStatus` is “online,” it should render a green circle icon. If `userStatus` is “offline,” it should render a red circle. If the status is unknown, it should render a grey circle. Implement the logic to handle these different states.
   - **Hints:** Use conditional rendering to dynamically determine which icon should be displayed based on `userStatus`.

### 3. **Handling Asynchronous Data in Components**
   - **Question:** You need to create a component that fetches data from an API and displays it as a list. While the data is being fetched, a loading spinner should be shown. If the data fails to load, display an error message.
   - **Hints:** You’ll need `useEffect` for data fetching and `useState` for managing loading, error, and data states.

### 4. **Implementing a Counter with Functional Updates**
   - **Question:** Create a counter component that increments by 1 every second. When the count reaches 10, it should stop incrementing automatically. How would you handle this using React hooks?
   - **Hints:** `useState` to store the count, `useEffect` to create the interval, and `clearInterval` when the count reaches 10.

### 5. **Dynamic Form with Controlled Inputs**
   - **Question:** You’re building a dynamic form where users can add multiple inputs. Each input should be stored in an array of strings representing the entered values. Write the logic to add new inputs dynamically and capture the input values.
   - **Hints:** Use `useState` to manage the input list and map over the array to render each input. You might need `onChange` handlers to capture each input’s value.

### 6. **Memoization for Expensive Calculations**
   - **Question:** Suppose you have a component that performs a heavy calculation whenever a user inputs a number. To prevent unnecessary recalculations, implement memoization for this function.
   - **Hints:** Use `useMemo` to store the result of the calculation, only re-computing when the input number changes.

### 7. **Debouncing Search Input**
   - **Question:** Build a search input that triggers a fetch call only after the user stops typing for 500 milliseconds. This way, the API isn’t called on every keystroke.
   - **Hints:** Implement a debouncing function using `useEffect` with a timer. Clear the timer whenever the user types within the 500ms interval.

### 8. **Handling Complex State with `useReducer`**
   - **Question:** Imagine a shopping cart component where items can be added, removed, and their quantities can be adjusted. Implement logic to handle these three actions with `useReducer`.
   - **Hints:** Define actions like `ADD_ITEM`, `REMOVE_ITEM`, and `UPDATE_QUANTITY` and a reducer function that modifies the cart state accordingly.

### 9. **Creating a Toggleable Accordion**
   - **Question:** Build an accordion component where only one section can be open at a time. When a section is clicked, it should expand to show content, and any other open section should close.
   - **Hints:** Track the ID of the currently open section in state, and set it to `null` if the section is clicked again.

### 10. **Rendering a List with Conditional Styles**
   - **Question:** Display a list of items with each item having a status (e.g., completed or pending). If an item is completed, display it with a green checkmark icon. Otherwise, display it with a red cross icon. How would you implement this logic?
   - **Hints:** Use `map` to iterate over the list and conditional rendering based on the item’s `status` property.

These questions cover a range of core React concepts, from state and lifecycle management to hooks and conditional rendering, and should help build a strong understanding of React's logic. Let me know if you'd like solutions or explanations for any specific problem!
