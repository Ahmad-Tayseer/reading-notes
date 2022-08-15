# ***Read: Class 29 - Advanced State with Reducers***

***

## ***useReducer hook***

***

## **Name an alternative to the useState Hook.**

useReducer is an alternative to useState hook.

    const [state, dispatch] = useReducer(reducer, initialArg, init);

***

## **Why might the useReducer Hook be preferable to the useState Hook?**

useReducer is usually preferable to useState when you have complex state logic that involves multiple sub-values or when the next state depends on the previous one. useReducer also lets you optimize performance for components that trigger deep updates because you can pass dispatch down instead of callbacks.

***

## **What are two ways to set the initial state?**

There are two different ways to initialize useReducer state. You may choose either one depending on the use case. The simplest way is to pass the initial state as a second argument:

    const [state, dispatch] = useReducer(
    reducer,
    {count: initialCount}
    );

- Lazy initialization: You can also create the initial state lazily. To do this, you can pass an init function as the third argument.

- Bailing out of a dispatch: If you return the same value from a Reducer Hook as the current state, React will bail out without rendering the children or firing effects. (React uses the Object.is comparison algorithm.)

***
***

## ***Ultimate Guide to useReducer***

***

## **In terms of state, what does useReducer expect to receive as a parameter?**

The useReducer Hook is used to store and update states, just like the useState Hook. It accepts a reducer function as its first parameter and the initial state as the second:

    const [count, dispatch] = useReducer(reducer, initialState);

The reducer function itself accepts two parameters and returns one value. The first parameter is the current state, and the second is the action. The state is the data we are manipulating. The reducer function receives an action, which is executed by a dispatch function:

    function reducer(state, action) { }

    dispatch({ type: 'increment' })

***

## **What does useReducer return?**

useReducer returns an array that holds the current state value and a dispatch function to which you can pass an action and later invoke it. While this is similar to the pattern Redux uses, there are a few differences.

***

## **Explain dispatch to a non-technical recruiter.**

- The dispatch function accepts an object that represents the type of action we want to execute when it is called. Basically, it sends the type of action to the reducer function to perform its job, which, of course, is updating the state.

- The action to be executed is specified in our reducer function, which in turn, is passed to the useReducer. The reducer function will then return the updated state.

- The actions that will be dispatched by our components should always be represented as one object with the type and payload key, where type stands as the identifier of the dispatched action and payload is the piece of information that this action will add to the state.

***

[README](README.md)
