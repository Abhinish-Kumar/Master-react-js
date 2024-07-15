 # Chapter 3 (conditional rendering)

## Render verified or unverified video with condition.


 ```javascript

import "./Video.css";
function Video({ title, channel, views, time }) {
let verified = true;
let channelJSX = null;

if(verified){
channelJSX =  <div className="channel">{channel} ✅</div>
}else{
channelJSX=<div className="channel">{channel} </div>
}
 return (
   <div className="container" key={title}>
     <div className="pic">
       <img
         src="https://graphicsfamily.com/wp-content/uploads/edd/2021/02/Digital-marketing-agency-banner-template-design-2048x1152.jpg"
         alt=""
       />
     </div>

     <div>{title} mastery course</div>
     {channelJSX}
     <div className="views">
       {views} views <span>.</span> {time}
     </div>
   </div>
 );
}

export default Video;

```

 <img src="/image/image3.png" />



### With props



```javascript
import React from "react";
import Video from "./Video";
import "./App.css";
let obj = {
  title: "React js",
  bgColor: "red",
  channel: "Hello Dodo",
  views: "1M",
  time: "6 months ago",
  verified: true,
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
        verified={false}
      />
      <Video
        title="Mongodb"
        bgColor="green"
        channel="Hello Dodo"
        views="10M"
        time="9 months ago"
        verified={true}
      />
    </>
  );
}

export default App;

```


```javascript
import "./Video.css";
function Video({ title, channel, views, time, verified }) {
  return (
    <div className="container" key={title}>
      <div className="pic">
        <img
          src="https://graphicsfamily.com/wp-content/uploads/edd/2021/02/Digital-marketing-agency-banner-template-design-2048x1152.jpg"
          alt=""
        />
      </div>

      <div>{title} mastery course</div>
      {verified ? (
        <div className="channel">{channel} ✅</div>
      ) : (
        <div className="channel">{channel} </div>
      )}
      <div className="views">
        {views} views <span>.</span> {time}
      </div>
    </div>
  );
}

export default Video;

```


### Optimize more

```javascript
import "./Video.css";
function Video({ title, channel, views, time, verified }) {
  return (
    <div className="container" key={title}>
      <div className="pic">
        <img
          src="https://graphicsfamily.com/wp-content/uploads/edd/2021/02/Digital-marketing-agency-banner-template-design-2048x1152.jpg"
          alt=""
        />
      </div>

      <div>{title} mastery course</div>
      <div className="channel">{channel} {verified ? '✅' : null} </div>
      <div className="views">
        {views} views <span>.</span> {time}
      </div>
    </div>
  );
}

export default Video;

```


### You can use Shortcircuit ,Using the && Operator for Conditional Rendering

```javascript
   <div className="channel">
        {channel} {verified && "✅"}
      </div>
```
The `&&` operator evaluates the expression on its left side. If the left side is `true`, it returns the right side; if the left side is `false`, it returns `false`. This behavior can be leveraged for rendering in JSX.




# Render a video list (array of objects)



```javascript
import React from "react";
import Video from "./Video";
import "./App.css";
let videoList = [
  {
    title: "React js",
    bgColor: "red",
    channel: "Hello Dodo",
    views: "1M",
    time: "6 months ago",
    verified: true,
  },
  {
    title: "Node js",
    bgColor: "red",
    channel: "Hello Dodo",
    views: "3M",
    time: "4 months ago",
    verified: false,
  },
  {
    title: "Next js",
    bgColor: "red",
    channel: "Hello Dodo",
    views: "9M",
    time: "1 months ago",
    verified: true,
  },
  {
    title: "Electron js",
    bgColor: "red",
    channel: "Hello Dodo",
    views: "10M",
    time: "11 months ago",
    verified: false,
  },
];

function App() {
  return (
    <>
      <h1>Hello World</h1>
      <div className="main-body">
        {videoList.map((video) => {
          return (
            <Video
              title={video.title}
              bgColor={video.bgColor}
              channel={video.channel}
              views={video.views}
              time={video.time}
              verified={video.verified}
            />
          );
        })}
      </div>
    </>
  );
}

export default App;

```


```javascript
import "./Video.css";
function Video({ title, channel, views, time, verified }) {
  return (
    <div className="container" key={title}>
      <div className="pic">
        <img
          src="https://graphicsfamily.com/wp-content/uploads/edd/2021/02/Digital-marketing-agency-banner-template-design-2048x1152.jpg"
          alt=""
        />
      </div>

      <div>{title} mastery course</div>

      <div className="channel">{channel} {verified ? '✅' : null} </div>
      {/* <div className="channel">
        {channel} {verified && "✅"}
      </div> */}

      <div className="views">
        {views} views <span>.</span> {time}
      </div>
    </div>
  );
}

export default Video;


```

 <img src="/image/image4.png" />




 
