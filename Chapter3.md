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

 
