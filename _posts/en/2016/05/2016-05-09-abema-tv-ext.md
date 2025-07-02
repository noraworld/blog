---
layout: post
title: Chrome Extension for AbemaTV That Lets Comments Flow Like on Nico Nico Douga
image: "https://raw.githubusercontent.com/noraworld/blog-content/main/abema-tv-ext/abematv_niconico_comment.png"
date: '2016-05-09 04:57:13'
tags:
- useful
- service
---

Some time ago, I discreetly integrated Google Analytics into this blog. As I was checking what search terms people from search engines were using, I found that most of them were related to AbemaTV extensions, like "abematv chrome extension," "abematv chrome," and "abematv extension."

So, my curiosity piqued, I decided to look for AbemaTV extensions, and I found someone who created a really impressive extension. I'm a bit excited, but I'd like to introduce it.

### What kind of extension is it?
A popular video site that everyone knows, "Ni○ ni○ Video," is famous for its system where comments flow across the video screen, right? Well, there's an extension that makes this possible on AbemaTV too!

<a href="https://chrome.google.com/webstore/detail/bemtv-ext/jgbkfdjdcbohgenpccfgldadaofnfknl?hl=ja&gl=JP" target="_blank">\_bem\_tv ext - Chrome Web Store</a>

I actually just noticed and installed it myself, and it turns out it was only published on the Chrome Web Store yesterday.

Before that, the source code was publicly available, and you had to download and load it yourself, but now that it's on the store, anyone can easily download it from there!

By the way, it seems that currently, it's only supported by Google Chrome, and hasn't been packaged for Firefox yet.

### Comments flow like on a familiar video site!
![AbemaTV Nico Nico Style](https://raw.githubusercontent.com/noraworld/blog-content/main/abema-tv-ext/abematv_niconico_comment.png)

↑ As you can see, the comments on AbemaTV flow over the video like this.

This screenshot was taken around midday (1 PM), so there are few comments, but during anime broadcasts at night, a large number of comments flow, making it very lively.

AbemaTV reflects comments in real time, so you can enjoy watching them, but if you don't click the update button, the comments won't be displayed, which is rather inconvenient. However, with this extension, you can enjoy the comments without that hassle, making it really fun!

You can also change the speed at which the comments flow, allowing you to watch them at your preferred pace.

### Many other useful features
Even just this feature is quite convenient, but this extension boasts many other useful features as well. Here's a quick rundown.

* Resize to prevent cutting off edges of the video to fit the window size
* Double-click to switch to full screen
* Send comments with Enter
* Hide old comments (removing the scroll bar from the comment section)
* Flow comments using CSS animation
* Remove specified words from flowing comments (such as emoticons, consecutive words, etc.)
* Block comments containing specified words from flowing
* Adjust the position of the comment input field downward, reverse the order of comment lists, scroll down
* Remove the post button, single-line the input field
* Prohibit program navigation with the mouse wheel
* Display the remaining time of the program near the comment input field
* Always display the comment section

The feature I wanted most before discovering this extension was the ability to adjust the window size. Currently, AbemaTV cuts off the bottom of the video if it's not in full screen. Tickers cut off because the window size isn't right, so having a feature that adjusts it perfectly is very satisfying.

The AbemaTV comment input field is multi-line, but line breaks are ignored when posting, so there's a neat feature to make it single-line. (This might not be the intended purpose, though...) There's also a function that allows you to send the comment with the Enter key instead of breaking lines, addressing a bothersome issue.

### A few bugs present
As this extension is newly released, there are a few minor bugs—

At least in my environment, the comments didn't flow in the familiar video site style unless I kept the comment section always displayed on the right side.

You can set the extension to always display the comment section from the start, so it's not very inconvenient, but it would be great if the comments could flow over the video without displaying the comment section.

Moreover, AbemaTV displays the latest comments at the top, and while the extension allows you to set the latest comments to the bottom, the comments didn't flow unless I kept it set to the bottom.

Occasionally, the comments stop flowing when switching channels, but refreshing resolves this.

However, since it's newly released, I hope it improves steadily over time.

Additionally, the source code for this extension is available on GitHub, so if I'm capable of reading the code and making corrections, I'd love to fix the above issues and send a pull request.

<a href="https://github.com/nakayuki805/AbemaTVChromeExtension" target="_blank">AbemaTVChromeExtension - GitHub</a>

### In summary
I downloaded this extension (or rather, the source code before its release) just yesterday, thinking I'd definitely like to introduce it. When I checked the README, it had just been released, so I hurriedly started writing the article.

I had also created and released a <a href="https://chrome.google.com/webstore/detail/%E3%83%8B%E3%82%B3%E3%83%8B%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%80%E3%83%BC/baiinihbicmkmkhblpboabkckgheaahm?utm_source=chrome-ntp-icon" target="_blank">Nico Nico Douga extension</a> between last year and this year, so I was considering creating a similar extension for AbemaTV (mainly to adjust the window size), and I discovered someone had created a more advanced extension, which is a bit frustrating. However, I think it’s better to support this extension if there are features I’d like to incorporate, rather than creating a new one.

From now on, I’ll continue enjoying AbemaTV along with YouTube and Nico Nico Douga.

* <a href="https://chrome.google.com/webstore/detail/bemtv-ext/jgbkfdjdcbohgenpccfgldadaofnfknl?hl=ja&gl=JP" target="_blank">\_bem\_tv ext - Chrome Web Store</a>
* <a href="https://github.com/nakayuki805/AbemaTVChromeExtension" target="_blank">AbemaTVChromeExtension - GitHub</a>
