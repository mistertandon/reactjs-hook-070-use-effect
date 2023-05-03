## useState Hook
- [useState](https://reactjs.org/docs/hooks-overview.html) documentation.
- useState is a Hook. We call it inside a function component to add some local state to it. useState returns a pair: the current state value and a function that lets you update it.
- The only argument to useState is the initial state.

## useEffect Hook
- The component rendering and side-effect logic are independent.

- Examples of side-effects are fetch requests, manipulating DOM directly, using timer functions like setTimeout(), and more.

- How to decouple rendering from the side-effect? Welcome useEffect() — the hook that runs side-effects independently of rendering.

- useEffect() hook accepts 2 arguments:

    useEffect(callback[, dependencies]);

    Put your side-effect logic into the callback function, then use the dependencies argument to control when you want the side-effect to run. That's the sole purpose of useEffect().

- callback is the function containing the side-effect logic. callback is executed right after changes were being pushed to DOM.

- we can return a function inside it and this return function is where the cleanup happens.

- The cleanup function prevents memory leaks and removes some unnecessary and unwanted behaviors.

```
useEffect(() => { 
   document.addEventListener('click', handleClick);

   return function cleanup () {
     document.removeEventListener('click', handleClick);
   }
}, [])
```

> Here we return a cleanup function with the removing logic of our event. As per react hooks rule whenever an effect received a return function it runs only at the time of cleanup of the component.