Forms in React are essential components for collecting and handling user input. They differ from traditional HTML forms in several ways, primarily due to React's stateful nature and its declarative approach to UI development. Here's an in-depth look at how forms work in React:

## Basic Concepts

### Controlled vs Uncontrolled Components

 #### 1. Controlled Components:
 Controlled component is a component which have one or more input field.
 When we control input field through state then that component is called as controlled component.
Uncontrolled components are the components that are directly handled by the dom. getElementById is a uncontrolled way to get the input data.
COntrolled is handled by react js state and uncontrolled is handled by dom.



```javascript

import { useState } from "react";

function Form() {
  const [blog, setBlog] = useState({
    id: 12,
  });
  function handleChange(e) {
    console.log(e.target.value);
    setBlog({ ...blog, [e.target.name]: e.target.value });
    console.log(blog);
  }
  function handleSubmit(e) {
    e.preventDefault();
    console.log(blog);
  }
  return (
    <div className="Form">
      <form>
        <input type="text" onChange={handleChange} name="City" />
        <input type="text" onChange={handleChange} name="Course" />
        <button onClick={handleSubmit}>Submit</button>
      </form>
    </div>
  );
}

export default Form;


```















 
