---
layout: post
title: "Test IIS Express Externally"
date: "2016-02-11"
thumbnail: "/assets/images/unable-to-connect-to-internet.gif"
---
![Post Thumbnail](/assets/images/unable-to-connect-to-internet.gif)

Are you a .NET developer building mobile web applications? Have you ever been frustrated by the fact that there's no easy way to enable IIS Express to accept connections from remote devices?
<!--more-->

Follow the following steps to make your life easier:

1. Download and install [ngrok](https://ngrok.com/download) or use its NPM wrapper (very handy if you're already using NodeJS) [ngrok npm](https://www.npmjs.com/package/ngrok)
2. Download and install [iisexpress-proxy](https://github.com/icflorescu/iisexpress-proxy) by using NPM and NodeJS `npm install -g iisexpress-proxy`
3. Open two (2) PowerShell (command prompt) windows
4. In one window, run `iisexpress-proxy 55708 to 3000` (assuming 55708 is the IIS Express port provided by VS)
5. In second window, run `.\ngrok.exe http 3000`
6. Open the public URL provided by `ngrok` (e.g http://somerandomnum.ngrok.io)

Hope it's easy for you as this steps above!
