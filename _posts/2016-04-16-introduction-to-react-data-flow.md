---
title: "Introduction to React Data Flow"
layout: post
date: 2016-04-16
thumbnail: "{{site.baseurl}}/assets/images/football-passing.gif"
---
![Post Thumbnail](/assets/images/football-passing.gif)

In **React JS**, data flows in **one direction**, from **Parent to Child**.  This helps components to be **simple** and **predictable**.
<!--more-->

>*"Simplicity is the ultimate sophistication." -Leonardo da Vinci*

Consider React components as simple functions that receive **props** and **state** and return HTML.  When child components receive **props** from their parents, they either **apply modifications** (render) or **pass it to another child** that may use it.

![React Data Flow](/assets/images/react-data-flow.png)

**Props** are properties passed to a child component that can hold many [data types](https://facebook.github.io/react/docs/reusable-components.html#prop-validation) (e.g. array, object, number, function, others).  Considering React components looks like HTML tags, **props** are the **attributes** of the **HTML element**.  On the following example, **Square** is the component, **size**, **className** and **onClick** are the **props**.

```html
<Square size="25" className="highlight" onClick={handleClick} />
```

**Note:** Take in mind that JavaScript has reserved words such as **class**.  Passing a CSS class can be done using **className**.

## Two types of components: **Stateful** and **Sateless**.  

**Sateful Components.** Functions that internally modify the underlying data (props).

<iframe height='266' scrolling='no' src='//codepen.io/embengineering/embed/xVjrOj/?height=266&theme-id=0&default-tab=js,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/embengineering/pen/xVjrOj/'>react-hello-world-es6-stateful</a> by Emmanuel Morales (<a href='http://codepen.io/embengineering'>@embengineering</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

**Sateless Components.** Pure components that respond to the underlying data received (props), without modifying it. A pure function is a function where the return value is only determined by its input values, without observable side effects.

<iframe height='257' scrolling='no' src='//codepen.io/embengineering/embed/reJXVg/?height=257&theme-id=0&default-tab=js,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='http://codepen.io/embengineering/pen/reJXVg/'>react-hello-world-es6</a> by Emmanuel Morales (<a href='http://codepen.io/embengineering'>@embengineering</a>) on <a href='http://codepen.io'>CodePen</a>.
</iframe>

## What's the State?

Because the **State** in React is a full topic itself, let's quickly define it as the **private data a component may change to trigger an UI update, in response to an event**. [How state works?](https://facebook.github.io/react/docs/interactivity-and-dynamic-uis.html#how-state-works)

Be aware that in an ideal world, most of your components would be **stateless functions** because in the future we’ll also be able to make performance optimizations specific to these components by avoiding unnecessary checks and memory allocations. This is the [recommended pattern](https://facebook.github.io/react/docs/reusable-components.html#stateless-functions).

## Communication Between Components

In order to communicate between two components that don't have a parent-child relationship, a global event system can be used. We need to subscribe to events in `componentDidMount()`, unsubscribe in `componentWillUnmount()`, and call `setState()` when an event is received.  [Flux](https://facebook.github.io/flux/docs/overview.html) and [Redux](http://redux.js.org/index.html) are some of the possible ways to arrange this in a more elegant way.  Please take a look at all of the [Lifecycle Methods](https://facebook.github.io/react/docs/component-specs.html#lifecycle-methods) supported on a React component for more details.

## Conclusion

There are many ways of building React applications, but the unidirectional communication between components is what makes React one of the easiest libraries to debug and work with.  Furthermore, working with **Stateless** components and combine it with an event system such as **Redux** can help you create a clean infrastructure to manage your UI in an organized and scalable way.

Later, I'll be covering how to build a simple application using Redux and how to manage the application data, simple an more predictable; so keep in touch. :)
