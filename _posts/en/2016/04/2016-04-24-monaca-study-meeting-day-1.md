---
layout: post
title: Attended an App Development Platform Monaca Study Session @ Day 1
image: "https://raw.githubusercontent.com/noraworld/blog-content/main/monaca-study-meeting-day-1/monaca_logo_1.png"
date: '2016-04-24 07:24:04'
tags:
- development
- event
---

On the 22nd (Friday), I was invited by members of a computer club to join an app development study session, so I participated.

This time, we developed using services called <a href="https://ja.monaca.io/" target="_blank">Monaca</a> and <a href="http://mb.cloud.nifty.com/" target="_blank">Nifty Cloud mobile backend</a>.

### What is Monaca?
![Monaca](https://raw.githubusercontent.com/noraworld/blog-content/main/monaca-study-meeting-day-1/monaca_app.png)

Monaca is a hybrid app development platform that can be developed in HTML5. Normally, to create an iPhone (iOS) app, you develop using a development environment called XCode with a language called Swift, and to create an Android app, you develop using a development environment such as Android Studio or Eclipse, mainly using Java.

iOS apps and Android apps are created in separate development environments and languages, but with Monaca, you can create apps that run on both iOS and Android using only HTML5 (HTML, CSS, JavaScript, etc.).

If you know HTML5, you can start creating right away, and since you don't have to create separately for iOS and Android, you can create apps very easily.

Moreover, since Monaca is a service that allows development on the web, it is a big feature that there is no need to install any special apps. Particularly with XCode, since it can only be used on Mac (not usable on Windows), it's groundbreaking that even people who don't own a Mac can develop iOS apps.

I don't know much about Monaca either, but I heard that you can also release apps created with Monaca to the App Store or Google Play (of course, you need to pass a review).

### What is Nifty Cloud mobile backend?
This is a service that allows you to use a database to manage user IDs, etc., for free. All methods for using the database are provided, and all you have to do is follow them and enter the given API Key to easily use the database.

Even with the free version, you can have up to two million accesses, which is a fairly generous service, making it very convenient.

### The App We Are Creating
The app we are creating this time is a game where you tap at the right timing to keep expanding circles within the frame, similar to ripples.

When you enter your user ID and password on the login screen and register as a member, the game screen displays, allowing you to play the game. When you log out, the login screen appears again, making it a simple app.

### Current Progress
This app is still unfinished. Currently, we have a login screen displayed, and when logged in, the page transitions. We've implemented it so that when you press the login button, it references the database and logs in if the password matches, prompts a reentry if it is incorrect, and registers a new user ID if new.

Here is the login page look↓

![CircleTapGame Login Page](https://raw.githubusercontent.com/noraworld/blog-content/main/monaca-study-meeting-day-1/login_screen.png)

Once you log in correctly, the page transitions↓

![CircleTapGame Logout Page](https://raw.githubusercontent.com/noraworld/blog-content/main/monaca-study-meeting-day-1/logout_screen.png)

You can create all input forms and login buttons just with HTML. On a smartphone, a tap corresponds to a click on a computer, so when writing JavaScript, you can also handle tap events with a click event. As someone just starting with the web, it was very intuitive and easy to understand.

### To Continue on the Second Day
We're creating a game, yet the game screen isn't done at all, haha. And though I've set it up so "Log Out" appears after logging in to allow you to log out, there is a bug where if you're logged in on multiple devices, you can't log out.

The person who hosted the study session plans to host another one on the second day, so on the second day, we plan to fix it so that logging out is possible even when using multiple devices, and create actual game screens and games on the page that now displays only the word "Log Out."

### What's Amazing About Monaca
I used Monaca for the first time this time and want to summarize what I found amazing.

* You can create both iOS and Android apps at the same time
* It's easy to create because it's just HTML5
* You can start easily because no special software is needed
* You can create iOS apps even without owning a Mac
* **You can check on the actual device in real-time**

The first four points are as explained initially. Besides those, the most impressive point was that **you can check in real-time**.

When you edit on the computer and save the file, the changes are reflected in real-time, and you can check them on the Monaca app on your smartphone. There's no need to press the refresh button, and about 1-2 seconds after saving on the computer, the smartphone automatically reloads, displaying the new screen.

Furthermore, there's no need to connect the computer and smartphone with a code; as long as they are both connected to the internet, you can check in real-time, allowing for very smooth development.

### Impressions of Using Monaca
While it might be hard to instantly create a full-fledged app like those in the store using just Monaca, I felt it is a sufficiently high-quality service if the goal is to also learn while creating light apps!

It's recommended for those who don't want to take a lot of time studying smartphone app development but want to try making a simple smartphone app.

* <a href="https://ja.monaca.io/" target="_blank">Monaca</a>
* <a href="http://mb.cloud.nifty.com/" target="_blank">Nifty Cloud mobile backend</a>
