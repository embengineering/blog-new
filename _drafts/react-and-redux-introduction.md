---
title: "Getting Started with React And Redux"
layout: post
date: "2016-04-25"
thumbnail: "{{site.baseurl}}/assets/images/building.png"
---
![Post Thumbnail]({{site.baseurl}}/assets/images/building.png)

Let's create a small application using React and Redux...
<!--more-->

>*“There are two ways of constructing a software design: One way is to make it so simple that there are obviously no deficiencies, and the other way is to make it so complicated that there are no obvious deficiencies. The first method is far more difficult.” -C.A.R. Hoare (British computer scientist, winner of the 1980 Turing Award)*

## Introduction

There are many "starting" projects to help you get started with these technologies.  It's worth it to mention that I was inspired from few of them.  However, many were too complicated or lack on the technologies I was aiming to use.

Before starting, I would like to mention a basic list of technologies I considered in my project. The list can be longer if I get into details. Let's expand this topic in a separate post. For now this is the core of the project.

1. [Webpack](https://webpack.github.io/) (Module bundler)
2. [SASS](http://sass-lang.com/) (Mature CSS extension language)
3. [React](http://facebook.github.io/react/) (A JavaScript library for building user interfaces)
4. [Google Material Design](https://getmdl.io/) (The official Material Design library that doesn't rely on JavaScript frameworks)
5. [React Hot Loader](http://gaearon.github.io/react-hot-loader/) (Tweak React components in real time)
6. [Redux Dev Tools](https://github.com/gaearon/redux-devtools) (A live-editing time travel environment for Redux)

Building web applications with the technologies mentioned above, require us to have a dependency on Node and NPM, let's make sure we have them install and configured:

1. Download and install [NodeJS](https://nodejs.org/en/download/)
3. Verify the installation by using `node -v` and `npm -v`

## How to get started?

To get started with the real exercise, let's work on additional steps:

1. Clone the following repository [embengineering/react-redux-starting-kit](https://github.com/embengineering/react-redux-starting-kit.git)
2. Switch to directory `cd react-redux-starting-kit`
3. Install NPM dependencies `npm install`
4. Run in development mode `npm run watch`

If you haven't decided on a good text editor for writing your React application, I'll recommend to download [Atom](https://atom.io/).  For a nice experience working with React, ES2015 in Atom, I recommend installing few extensions to give "super powers" to Atom. You can install them with just one line:

{% highlight bash %}
apm install auto-detect-indentation highlight-selected pigments react sort-lines tab-switcher todo-show open-recent minimap minimap-highlight-selected multi-cursor-plus
{% endhighlight %}

## Build a Mini Dashboard (The Right Way)
1. Create `Card.jsx` into `/components`.

{% highlight jsx %}
import React from 'react';

const Card = ({className, imgUrl, title, msg}) => (
  <div className={className}>
    <div className="mdl-card__title"
      style={{background: 'url(' + imgUrl  + ') center/cover'}}>
      <h2 className="mdl-card__title-text">{title}</h2>
    </div>
    <div className="mdl-card__supporting-text">{msg}</div>
  </div>
);

export default Card;
{% endhighlight %}
