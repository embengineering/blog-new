---
title: "Introduction to React Data Flow"
summary: "An introduction to React Data Flow"
layout: post
date: "2016-03-18 12:00:00 -0600"
published: false
---
While working with React, I constantly need to reference critical concepts about this technology. That's why I created this post, to reconcile how React data flows in a simple way, easy to understand.

Let's start reviewing why React is so powerful and useful.

## Why React?

### Simple
Simply define how your application will look at a specific time and React will manage all UI changes when the underlying data changes.

### Reusable and Modular

React components are like LEGO bricks, you can reuse them in many different ways. Changing the underlying data may result in a different representation.

### Fast

React uses a virtual DOM to determine what changed in order to [reconcile](https://facebook.github.io/react/docs/reconciliation.html) and apply as few mutations as possible.

![React Virtual Dom](/assets/posts/2016-04-01/react-virtual-dom.png)

## What's React?

* Just a JavaScript library for building User Interfaces.
* Is the `V` (view) in the `MVC` pattern.
* Performance focused (Virtual DOM)
* Modular (Components)
* Looks like HTML

```html
<ParentComponent>
  <ChildComponent />
</ParentComponent>
```

# Data Flow

In React, data flows in **one direction**, from **Parent to Child**.  This helps components to be **simple** and **predictable**.  When components receive `props` from the parent, they either **apply modifications (Render)** or **pass it to a child** that may use it. Consider React components as simple functions that receive `props` and `state` and return HTML.

![React Data Flow](/assets/posts/2016-04-01/react-data-flow.png)

`Props` are **"properties"** passed to a child component that can hold any data.

Considering React components looks like HTML tags, `props` are passed as **"HTML attributes"**.

```html
<Square size="25" className="highlight" onClick={onClick} />
```

Take in mind that JavaScript has reserved words such as **class**, so passing a CSS class can be done using **className**. For all supported `props` types, please refer [here](https://facebook.github.io/react/docs/reusable-components.html#prop-validation).

There are two types of components **Stateful** and **Sateless**.  Because `state` is a whole different topic, let's summarize this concept.  **Sateful Components** are the ones that internally modify the underlying data, and **Sateless Components** are only `pure components` that respond to the underlying data received, without modifying it.

Let's define the `state` as the **private data a component's event handlers may change to trigger an UI update**. Please reference [here](https://facebook.github.io/react/docs/interactivity-and-dynamic-uis.html#how-state-works) for more information.

Be aware that in an ideal world, most of your components would be **stateless functions** because in the future we’ll also be able to make performance optimizations specific to these components by avoiding unnecessary checks and memory allocations. This is the [recommended pattern](https://facebook.github.io/react/docs/reusable-components.html#stateless-functions).

# Communication Between Components

In order to communicate between two components that don't have a parent-child relationship, a global event system can be used. We need to subscribe to events in `componentDidMount()`, unsubscribe in `componentWillUnmount()`, and call `setState()` when an event is received.  [Flux](https://facebook.github.io/flux/docs/overview.html) and [Redux](http://redux.js.org/index.html) are some of the possible ways to arrange this in a more elegant way.  Please take a look at all of the [Lifecycle Methods](https://facebook.github.io/react/docs/component-specs.html#lifecycle-methods) supported on a React component for more details.
