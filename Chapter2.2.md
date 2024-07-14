# Assignment 2

## Q1.) Object as props.

```javascirpt
import React from "react";
import Video from "./Video";
import "./App.css";

// Object defined outside the component
let obj = {
  title: "React js",
  bgColor: "red",
  channel: "Hello Dodo",
  views: "1M",
  time: "6 months ago",
};

function App() {
  return (
    <>
      <h1>Hello World</h1>
      <Video {...obj} />

      <Video
        title="Node js"
        bgColor="green"
        channel="Hello Dodo"
        views="10M"
        time="2 months ago"
      />
    </>
  );
}

export default App;

```


Note:- while both approaches are valid, using an object outside the component is advantageous for sharing common props across instances, promoting reusability and maintaining consistency. Props defined inside the component offer flexibility for specific instance customization and dynamic changes. Choosing between them depends on the specific needs and structure of your application.










