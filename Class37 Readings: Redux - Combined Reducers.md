# ***Read: Class 37 - Redux - Combined Reducers***

***

## ***combineReducers(reducers)***

***

## **Definition**

The combineReducers are helper function turns an object whose values are different reducing functions into a single reducing function you can pass to createStore.

The resulting reducer calls every child reducer, and gathers their results into a single state object. The state produced by combineReducers() namespaces the states of each reducer under their keys as passed to combineReducers().

Example:

    rootReducer = combineReducers({potato: potatoReducer, tomato: tomatoReducer})
    // This would produce the following state object
    {
    potato: {
        // ... potatoes, and other state managed by the potatoReducer ...
    },
    tomato: {
        // ... tomatoes, and other state managed by the tomatoReducer, maybe some nice sauce? ...
        }
    }

## **Arguments:**

    reducers (Object): An object whose values correspond to different reducing functions that need to be combined into one. See the notes below for some rules every passed reducer must follow.

Earlier documentation suggested the use of the ES6 import * as reducers syntax to obtain the reducers object. This was the source of a lot of confusion, which is why we now recommend exporting a single reducer obtained using combineReducers() from reducers/index.js instead. An example is included below.

Returns

    (Function): A reducer that invokes every reducer inside the reducers object, and constructs a state object with the same shape.

***

## ***Using combineReducers***

***

## **Core Concepts**

    The most common state shape for a Redux app is a plain Javascript object containing "slices" of domain-specific data at each top-level key. Similarly, the most common approach to writing reducer logic for that state shape is to have "slice reducer" functions, each with the same (state, action) signature, and each responsible for managing all updates to that specific slice of state. Multiple slice reducers can respond to the same action, independently update their own slice as needed, and the updated slices are combined into the new state object.

## **Defining State Shape**

    There are two ways to define the initial shape and contents of your store's state. First, the createStore function can take preloadedState as its second argument. This is primarily intended for initializing the store with state that was previously persisted elsewhere, such as the browser's localStorage. The other way is for the root reducer to return the initial state value when the state argument is undefined. These two approaches are described in more detail in Initializing State, but there are some additional concerns to be aware of when using combineReducers.

    combineReducers takes an object full of slice reducer functions, and creates a function that outputs a corresponding state object with the same keys. This means that if no preloaded state is provided to createStore, the naming of the keys in the input slice reducer object will define the naming of the keys in the output state object. The correlation between these names is not always apparent, especially when using ES6 features such as default module exports and object literal shorthands.

Here's an example of how use of ES6 object literal shorthand with combineReducers can define the state shape:

    // reducers.js
    export default theDefaultReducer = (state = 0, action) => state

    export const firstNamedReducer = (state = 1, action) => state

    export const secondNamedReducer = (state = 2, action) => state

    // rootReducer.js
    import { combineReducers, createStore } from 'redux'

    import theDefaultReducer, {
    firstNamedReducer,
    secondNamedReducer
    } from './reducers'

    // Use ES6 object literal shorthand syntax to define the object shape
    const rootReducer = combineReducers({
    theDefaultReducer,
    firstNamedReducer,
    secondNamedReducer
    })

    const store = createStore(rootReducer)
    console.log(store.getState())
    // {theDefaultReducer : 0, firstNamedReducer : 1, secondNamedReducer : 2}

***

[README](README.md)
