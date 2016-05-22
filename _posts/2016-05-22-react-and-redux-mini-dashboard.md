---
title: "Getting Started with React And Redux"
layout: post
date: "2016-05-22"
thumbnail: "{{site.baseurl}}/assets/images/writing-react-component.gif"
---
![Post Thumbnail]({{site.baseurl}}/assets/images/writing-react-component.gif)

Let's create a small application using React and Redux...
<!--more-->

>*“There are two ways of constructing a software design: One way is to make it so simple that there are obviously no deficiencies, and the other way is to make it so complicated that there are no obvious deficiencies. The first method is far more difficult.” -C.A.R. Hoare (British computer scientist, winner of the 1980 Turing Award)*

# Introduction

Before starting, I would like to mention a basic list of technologies I considered in my project. The list can be longer if I get into details. Let's expand this topic in a separate post. For now this is the core of the project.

1. [Webpack](https://webpack.github.io/) (Module bundler)
2. [SASS](http://sass-lang.com/) (Mature CSS extension language)
3. [React](http://facebook.github.io/react/) (A JavaScript library for building user interfaces)
4. [Google Material Design](https://getmdl.io/) (The official Material Design library that doesn't rely on JavaScript frameworks)
5. [React Hot Loader](http://gaearon.github.io/react-hot-loader/) (Tweak React components in real time)
6. [Redux Dev Tools](https://github.com/gaearon/redux-devtools) (A live-editing time travel environment for Redux)

Building web applications with these technologies require us to have a dependency on Node and NPM.  Let's make sure we have them install and configured:

1. Download and install [NodeJS](https://nodejs.org/en/download/)
3. Verify the installation by using `node -v` and `npm -v`

# How to get started?

To get started with the step-by-step exercise, make sure you are able to run the development environment:

1. Clone the following repository [embengineering/react-redux-starting-kit](https://github.com/embengineering/react-redux-starting-kit.git)
2. Switch to directory `cd react-redux-starting-kit`
3. Install NPM dependencies `npm install`
4. Run in development mode `npm run watch`

If you haven't decided on a good text editor for writing your React application, I'll recommend to download [Atom](https://atom.io/).  For a nice experience working with React and ES6 in Atom, I recommend installing few extensions to give "super powers" to Atom. You can install them with one line from your terminal:

{% highlight bash %}
apm install auto-detect-indentation highlight-selected pigments react sort-lines tab-switcher todo-show open-recent minimap minimap-highlight-selected multi-cursor-plus
{% endhighlight %}

# Re-Build a Mini Dashboard (The Right Way)

If you were able to accomplish the "get started" section, you should see a basic dashboard.  The dashboard is using only one React component and hard-coded data.  Data is passed to the React component using `props` from the `~/main.js` (entry point).  

The following step-by-step tutorial will help you build a better version of the dashboard: scalable, reusable and to easy to maintain.

In order to keep this tutorial short, I'll guide you step-by-step using my commits from [Github](https://github.com/embengineering/react-redux-starting-kit/commits/starting-point).

## Refactor current dashboard with stateless components

[Step 1:](https://github.com/embengineering/react-redux-starting-kit/commit/80ce25506d71929e1d752e6d64d11c41094f8a5d)  Create `~/components/Card.jsx` component and refactor `StaticMiniDashboard.jsx` to use it.

[Step 2:](https://github.com/embengineering/react-redux-starting-kit/commit/aeff4303ce6f1668011796f087b2429e70d64b54)  Create `~/components/WelcomeCard.jsx` component and refactor `StaticMiniDashboard.jsx` to use it.

[Step 3:](https://github.com/embengineering/react-redux-starting-kit/commit/1e24b1a34bd76c82f757ff34aed8177070c0989b)  Create `~/components/CardList.jsx` component and refactor `StaticMiniDashboard.jsx` to use it.

[Step 4:](https://github.com/embengineering/react-redux-starting-kit/commit/1222939575742723b100c84da65df7fe23a6d972)  Create `~/containers/WelcomeCardContainer.jsx`.

[Step 5:](https://github.com/embengineering/react-redux-starting-kit/commit/c7fcd02025847b655c6b605a07449bce50384341)  Create `~/containers/CardListContainers.jsx`.

## Add [Redux](http://redux.js.org) for organization and scalability

**Note:  At this point there will be no changes in the UI, just in the architecture.**

[Step 6:](https://github.com/embengineering/react-redux-starting-kit/commit/9d3d9a5ed635e54d334a4b0cf85aa863a067917e)  Define initial state '~/initialState.js'.

[Step 7:](https://github.com/embengineering/react-redux-starting-kit/commit/491aab1bc13b80b039b194125ccc280eae4abed4)  Create `~/actions/miniDashboardActions.js` and add constants to `~/constants.js`.

[Step 8:](https://github.com/embengineering/react-redux-starting-kit/commit/688e59f7532f90a20537ddbc27bb710f4ebf0d8b)  Create `~/reducers/welcomeCardReducer.js`.

[Step 9:](https://github.com/embengineering/react-redux-starting-kit/commit/a37732ff1403ba8594ef88f1c097fdc1002fc271)  Create `~/reducers/cardListReducer.js`.

[Step 10:](https://github.com/embengineering/react-redux-starting-kit/commit/edc3eb5d770ef4c430e9f5494566236aa8d56731)  Update `~/reducers/index.js` to combine reducers.

## Update the application to support Redux

[Step 11:](https://github.com/embengineering/react-redux-starting-kit/commit/30aeef100b7a089f9a49d5b4de02aed36cfeb496)  Rename `~/components/StaticMiniDashboard.jsx` to `~/components/MiniDashboard.jsx` and refactor to use containers.

[Step 12:](https://github.com/embengineering/react-redux-starting-kit/commit/0e5f1387e8fd081971f7756c892eed65b6750fed)  Update '~/main.js' to finalize the implementation of Redux.

[Step 13:](http://localhost:8080/)  Test http://localhost:8080/.


## Integrate [Firebase](https://www.firebase.com/) As Your Back-End Service (Optional)

[Step 14:](https://github.com/embengineering/react-redux-starting-kit/commit/c2a2d249490195630dde77b0a53c7b13cf394b27)  Create a valid JSON file with test data from `~/main.js` (e.g. `~/data.json`).

Step 15:  Sign-up or sign-in to Firebase](https://console.firebase.google.com/) using your Google account.

Step 16:  Create new database 'your-custom-name-db'.

Step 17:  Import `~/data.json` JSON file into Firebase.

[Step 18:](https://github.com/embengineering/react-redux-starting-kit/commit/9c397ab93f5acb4b1067a49be7e5bb23f142a1ba)  Update `~/actions/miniDashboardActions.js` to listen to your back-end service.

[Step 19:](https://github.com/embengineering/react-redux-starting-kit/commit/13aeb809458067099f88d1cf30fae29a14508261)  Update `~/main.js` to remove hard-coded data and start listening to new methods.

[Step 20:](http://localhost:8080/)  Test http://localhost:8080/.
