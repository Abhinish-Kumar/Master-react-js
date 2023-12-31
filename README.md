# Master-react-js
#### What is react-js,really?
1. React is officially defined as a "Javascript library for creating user interface" but what does that really mean?what is library?
2. React is a library,made in javascript and which we code in javascript, to build great application that run on the web.

#### Prerequisit for this course.
1. Must have a good knowledge of javascript to become a solid React programmer.
2. The most basic javascript concepts are like variable,basic data type,conditionals,array methods,functions, and Es6 modules.

#### If react is made up with javascript so why dont we use javascript?
1. React is indeed built with JavaScript, but it offers distinct advantages that can make development more efficient and organized.
2. Javascript is a 20years old language which was created for adding small bits of behaviour to the browser through scripts and was not designed for creating complete applications.
3. By using react we avoid to write a number of lines of code in javascript like geting elements from the html and apply some opetation on that html element.
4. React use declarative approach means we not need to create or describe every thing from scratch.

#### Can i use Javascript in React applications?
1. Yes! any valid javascript code can be included within your React applications.
2. You can use any browser or window API,such as geolocation or the fetch API.

#### How to create react apps?

##### There are three ways to create a React application.
1. Putting React in an HTML file with external scripts.
2. Using an in-browser React environment like CodeSandbox.
3. Create a React app on your computer using a tool like create-react-app.

#### What is the best way to create a React app?
1. Which is the best way to create your application depends on what you want to do with it.
2. If you want to create a complete application that you want to ultimately push to the web, it is the best to create that React application on your computer using a tool like create-react-app.
3. The easiest and most beginner friendly way to create and build React apps for learning and prototyping is to use a tool like CodeSandBox.

# JSX Elements

#### JSX is a powerful tool for structuring applications.
1. JSX borrows its syntax from most widely used programming language :html.
2. As a reasult ,JSX is a powerful tool to structure our applications.
3. Example of react element.

```javascript

<div>Hello World</div>

```
To be displayed in the browser ,React elements needs to be rendered (using ReactDOM.render())

#### How jsx is different from html.

1. We can write valid html in jsx,but what differs slightly is the way some attributes are written.
2. Attributes that consists of multiple words are written in camelcase syntax (ie className) and have different names than standard HTMl(class).

```javascript

<div id="header">

  <h1 className="title">Hello React</h1>

</div>

```
3. The reason JSX has this different way of writing attributes is because it is made using javascript functions (relax).

#### JSX must have a trailing slash if it is made up of one tag.

1. Unlike standard html, elements like input,img,br must cloe with a trailing forward shash for it to be valid jsx.

```javascript

<input type="email" />
<input type="email" > //is a syntax error

```
#### JSX have two tags must have a closing tag.
1. Elements that should have two tags,such as div,main,button, must have their closing,second tag in jsx, otherwise it will return in a syntax error.

   ```javascript
   
   <button>Click me</button>
   
   ```
#### How JSX elements are styled.
1. Inline styles are written differently as well as comared to plain HTML.
2. Inline styles must not be included as a string,but within an object.
3. Once again,the style properties that we use must be written in the camel-case style.

```javascript
<h1 style={{color:"blue",fontSize:22,padding:"0.5rem 1rem"}}>

  Hello World!

</h1>;
```
Style properties that accepts pixels values (like width,height,padding,margin,etc) can use integers insted of strings.For example.fontsize:22 insted of fontSize:"22px".

#### JSX can be conditionally displayed.
1. New React developers may be wondering how it is beneficial that React can use Javascript code.
2. One simple example if that conditionally hide or display JSX content, we can use any valid Javascript conditional,like an if statement or switch statement.
```javascript

const isAuthUser=true;

if(isAuthUser){
return <div>Hello World</div>
}else{
return <button>Login</button>
}

```
3. Where are we returning this code? Within a React component,which we will cover in a letter section.

#### JSX cannot be understood by the browser.
1. As mentioned above ,JSX is not HTML ,but a part of javascript functions.
2. In fact,writing <div>hello world</div> is JSX is just a more convinient and understandable way of writing code like the following:

```javascript

React.createElement("div",null,"Hello World");

```
3. Both pieces of code have the same output of "Hello World".
4. To write JSX and have the browser understandable this different syntax,we must use a Transpiler to convert JSX to these functions calls.
5. The most common transpiler is called Babble.


# Components

#### What are react components?
1. Insted of just rendering one or another set of JSX elements,we can include them within React components.
2. Components are created using what looks like a normal Javascript function,but is different in that return JSX elements.

```javascript

function Greeting(){
return <div>Hello ,React</div>
}

```

#### Why use React Components?
1. React comonents allow us to create more complex logic and structures within our React application than we would with JSX elements alone.
2. Think of React components as our React elements that have their own functionality.
3. As we know, functions allow us to create our own functionality and reuse it where we like across our application.
4. Components are reusable whereever we like across our app and as many times as we like.

#### Components are not normal javascript functions.
1. How would we render or display the returned JSX from the component above?

```javascript

import React from 'react';
import ReactDOM from 'react-dom';

function Greeting(){
return <div>Hello react</div>;
}

ReactDOM.render(<Greeting/>,document.getElementById("root"));

```
2. We use the 'React' import to parse the JSX and ReactDOM to render our component to a root element with the id of 'root'.

#### What can components return?
1. Components can return valid JSX elements ,as well as string,numbers,booleans,the value null,as well as arrays and fragments.
2. Why would we want to return null? It is common to return null if we want a component to display nothing.

```javascript

function Gretting(){

if(isAuthUser){
return "Hello again";
}else{
return null;
}

}

```
3. Another rule is that JSX elements must be wrapped in one parent element.Multiple sibling elements cannot be returned.
4. If you need to return multiple elements ,but dont need to add another element to the DOM (usually for a conditional),You can use a special Recat component called a fragment.
5. Fragments can be written as '<></>' or when you import React into your file,with <React.Fragment></React.Fragment>.

```javascript

function Greeting(){

const isAuthUser = true;

if(isAuthUser){
return (

<>
<h1>Hello react</h1>
<button>Logout</button>
</>
);
}else{
return null;
}


}
```

Note that when attempting to return a number of JSX elements that are spread over multiple lines,we can return it all using a set of parentheses () as you see in the example above.

#### Components can return other componets.
1. The most important thing components can return is other components.
2. Below is a basic example of a React application contained with in a component called 'App' that returns multiple components.

   ```javascript
   import React from 'react';
   import ReactDOM from 'react-dom';

   import Layer from './components/Layer';
   import Navbar from './components/Navbar';
   import Aside from './components/Aside';
   import Footer from './components/Footer';
   
   function App(){
   return (

        <Layer/>
        <Navbar/>
        <Aside/>
        <Footer/>

  );
  }
 
 ReactDOM.render(<App/>,document.getElementById('root'));
    ```
3. What is powerful about this is that we are using the customixation of components to describe what they are (ie. layout) and their function in our application.This tells us how they should be used just by looking at their name.
4. Additionally ,we are using the power of JSX to compose these components.In other words,to use the HTML-like syntax of JSX to structure them in an immediately understandable way(ie. the Navbar is at the top of the app,the Footer at the bottom,etc).

#### Javascript can be used in JSX using curly braces.

1. Just as we can use javasript variables within our components,we can use them directly within our JSX as well.
2. There are a few core rules to using dynamic values within JSX ,however.
3. JSX can accept any primitive values(strings,booleans,numbers),but it will not accept plain objects.
4. JSX can also include expressions that resolve to these values.
5. For Example,conditionals can be included within JSX using the ternary operator,since it resolve to a value.

```javascript

function Greeting(){
const isAuthUser = true;

return <div>{isAuthUser ? "Hello" : null} </div>;
}

```

# Props

#### Components can be passed values using props
1. Data passed to components in javascript are called props.
2. Props look identical to attributes on plain JSX/HTML elements,but you can access theirvalues within the component itself.
3. Props are valuable in parameters of the component to which they are passed Props are always included as properties of an object.

```javascript

ReactDOM.render(

<Greeting username="JOHN" />,
document.getElementById("root")

);

function Greeting(props){
return <h1>Hello {props.username}</h1>;
}

```
#### Props cannot be directly changed
1. Props must never be directly changed within the child component.
2. Another way to say this that props should never be mutated,since props are a plain javascript object.

```javascript

//We cannot modify the props object:

function header(props){

props.username = "Doug";
return <h1>Hello {props.name}</h1>;

}

````
Components are considered pure functions. That is.for every input,we should be able to expect the same output.This means we cannot mutate the props object ,only read from it.

#### Special props:the children prop
1. The children prop is useful if we want to pass elements/components as props to other components.
2. The children prop is especially useful for when you want the same component(such as a Layout component) to wrap all other components.

```javascript

function Layout(props){
return <div className="container>{props.children}</div>;
}

function IndexPage(){
return (
<Layout>

<Header/>
<Hero/>
<Footer/>

</Layout>
)
}

function AboutPage(){
return (
<Layout>
<About/>
<Footer/>
</Layout>
)
}



```

3. The benefit of this pattern is that all styles to the Layout component will be shared with its child components.

## List and Keys 

#### Iterate over arrays im JSX using map
1. How do we disaplays lists in JSX using array data?
2. Use the .map() funciton to convert lists of data (Arrays) into lists of elements.

```javascript

const people = ["John","smith","fred"];
const peopleList = people.map((person)=><p>{person}</p>;

```

3. .map can be used for components as well as plain JSX elements.

```javascript

function App(){
const people = ["John","smith","fred"];

return (
<ul>
{people.map((person)=>(
<Person name={person}/>
))}
</ul>
)
}
);}


function Person({name}){
//We access the 'name' prop directly using object destructuring
return <p>This person's name is : {name}</p>;
}
```


#### The importance of Keys in lists
1. Each React element within a list of elements needs a special key prop.
2. Keys are essential for React to be able to keep track of each element that is being iterated over wiht the .map() fuction.
3. React uses Keys to update individual elements when their data changes (insted of re-rendering the entire list).
4. Keys need to have unique values to be able to identify each of them according tp their key value.

```javascript

function App(){
const people = [
{id:"Ksy7py",name:"john},
{id:"ad7py",name:"rohn},
{id:"fads7py",name:"sohn},
];

return (
<ul>
{person.map((person)=>(
<Person key={person.id} name={person.name} />
 )
)
}
</ul>
);
}


```


## State and Managing Data








# Practice

```javascript

import React from "react";
import ReactDOM from "react-dom";

function Box(props) {
  return <p>Name : {props.name}</p>;
}

function Greeting() {
  return (
    <>
      <h1>List of employees</h1>
      <Box name="Gungun gupta" />
      <Box name="Abhinish" />
      <Box name="Anjali singhania" />
      <Box name="Radhika" />
    </>
  );
}

ReactDOM.render(<Greeting />, document.getElementById("root"));


```


```javascript

import React from "react";
import { useState } from "react";
import ReactDOM from "react-dom";

function Greeting() {
  const [counter, setCounter] = useState(10);
  return (
    <>
      <button onClick={() => setCounter((prevCount) => prevCount - 1)}>
        -
      </button>
      <h1>{counter}</h1>
      <button onClick={() => setCounter((prevCount) => prevCount + 1)}>
        +
      </button>
    </>
  );
}

ReactDOM.render(<Greeting />, document.getElementById("root"));


```













