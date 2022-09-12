# ***Read: Class 39 - Redux - Additional Topics***

***

## **MobX**

MobX is a simple, scalable and battle tested state management solution. This tutorial will teach you all the important concepts of MobX in ten minutes. MobX is a standalone library, but most people are using it with React and this tutorial focuses on that combination.

State is the heart of each application and there is no quicker way to create buggy, unmanageable applications than by producing an inconsistent state or state that is out-of-sync with local variables that linger around. Hence many state management solutions try to restrict the ways in which you can modify state, for example by making state immutable. But this introduces new problems; data needs to be normalized, referential integrity can no longer be guaranteed and it becomes next to impossible to use powerful concepts like classes in case you fancy those.

MobX makes state management simple again by addressing the root issue: it makes it impossible to produce an inconsistent state. The strategy to achieve that is simple: Make sure that everything that can be derived from the application state, will be derived. Automatically.

Conceptually MobX treats your application like a spreadsheet.

![](https://mobx.js.org/assets/getting-started-assets/overview.png)

- First of all, there is the application state. Graphs of objects, arrays, primitives, references that forms the model of your application. These values are the “data cells” of your application.

- Secondly there are derivations. Basically, any value that can be computed automatically from the state of your application. These derivations, or computed values, can range from simple values, like the number of unfinished todos, to complex stuff like a visual HTML representation of your todos. In spreadsheet terms: these are the formulas and charts of your application.

- Reactions are very similar to derivations. The main difference is these functions don't produce a value. Instead, they run automatically to perform some task. Usually this is I/O related. They make sure that the DOM is updated or that network requests are made automatically at the right time.

- Finally there are actions. Actions are all the things that alter the state. MobX will make sure that all changes to the application state caused by your actions are automatically processed by all derivations and reactions. Synchronously and glitch-free.

***

## **Redux Toolkit**

The official, opinionated, batteries-included toolset for efficient Redux development.

- Simple:

Includes utilities to simplify common use cases like store setup, creating reducers, immutable update logic, and more.

- Opinionated

Provides good defaults for store setup out of the box, and includes the most commonly used Redux addons built-in.

- Powerful

Takes inspiration from libraries like Immer and Autodux to let you write "mutative" immutable update logic, and even create entire "slices" of state automatically.

- Effective

Lets you focus on the core logic your app needs, so you can do more work with less code.

***

## **Hookstate**

The most straightforward, extensible and incredibly fast state management that is based on React state hook

- Easy to Use

Concise, pragmatic but flexible API. Very easy to learn. See Getting Started and other code samples to learn it in minutes.

- Incredibly Fast

Incredible performance based on unique method for tracking of used/rendered and updated state segments. Ideal solution for huge states and very frequent updates.

- Feature Rich

Small core library packed with features: global states, local states, asynchronously loaded states, partial state updates, deeply nested state updates.

- First-class Typescript

Complete type inferrence for any complexity of structures of managed state data. Full IntelliSense support tested in VS Code.

- Plugins System

Extend or customize your state hooks. There are several standard plugins available: state snapshoting and rolling back, tracking modified fields, state validation and local storage persistence.

- Development Tools

Develop like a pro. Browser's extension to trace and set state values, to set breakpoints on state changes and to identify components using a segment of a state.

***

[README](README.md)
