# Advanced React.js Exam Paper

## Total Marks: 100

### Section A: Multiple Choice Questions (MCQs) [20 Marks]

1. **Which lifecycle method is invoked immediately after a component is added to the DOM?**
    - a) componentDidUpdate
    - b) componentDidMount
    - c) componentWillUnmount
    - d) shouldComponentUpdate  
    **[2 marks]**

2. **Which of the following hooks is used to handle state in a functional component?**
    - a) useContext
    - b) useEffect
    - c) useState
    - d) useReducer  
    **[2 marks]**

3. **What is the purpose of the `React.memo` function?**
    - a) Memoizes a function's result
    - b) Optimizes rendering by memoizing a component
    - c) Handles side effects
    - d) Manages component state  
    **[2 marks]**

4. **In React Router v6, which hook is used to access the navigation object?**
    - a) useHistory
    - b) useNavigate
    - c) useLocation
    - d) useParams  
    **[2 marks]**

5. **Which of the following statements about Context API is false?**
    - a) It is used to pass data through the component tree without props drilling.
    - b) Context can be used for global state management.
    - c) Context should be used as a substitute for Redux in every application.
    - d) Context can be consumed using the useContext hook.  
    **[2 marks]**

6. **How can you prevent a component from rendering in React?**
    - a) Return `null` from the render method
    - b) Use `shouldComponentUpdate` to return false
    - c) Both of the above
    - d) None of the above  
    **[2 marks]**

7. **What does the `useReducer` hook return?**
    - a) State and dispatch function
    - b) State and setState function
    - c) State and reducer function
    - d) State and action function  
    **[2 marks]**

8. **Which method is used to update the state in a class component?**
    - a) this.state
    - b) this.setState
    - c) this.useState
    - d) this.stateUpdate  
    **[2 marks]**

9. **What does the `StrictMode` component do?**
    - a) It is used for production build optimizations.
    - b) It checks for potential problems in an application.
    - c) It is used to apply strict linting rules.
    - d) It enables experimental features.  
    **[2 marks]**

10. **Which hook is used for data fetching in a functional component?**
    - a) useFetch
    - b) useData
    - c) useEffect
    - d) useRequest  
    **[2 marks]**

### Section B: Short Answer Questions [30 Marks]

1. **Explain the concept of Higher-Order Components (HOC) in React. Provide an example to illustrate your explanation.**  
   **[6 marks]**

2. **Describe the virtual DOM and how it enhances the performance of a React application.**  
   **[6 marks]**

3. **What are custom hooks in React? Create a simple custom hook for fetching data from an API.**  
   **[6 marks]**

4. **Discuss the differences between functional and class components in React. Provide scenarios where one might be preferred over the other.**  
   **[6 marks]**

5. **Explain the `useEffect` hook and its various use cases with examples.**  
   **[6 marks]**

### Section C: Practical Tasks [50 Marks]

1. **Task 1: State Management with Context API [20 Marks]**

    Create a simple application that demonstrates state management using Context API. The application should include:
    - A context provider that holds user information (e.g., name, email).
    - Components that consume the context data.
    - A form to update the user information within the context.

2. **Task 2: Advanced Routing with React Router [15 Marks]**

    Develop a multi-page React application using React Router v6. The application should include:
    - A navigation bar with links to at least three different routes (e.g., Home, About, Contact).
    - A route that uses URL parameters and displays dynamic content based on the parameter.
    - Proper handling of 404 errors with a custom error page.

3. **Task 3: Optimizing Performance [15 Marks]**

    Build a React application that fetches and displays a list of items from an API. Implement the following optimizations:
    - Use `React.memo` to prevent unnecessary re-renders of list items.
    - Implement pagination to load items in chunks.
    - Show a loading indicator while fetching data.
    - Handle errors gracefully with appropriate messages to the user.

---



or 

### Section C: Practical Tasks [50 Marks]

#### Task 1: Custom Hooks and Side Effects [20 Marks]

Create a simple application that demonstrates the use of custom hooks and side effects. The application should include:

- A custom hook for fetching data from an API.
- A component that uses this custom hook to display data.
- Handling of loading and error states within the custom hook.

#### Task 2: Form Handling and Validation [15 Marks]

Develop a form in React that includes the following:

- Input fields for name, email, and password.
- Real-time validation and error messages.
- Submission handling that displays a success message upon valid submission.

#### Task 3: Using Redux for State Management [15 Marks]

Build a simple application that demonstrates state management using Redux. The application should include:

- A Redux store with at least one slice of state (e.g., a list of items).
- Components that connect to the Redux store to read and update state.
- A button to add new items to the list and a way to display the list of items.

### Instructions:

- Answer all questions.
- For practical tasks, ensure the code is well-commented and structured.
- Utilize modern React practices and features wherever applicable.
- Manage your time effectively, allocating roughly 1 hour for each section.

**Good luck!**
