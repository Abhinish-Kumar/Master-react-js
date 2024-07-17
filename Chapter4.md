# Chapter 4 ( adding interactivity)


```javascript
function PlayButton() {
  return <button onClick={console.log("play")}>Play</button>;
}
```
correct

```javascript

function PlayButton() {
  return <button onClick={() => console.log("play")}>Play</button>;
}

```

or

```javascript

function PlayButton() {
  function handleClick() {
    console.log("play");
  }
  return <button onClick={handleClick}>Play</button>;
}

```

Note:- `onClick` is an event handler.
- Do not invoke the function directly; only define it.
- If the function is invoked directly, it will execute during the rendering phase instead of on the button click.















