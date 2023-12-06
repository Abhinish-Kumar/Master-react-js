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

   ```













