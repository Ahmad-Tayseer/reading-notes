# ***Read: Class 38 - Redux - Asynchronous Actions***

***

## **Redux Middleware and Side Effects**

By itself, a Redux store doesn't know anything about async logic. It only knows how to synchronously dispatch actions, update the state by calling the root reducer function, and notify the UI that something has changed. Any asynchronicity has to happen outside the store.

A "side effect" is any change to state or behavior that can be seen outside of returning a value from a function. Some common kinds of side effects are things like:

- Logging a value to the console
- Saving a file
- Setting an async timer
- Making an AJAX HTTP request
- Modifying some state that exists outside of a function, or mutating arguments to a function
- Generating random numbers or unique random IDs (such as Math.random() or Date.now())

## **Using Middleware to Enable Async Logic**

One possibility is writing a middleware that looks for specific action types, and runs async logic when it sees those actions, like these examples:

    import { client } from '../api/client'

    const delayedActionMiddleware = storeAPI => next => action => {
    if (action.type === 'todos/todoAdded') {
        setTimeout(() => {
        // Delay this action by one second
        next(action)
        }, 1000)
        return
    }

    return next(action)
    }

    const fetchTodosMiddleware = storeAPI => next => action => {
    if (action.type === 'todos/fetchTodos') {
        // Make an API call to fetch todos from the server
        client.get('todos').then(todos => {
        // Dispatch an action with the todos we received
        storeAPI.dispatch({ type: 'todos/todosLoaded', payload: todos })
        })
    }

    return next(action)
    }

## **Redux Async Data Flow**

o how do middleware and async logic affect the overall data flow of a Redux app?

Just like with a normal action, we first need to handle a user event in the application, such as a click on a button. Then, we call dispatch(), and pass in something, whether it be a plain action object, a function, or some other value that a middleware can look for.

Once that dispatched value reaches a middleware, it can make an async call, and then dispatch a real action object when the async call completes.

Earlier, we saw a diagram that represents the normal synchronous Redux data flow. When we add async logic to a Redux app, we add an extra step where middleware can run logic like AJAX requests, then dispatch actions. That makes the async data flow look like this:

![](https://d33wubrfki0l68.cloudfront.net/08d01ed85246d3ece01963408572f3f6dfb49d41/4bc12/assets/images/reduxasyncdataflowdiagram-d97ff38a0f4da0f327163170ccc13e80.gif)

## **Using the Redux Thunk Middleware**

As it turns out, Redux already has an official version of that "async function middleware", called the Redux "Thunk" middleware. The thunk middleware allows us to write functions that get dispatch and getState as arguments. The thunk functions can have any async logic we want inside, and that logic can dispatch actions and read the store state as needed.

## **Configuring the Store**

The Redux thunk middleware is available on NPM as a package called redux-thunk. We need to install that package to use it in our app:

    npm install redux-thunk

Once it's installed, we can update the Redux store in our todo app to use that middleware:

    src/store.js
    import { createStore, applyMiddleware } from 'redux'
    import thunkMiddleware from 'redux-thunk'
    import { composeWithDevTools } from 'redux-devtools-extension'
    import rootReducer from './reducer'

    const composedEnhancer = composeWithDevTools(applyMiddleware(thunkMiddleware))

    // The store now has the ability to accept thunk functions in `dispatch`
    const store = createStore(rootReducer, composedEnhancer)
    export default store

***

[README](README.md)
