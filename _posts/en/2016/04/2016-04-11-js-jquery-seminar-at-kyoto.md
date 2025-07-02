---
layout: post
title: Participated in a JavaScript / jQuery Event Seminar @ Kyoto
image: "https://raw.githubusercontent.com/noraworld/blog-content/main/js-jquery-seminar-at-kyoto/google_maps.png"
date: '2016-04-11 07:12:58'
tags:
- event
- development
---

I attended a JavaScript / jQuery event seminar held in Kyoto on April 10th.

### It's Been a While, Kyoto
Before introducing the event, let's talk about Kyoto. I'm currently living alone in the Kansai region because my university is located there. Although I don't live in Kyoto, it's not far away, so I can go there easily.

However, I rarely go out since I'm quite a homebody, so I seldom go to Kyoto. The last time I went there was in August last year, about eight months ago, when I went to karaoke with about five friends. I haven't gone there since.

This time, the event was held at a place called **Shijo Karasuma** in Kyoto. Place names in Kyoto can be quite tricky. Before googling, I pronounced it as **"karasumaru."** Please commend me for not reading it as **"torimaru."** I took the subway from Kyoto Station to get to Shijo Karasuma.

Kyoto is quite a bustling city. The area around Kyoto Station is spacious, and there are not only JR lines but also subways. When I arrived at Kyoto Station, I was confused about where to go and which line to take in which direction.

Of course, the event introduction site provided information on which subway line to take from Kyoto Station and which station to get off, but I first struggled to find where the subway platform was. It's a matter of checking the signs properly.

Even after reaching the underground, I couldn't locate the ticket gate for the line I wanted to take, so I asked a station staff member for directions. Then, when I tried to buy a ticket to Shijo, I found the route map convoluted, and it took me about five minutes to find the station I needed.

Finally arriving at Shijo Karasuma, I breathed a sigh of relief. But since I anticipated getting lost, I left home quite early and ended up arriving two hours before the meeting time, which was quite a struggle to kill time. Being a homebody really throws off one's sense of normalcy. I'm aware of it (but I’m not saying I’ll reflect on it←).

### Event Overview
The event lasted about three hours. We first studied JavaScript (JS), and after that, we mostly coded with jQuery.

Although it was an event, it was more like a study session rather than creating something new on our own. It wasn't just listening to talks; we also actually wrote code and deepened our understanding by seeing how it worked.

Just to introduce, JS is a programming language that adds interactivity to websites. For example, when you scroll down, an arrow appears, and clicking on it animates you back up to the top—that's JS. jQuery is a library that makes writing JS easier. As its catchphrase **"Write Less, Do More"** suggests, you can do a lot with a small amount of code.

As an aside, I learned about the origin of the name JavaScript at the event. It was initially called LiveScript, but it was renamed to JavaScript to ride on the popularity of Java at that time. The instructor suggested that this renaming might be one of the reasons JS became popular.

Even now, many people confuse Java and JavaScript, but they are not used in the same way. To someone who doesn't know Java and JS, it's like saying a melon is the same as melon bread, or India is the same as Indonesia. I wonder if this joke is quite famous?

### Basics of Syntax
Returning to the topic, the event started with the basics of JS syntax. Things like data types, variable definitions, conditional branching, loops, null/undefined, etc. I'm already capable of writing a fair amount of JS and know the general syntax of programming languages, so to be honest, it was a bit boring.

Just listening makes you sleepy, so we actually wrote programs to stay engaged. We wrote a program similar to World Nabetsu (I think he's now a rakugo storyteller called Katsura Sando?), where you output "Fizz" for multiples of 3 (≠ multiples of 5), "Buzz" for multiples of 5 (≠ multiples of 3), "FizzBuzz" for multiples of both, and the number itself for others.

### The Essence of JS is DOM
Calculations like variable declarations and addition/subtraction can be done in any language. It's not exclusive to JS. The essence of JS is its ability to use DOM. You can retrieve HTML elements on a page and change their colors or add new elements, which is a feature of JS.

After confirming the syntax, we studied how to use DOM by manipulating HTML on a page with JS. I already knew this part, so I listened leisurely while writing code.

### The Recommendation of jQuery
With jQuery, you can write code more easily than with JS.

```js
document.getElementById('element').style.color = 'orange';
```

versus

```js
$('#element').css('color', 'orange');
```

is shorter and simpler, right!

Moreover, with jQuery, you can use CSS properties and values as they are, so if you have done CSS before, you can write it quite easily. With the above jQuery code, it's effectively executing
```
#element {
    color: orange;
}
```
in JS, which is so cool!!

...Well, I received a lecture on such things (the lecturer wasn't as excited as I am though, haha). I use jQuery a lot myself (it's used on this blog too), so I understand well the usefulness of jQuery.

### Creating a Typing Game
This is where it got serious. We used everything we learned to create a typing game like this.

![Typing Game](https://raw.githubusercontent.com/noraworld/blog-content/main/js-jquery-seminar-at-kyoto/typing_game.png)

You first select a difficulty. The image shows easy mode. Once you press the button, the game starts, showing elapsed time and the string to type. If you type the string correctly in the input field, the next string appears immediately, and after answering five questions correctly, the game ends, and your time is displayed.

It's simple with a small codebase, but quite solid as a typing game. Tweaking the code a bit allows you to easily increase the number of questions or even set the number of questions yourself. It might be interesting to configure the amount of text to type too.

By the way, there are four difficulty levels: easy, normal, hard, and nightmare. This is what nightmare looks like.

![Typing Game](https://raw.githubusercontent.com/noraworld/blog-content/main/js-jquery-seminar-at-kyoto/typing_game_nightmare.png)

**J$%Z<** ... Truly a nightmare (meaningful). Words like "apple" or "orange" are easy because they are commonly typed, but random strings can be quite challenging. So, even though I found easy mode hard, adding symbols makes it chaotic... haha. Also, due to font issues, it's tough not being able to distinguish between vertical bar |, uppercase I, and lowercase l.

After making this, I briefly thought about adding new options and improving the design, but I probably won't do it because it's too much hassle←

~~I plan to publish the source code for this typing game on GitHub if I feel like it. If I feel like it!~~

[Update: 2016/4/16 (Sat)]

I published the source code on GitHub. In addition to the typing game, I also released the JS/jQuery syntax and Google Map codes I studied at this event. The code is quite messy since it's directly uploaded from the study session, but please forgive me, haha.

<a href="https://github.com/secondnoraworld/js-jquery-seminar" target="_blank">js-jquery-seminar</a>

### Embedding Google Maps
I created what you often see on company or store websites: an embedded Google Map alongside the company's (or store's) address. It was simple to create using the API provided by Google.

![Google Map](https://raw.githubusercontent.com/noraworld/blog-content/main/js-jquery-seminar-at-kyoto/google_maps.png)

The map shows Tokyo, but you can set any location initially displayed by configuring the latitude and longitude. You can also set the zoom level to display a more detailed map. The Google Maps API can do various other things too, but due to time constraints, we finished by displaying Tokyo.

Until now, I've played around with APIs like those from Twitter, Ghost (this blog), and NicoNico Douga, but it was my first time with the Google Maps API. I was surprised at how easy it was with such a small amount of code.

### Impressions
It initially started with basic syntax and familiar content, which was a bit dull, but making the typing game taught me the pure fun of game creation, and with Google Map, I thought I'd like to actively use various service APIs more.

This event was probably held for beginners. Though I enjoyed this event as it was, I would love to participate in more advanced events as well.
