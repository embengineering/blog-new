---
title: "Introduction to React"
summary: "Quick introduction to React"
layout: post
date: 2016-04-13
---
I constantly see myself referencing critical concepts about React. There is too much information out there, so my intention is to reconcile important concepts about this technology.

On this post, I'm going to cover an **Introduction to React** by answering three questions: **Why, How, What**, by following the idea of the ["Golden Circle"](http://www.ted.com/talks/simon_sinek_how_great_leaders_inspire_action).

## Why?

**Simplicity.**  Because there is always a better of building web applications.

> *“Life is really simple, but we insist on making it complicated.” -Confucius*

## How?

**Solving one problem.**  According to Facebook, React was built to solve one problem:  *building large applications with data that changes over time*.

Large applications such as Manufacturing (MES), Hospital, Pharma, and Time & Attendance systems, often require too many user interactions.  Constantly, the application data changes from everywhere: APIs, mobile devices, interfaces, etc.  Performance is affected heavily.  Also, organization, maintenance and scalability were taken in consideration when building this technology.

**It's Simple.**  Simply define how your application will look at a specific time and React will manage all UI changes when the underlying data changes. Try modifying the **name** string on the following [example](http://codepen.io/embengineering/pen/reJXVg).

<p data-height="206" data-theme-id="0" data-slug-hash="reJXVg" data-default-tab="js" data-user="embengineering" class="codepen">See the Pen <a href="https://codepen.io/embengineering/pen/reJXVg/">react-hello-world-es6</a> by Emmanuel Morales (<a href="http://codepen.io/embengineering">@embengineering</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

**It's Reusable and Modular.**  React components are like [LEGO](http://www.lego.com/en-us/) bricks, you can reuse them in many different ways. Changing the underlying data may result in a different representation. On the following example we re-use the **Hello** component multiple times with a different overlying data.

<p data-height="330" data-theme-id="0" data-slug-hash="ONQKNz" data-default-tab="js" data-user="embengineering" class="codepen">See the Pen <a href="https://codepen.io/embengineering/pen/ONQKNz/">react-hello-world-es6-reusability</a> by Emmanuel Morales (<a href="http://codepen.io/embengineering">@embengineering</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>

**It's Fast.**  React uses a virtual DOM to determine what changed in order to [reconcile](https://facebook.github.io/react/docs/reconciliation.html) and apply as few mutations as possible..

![React Virtual Dom](/assets/posts/2016-04-01/react-virtual-dom.png)

Take a look at this [example](http://codepen.io/embengineering/full/yOvmoW), where a collection of 1K items is being rendered in React, Angular, Knockout and Raw JS. Also, make sure you **run multiple times** for each technology in order to see the benefit of the algorithm.

![Performance Result Example](/assets/images/react-angular-knockout-performance-example.png)

Note that performance can increase even more by manually using the [Lifecycle Method](https://facebook.github.io/react/docs/component-specs.html#updating-shouldcomponentupdate) **shouldComponentUpdate()** and returning **false** when you're certain that the new information ([props](https://facebook.github.io/react/docs/transferring-props.html)) received will not require a component update.

## What?

React is not considered a framework, but a **JavaScript library** for building **User Interfaces**.  It's considered the **V** (view) in the **MVC** pattern.  It helps create modular web components that looks just like HTML, thanks to JSX.  [JSX](https://facebook.github.io/jsx/) is a JavaScript syntax extension created by Facebook *"to define a concise and familiar syntax for creating tree structures with attributes"*.

```xml
<Dropdown>
  A dropdown list
  <Menu>
    <MenuItem>Do Something</MenuItem>
    <MenuItem>Do Something Fun!</MenuItem>
    <MenuItem>Do Something Else</MenuItem>
  </Menu>
</Dropdown>
```

## Conclusion

React is not a framework, it's just a library to complement and support web development.  It's main function is to provide control of large UIs when data changes over time, improve performance and provide a modular solution, easy to debug and scale.

<iframe src="https://docs.google.com/presentation/d/1MNxPHJtJQZV_MgPRr4mgV3uVmlQu4Mpl-KrsHOhzw80/embed?start=false&loop=false&delayms=3000" frameborder="0" width="100%" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
