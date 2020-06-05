## What is React

React is a JavaScript library that aims to simplify development of visual interfaces.

Developed at **Facebook** in 2011 and open-sourced in 2013, it drives some of the most widely used apps, powering Facebook and Instagram among countless other applications.

Its primary goal is to make it easy to reason about an interface and its state at any point in time, by dividing the UI into a collection of components.



## Single Page Applications

React app is usually built as a single page application.

You only load the code (HTML, CSS, JavaScript) once, and when you interact with the application, what generally happens is that JavaScript intercepts the browser events and instead of making a new request to the server that then returns a new document, the client requests some JSON or performs an action on the server but the page that the user sees is never completely wiped away, and behaves more like a desktop application.



## Declarative approach to building UIs

With React:

- you can build Web interfaces without even touching the DOM directly
- you can have an event system without having to interact with the actual DOM Events

We just tell React we want a component to be rendered in a specific way, and we never have to interact with the DOM to reference it later.



## Components

A component is one isolated piece of interface. In React everything is a component.

You create small and lean components and use them to compose more functionality on top of them.

When rendering a component, one can pass in values that are known as **props**.

There are two ways to define a component in React:

- a function component
- a class component



## Virtual DOM

React keeps a copy of the DOM representation, for what concerns the React rendering: the Virtual DOM.

React uses a Virtual DOM to help the browser use less resources when changes need to be done on a page.

When components change their inner state React applies **Reconciliation** algorithm:

- React updates the Virtual DOM relative to the changed (dirty) components marked as dirty (with some
  additional checks)
- it runs the diffing algorithm to reconcile the changes
- and then updates the real DOM

The key thing is that React batches much of the changes and performs a unique update to the real DOM, by changing all the elements that need to be changed at the same time, so the repaint and reflow the browser must perform to render the changes are executed just once.



## Component lifecycle

Up until recently, class components were the only way to define a component that had its own state, and could access the lifecycle methods.

During the lifetime of a component, there's a series of events that gets called, and to each event you can hook and provide custom functionality.

There are 3 phases in a React component lifecycle:

- Mounting
- Updating
- Unmounting



## JSX

JSX is a technology that was introduced by React.

Although React can work completely fine without using JSX, it's an ideal technology to work with components.

It looks like a strange mix of JavaScript and HTML, but in reality it's all JavaScript.

What looks like HTML, is actually syntactic sugar for defining components and their positioning inside the markup.

A browser cannot execute JavaScript files containing JSX code. They must be first transformed to regular JS. The most popular way to perform this is to use **Babel**.

JSX accepts any kind of JavaScript mixed into it. Whenever you need to add some JS, just put it inside curly braces `{}`.

You need to know a few differences between how you would define some things in HTML, and how you define them in JSX:

- you need to close all tags
- camelCase is the new standard
- class becomes className
- form fields definition and events are changed in JSX to provide more consistency and utility
- cool way to define CSS
- horizontal white space is trimmed to 1
- vertical white space is eliminated
- and some more things...



## Hooks

Before Hooks function components, lighter and more flexible, were limited in functionality.

Hooks allow function components to have state and to respond to lifecycle events too.

The most used (**Basic**) hooks are:

- useState - returns a stateful value, and a function to update it
- useEffect - accepts a function that contains imperative, possibly effectful code
- useContext - accepts a context object and returns the current context value for that context

The less used (**Advanced**) hooks are:

- useCallback, useMemo - returns a memoized callback
- some other hooks
- your own custom hooks - lets you extract component logic into reusable functions



## State variables - old and new way

If you’re coming from classes, you might be tempted to always call `useState` once and put all state into a single object. You can do it if you’d like.

However, **React developers recommend to split state into multiple state variables based on which values tend to change together**.

Both putting all state in a single `useState` call, and having a `useState` call per each field can work. Components tend to be most readable when you find a balance between these two extremes, and group related state into a few independent state variables. If the state logic becomes complex, they recommend managing it with a reducer or a custom Hook.



## Thinking in React

Start With A Mock

1. Break The UI Into A Component Hierarchy
2. Build A Static Version in React
3. Identify The Minimal (but complete) Representation Of UI State
4. Identify Where Your State Should Live
5. Add Inverse Data Flow

This should give you an idea of how to think about building components and applications with React.

Despite it may be a little more typing that code is modular and explicit and this approach is perfect for building large libraries of components.
