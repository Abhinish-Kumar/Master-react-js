# Assignment 1

## Q1:- If we delete node-module. How to run our react app successfully?

==> Reinstall projects dependenciess to run again successfully.

1. Delete node-modules

- Manually
- ```javascript
  
  >>>> rm -rf node-module (linux/mac)
  >>>> rmdir /S /Q node-module (windows)
  
  ```
S= including subdirectory
Q= without asking about canformation

2. Reinstall dependencies
Use specific package manger in your project.

```javascript

>>> npm install
>>> yarn install

```



## Q2:- How to install double console.log from react app?(Its not needed in real life to rmove them, its just an assignment problem) 

==> It occurs due to the "strict mode" component . "strict mode" is a development tool that helps identify potential problem in your application by intentially double-invoking certain lifecycle methods and other hooks to find and fix potential issues.

Solution==> just remove it.

## Q3:- Create a Page with multiple React App Both Apps should 

























