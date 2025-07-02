---
layout: post
title: I Have Updated My Portfolio @ ver 2
date: '2016-11-23 03:49:00'
tags:
- info
- development
---

I updated my portfolio on the 21st, the day before yesterday.

[noraworld.jp](https://noraworld.jp)

Actually, I've renewed my portfolio [before](https://blog.noraworld.jp/renewal-noraworld/), so this time it's version 2.

I was quite satisfied with the previous portfolio, but eventually, I got bored with it as time passed, and it wasn't compatible with smartphones or tablets, so I decided to create a new one. This time, it supports both smartphones and tablets.

### Concept
I wanted my portfolio to be simple yet stylish, so I extracted only the minimal necessary information and summarized it neatly. I added a slider animation to give it a bit of a stylish touch.

Also, around the time I started creating my portfolio, I was eager to try my hand at graphics work, so I used p5.js, a JavaScript graphics library. While it's fixed on smartphones, when accessed from a PC, the gallery that's randomly drawn changes. I have only prepared two so far, but if you're interested, please give it a try.

### Technical Talk
This time, I created it with "No jQuery and No Framework." In the past, I always relied on jQuery when writing JavaScript, and on frameworks when writing server-side code, so I wanted to see if I could create it without relying on them at all, and I took on the challenge.

Reflecting on trying "No jQuery and No Framework," I realized once again just how great jQuery and frameworks are.

There's a culture in the world that dislikes jQuery, but that's only when using single-page applications or data binding. I heard that jQuery is still advantageous when doing animations with JavaScript, and I got to experience that this time. On the flip side, by not relying on jQuery, it was a good opportunity to learn about the functions implemented by JavaScript for animations and browser differences.

As for server-side frameworks, I implemented only file delivery this time, so it wasn't that difficult. However, while working on the front-end, there were instances where I wanted to differentiate between the files delivered to smartphones and PCs, and at those times, I wanted to dynamically change the contents of HTML. I also felt like I wanted to use a template engine, so having a framework in place for such processes could make it easier to implement, which made me wonder if using a framework just for front-end development might be preferable.

Like the theme of this blog, the code for my portfolio is also available on GitHub, so if you're interested, feel free to take a look. [noraworld.jp - My portfolio](https://github.com/noraworld/noraworld.jp)

### Conclusion
I think I'll continue to renew my portfolio in the future, but for a while, I plan to publish it with this design. Well, since I'm not a designer, it's not something I will update frequently in the first place.

There may not be much to see, but if you're interested, please take a look!
