---
layout: post
title: "An Engineer with 8 Years of Mac Experience Introduces Handy Mac Apps!"
description: "Introducing 14 handy Mac apps favored by an engineer with 8 years of Mac experience."
image: "https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/apps_thumbnail.png"
date: "2022-12-22 13:53:04"
tags: [
  "application",
  "development",
  "useful"
]
published: true
---

### About this article
This article was originally written when I was tasked with contributing a technical article at UUUM Co., Ltd. It was posted on the company-managed Hatena Blog, so I kept it private here (on my personal blog). However, as of September 22, 2024, upon revisiting, I found that the Hatena Blog article was no longer publicly accessible. Therefore, I have decided to publish it here instead. (You see, things like this are why I believe personal achievements related to the company should be personally managed. I'm glad I managed them properly on my end.)



### Introduction
Hello, I'm [aoki_k](https://github.com/noraworld), and today marks my 544th day[^3] at UUUM.

[^3]: As of December 26, 2022

As this is an engineering blog, I primarily write about technical topics, but I usually post general interest articles as well, and that's what I'm bringing to you today: "An Engineer with 8 Years of Mac Experience Introduces Handy Mac Apps!"

Being an engineer, I spend most of my time in front of a computer. I use a Mac for both work and personal tasks, and having had it for quite a while, I thought I could introduce various useful apps.

#### Aside
This is my first time writing for the UUUM Engineering Blog, but it's not my first appearance. Previously, I was featured in an article called [UUUM Engineer Desk Tour vol.1](https://system.blog.uuum.jp/entry/2022/03/22/110000).

Since then, I've moved and organized my belongings, so my physical environment has changed quite a bit from when that article was written, but that's a story for another time.



### Introduction of Apps
I've talked quite a bit upfront, so let's get into the introduction of the apps.

Note, I've excluded major ones like Google Chrome and LINE, as well as apps like Docker and Visual Studio Code that most engineers are aware of (or use), and those dedicated to specific services.

#### [Alfred 5](https://www.alfredapp.com)
![Alfred 5](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/alfred.png)

This is a resident app that lets you easily execute a wide range of operations, like launching applications, calculating, running specific commands, and more, with just a few keyboard strokes. It's essentially an enhanced version of Spotlight.

You can summon it with a shortcut regardless of where your mouse focus is or which app window is active. It's very convenient for quick searches, calculations, and automating tedious processes.

You can register snippets, allowing you to insert hundreds of lines of a template by typing the snippet name, catering to specifics you might need.

It does require some setup and getting used to, but it's guaranteed to significantly improve your work efficiency.

##### Recommendation Level
★★★★☆

##### Installation
###### GUI
[Alfred 5](https://www.alfredapp.com)

###### CLI
```shell
brew install --cask alfred
```



#### [Amphetamine](https://apps.apple.com/us/app/amphetamine/id937984704)
![Amphetamine](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/amphetamine.png)

A resident app that temporarily prevents your Mac from going to sleep.

It takes time to download heavy files, install packages, or build projects. You might want to do other tasks in the meantime, but if your Mac enters sleep mode automatically, it can disrupt processes.

Although you can adjust sleep settings in your Mac's System Preferences to prevent this temporarily, it's cumbersome to change settings every time, and you might forget to change them back, leaving your device always on.

With this app, you can click the icon in the menu bar or use a preset shortcut to override sleep settings with your predefined time. For example, if your Mac is set to sleep after 15 minutes but Amphetamine is set to an hour, it'll sleep an hour later when Amphetamine is active. You can also set it to never sleep temporarily.

It's not ideal to disable sleep or extend sleep time drastically just for occasions like this, as it can waste electricity, shorten your display's life, and drain your battery if running on one. This app allows you to conveniently adjust the sleep time according to your situation.

I don't use it as much now since Mac's performance has improved, requiring less time for installs and builds.

##### Recommendation Level
★★☆☆☆

##### Installation
###### GUI
[Amphetamine](https://apps.apple.com/us/app/amphetamine/id937984704)

###### CLI
```shell
mas install 937984704
```



#### [AppCleaner](https://freemacsoft.net/appcleaner/)
![AppCleaner](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/app_cleaner.png)

This app helps to delete associated files like settings and metadata when uninstalling applications.

Unlike Windows, Mac often lacks dedicated uninstallers for apps. Apps installed from the Mac App Store can be deleted similarly to iOS apps, but other apps need to be removed using Finder or CLI.

However, simply deleting the app won't remove related settings files or metadata, and their locations differ per app. 

By dragging the app icon from Finder to AppCleaner, it searches for all related files on your Mac, allowing you to select what to keep or delete.

I'm one of those who feel uneasy leaving associated files after removing an app, so I always use this app.

##### Recommendation Level
★★★☆☆

##### Installation
###### GUI
[AppCleaner](https://freemacsoft.net/appcleaner/)

###### CLI
```shell
brew install --cask appcleaner
```



#### [Bartender 4](https://www.macbartender.com)

| Before | After |
| --- | --- |
| ![Bartender 4 (before)](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/bartender_before.png) | ![Bartender 4 (after)](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/bartender_after.png) |

This resident app lets you hide icons of resident apps from the menu bar.

You can organize app icons in the dock to some extent, but the menu bar displays all active resident apps, which can get messy quickly. Having icons visible for resident apps that perform tasks without interaction can be distracting, especially if organization is important to you.

With this app, you can hide resident app icons from the menu bar. When needed, simply operate its icon to reveal them temporarily. Clock and control menu icons cannot be hidden.

Recently, I've set my menu bar to be hidden by default, so I don't see much benefit. Also, if cluttered icons don't bother you, this app might be unnecessary.

##### Recommendation Level
★★☆☆☆

##### Installation
###### GUI
[Bartender 4](https://www.macbartender.com)

###### CLI
```shell
brew install --cask bartender
```



#### [Be Focused Pro](https://apps.apple.com/us/app/be-focused-pro-focus-timer/id961632517)
![Be Focused Pro](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/be_focused_pro.png)

A Pomodoro app. Those who know this likely don't need further explanation.

In short, it’s a timer app that lets you set session duration, break times, and session counts for longer breaks. It automatically starts breaks and has a simple UI.

The Pomodoro Technique is well-known, leading to many apps, so it might be hard to say why you should choose this one, but after trying various apps, this is the one I've settled on.

##### Recommendation Level
★★★☆☆

##### Installation
###### GUI
[Be Focused Pro](https://apps.apple.com/us/app/be-focused-pro-focus-timer/id961632517)

###### CLI
```shell
mas install 961632517
```



#### [BetterSnapTool](https://apps.apple.com/us/app/bettersnaptool/id417375580)
![BetterSnapTool](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/better_snap_tool.png)

This resident app allows for easy resizing of windows to full-screen, half-screen, or a quarter, among other sizes.

Operations can be performed via shortcuts or by dragging the window to the screen edge, similar to Windows.

In standard Mac operation, you can double-tap the top of a window to maximize, but this doesn't always work, or only maximizes vertically. Resizing to half-screen isn't possible either.

With this app, dragging windows to the screen's edge performs intuitive resizing. You can also assign shortcuts.

I find it more straightforward than double-tapping, and the flexibility in window sizing and placement is invaluable.

##### Recommendation Level
★★★★★

##### Installation
###### GUI
[BetterSnapTool](https://apps.apple.com/us/app/bettersnaptool/id417375580)

###### CLI
```shell
mas install 417375580
```



#### [Browserosaurus](https://browserosaurus.com)
![Browserosaurus](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/browserosaurus.png)

A resident app that lets you choose the browser you open links with when clicked from non-browser apps.

Clicking HTTP/HTTPS links within non-browser apps like Visual Studio Code usually opens them in the default browser.

But you might want to use different browsers for different purposes, like using Chrome for work links and Safari for personal ones.

This app is technically seen by the OS as a browser. By setting it as your default, it launches instead of typical browsers whenever you click a link. It checks installed browsers and displays them in a small popup for you to choose which to open. Simply select your desired browser to open the link.

Ideal for those who juggle multiple browsers. I used to separate work and personal browsers but now, thanks to Chrome's profile feature, my usage has decreased.

##### Recommendation Level
★★☆☆☆

##### Installation
###### GUI
[Browserosaurus](https://browserosaurus.com)

###### CLI
```shell
brew install --cask browserosaurus
```



#### [Create File Menu](https://apps.apple.com/us/app/new-file-menu/id1064959555)
![Create File Menu](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/create_file_menu.png)

A tool that adds a new file creation item to Finder's menu bar and right-click menu.

On Windows, you can create text files from the right-click menu by default, but not on Mac. This tool enables that.

Although I mostly use the CLI for file operations, it’s handy for creating quick notes in directories when using Finder.

##### Recommendation Level
★★★☆☆

##### Installation
###### GUI
[Create File Menu](https://apps.apple.com/us/app/new-file-menu/id1064959555)

###### CLI
```shell
mas install 1440519779
```



#### [Google Japanese IME](https://www.google.co.jp/ime/)
![Google Japanese IME](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/google_japanese_ime.png)

The classic Japanese IME.

While many use Mac's default IME, it often does not impress during shared screen meetings.

Google Japanese IME, a Google product, offers precise conversions most of the time, minimizing input stress. Sometimes it errs, but overall, it provides a smooth typing experience.

Dictionary tools are available, letting you register frequently used terms for increased input efficiency, like converting "yor" to "よろしくお願いいたします".

Additionally, you can counteract misconversions by registering the incorrect and correct terms in the dictionary tool.

Some may dislike this, but I set "meaddo" to convert to my email address, avoiding manual typing errors and sending mishaps.

Personally, the most useful feature is the ability to always input half-width characters. By default, numbers/characters input in Japanese mode are full-width; setting them to half-width lets you input numbers/characters without changing modes, boosting typing efficiency.

You can choose half/full-width per symbol, keeping symbols like "、" and "。" full-width, while "+" and "=" are half-width.

I've used Google Japanese IME for years. Paid IMEs might be more advanced, but this meets my needs for free.

##### Recommendation Level
★★★★★

##### Installation
###### GUI
[Google Japanese IME](https://www.google.co.jp/ime/)

###### CLI
```shell
brew install --cask google-japanese-ime
```



#### [Karabiner-Elements](https://karabiner-elements.pqrs.org)
![Karabiner-Elements](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/karabiner_elements.png)

An app that allows keymap modifications.

I use a US-layout keyboard, which has its quirks when switching Japanese inputs.

By default, Ctrl + Space toggles input sources, but that's cumbersome given how frequently I switch. Also, I dislike toggle keys[^1] for their ambiguity.

[^1]: Toggle keys annoy me since they depend on state memory/recognition, resulting in likely errors, especially if you switch focus between operations or forget the state.

On a US layout, the most convenient top-left key (near the left pinky) is Caps Lock — also a key I dislike for its toggle nature. Such a prime spot for an unnecessary key is inefficient.

This app resolves such issues. It allows for key mapping changes and specific actions for solo presses or repeated key presses, among many other complex configurations. It’s handy for environments using both JIS and US keyboards by allowing key-specific changes.

Here are my settings:

* Fn → Escape
    * Frequently used but not convenient at the far top-left
* Caps Lock → Ctrl
    * Emacs-like key bindings standard in Mac, requiring frequent Ctrl use
* Left Command (solo press) → 英数
    * JIS layout-like mapping
* Right Command (solo press) → かな
    * JIS layout-like mapping
* Swap colon and semicolon
    * I use colon more often in script languages like Ruby
* Command + Q (double-press) → Command + Q (single-press)
    * Prevents accidental app closing

Fn and Caps Lock remain unused and are unnecessary.

By mapping 英数 and かな as distinct keys, they are no longer toggle keys. Pressing Left Command for alphabets/numbers and Right Command for Japanese input ensures zero error.

This app is essential for me. Frankly, it’s so ingrained that my work would be impossible without it.

An amusing aside: REALFORCE, known for high-end keyboards, includes a keycap for Caps Lock to Ctrl change — they understand users well.

##### Recommendation Level
★★★★★

##### Installation
###### GUI
[Karabiner-Elements](https://karabiner-elements.pqrs.org)

###### CLI
```shell
brew install --cask karabiner-elements
```



#### [KeyboardCleanTool](https://folivora.ai/keyboardcleantool)
![KeyboardCleanTool](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/keyboard_clean_tool.png)

An app that disables keyboard operations temporarily.

As its name suggests, it's helpful for cleaning your keyboard. You can disconnect external keyboards, but cleaning the built-in one can trigger unintended responses. Powering down is an option, but it's unwieldy when cleaning is needed.

By using this app, you can disable keys temporarily and clean the built-in keyboard without random inputs.

Note some keys like fn aren't disabled, and the MacBook's trackpad remains responsive.

This isn't something frequently required, so its recommendation is low. But it's useful to avoid errors during cleaning if you’re using the built-in keyboard.

##### Recommendation Level
★☆☆☆☆

##### Installation
###### GUI
[KeyboardCleanTool](https://folivora.ai/keyboardcleantool)

###### CLI
```shell
brew install --cask keyboardcleantool
```



#### [Lunar](https://lunar.fyi)
![Lunar](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/lunar.png)

This app makes it easier to adjust screen brightness and contrast.

Adjusting brightness on external monitors is cumbersome; brightness keys affect only the Mac screen.

With this app, you can adjust external monitor brightness via keyboard or menu bar. You can set shortcuts for maximum/minimum brightness and contrast and use a menu bar slider for precise brightness.

I manually adjust brightness according to room lighting, but auto-brightness based on Mac sensors or gradual changes from sunrise to sunset are also available.

I find it invaluable for fine-tuning screen brightness according to room lighting.

##### Recommendation Level
★★★★★

##### Installation
###### GUI
[Lunar](https://lunar.fyi)

###### CLI
```shell
brew install --cask lunar
```



#### [Noizio](https://noiz.io)
![Noizio](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/noizio.png)

A resident app that offers various ambient sounds, noise, and frequency-specific sounds.

Sounds range from environmental like birds and rain, to noises like trains and white noise, to special sounds like alpha and beta waves, including unique ones like a heartbeat.

You can mix multiple sounds, adjust individual sound volumes, and save your favorite combinations. Shortcuts enable quick on/off toggling.

As an HSP (Highly Sensitive Person), I find minor noises distracting or sleep-disrupting, so I use this app for ambient sounds almost always, except when out or in the shower. It’s vital for my focus and sleep.

I can't concentrate on work with music since it splits my focus, but ambient sounds provide consistent, repetitive noise that doesn’t shift my attention, making it incredibly useful.

##### Recommendation Level
★★★★☆

##### Installation
###### GUI
[Noizio](https://noiz.io)

###### CLI
```shell
mas install 928871589
```



#### [Witch](https://manytricks.com/witch/)
![Witch](https://raw.githubusercontent.com/noraworld/blog-content/main/useful-mac-apps/witch.png)

A resident app for keyboard-based application switching. It's a beefed-up version of Command + Tab.

Command + Tab is useful, but small annoyances arise over time, like Finder[^2] intrusions or excluding certain apps.

Witch provides otherwise lacking features like excluding specific apps and shortcut changes. It can even overwrite Command + Tab.

My favored feature is switching between windows. The standard system allows for setting a shortcut for window switching but cannot reopen docked windows or display a central menu. It changes windows instantly.

Witch combines both application and window switching, similar to Windows' Ctrl + Tab, showing all windows in one menu for selection.

[^2]: Note, Finder's intrusiveness can be [addressed by closing Finder](https://zenn.dev/noraworld/articles/how-to-kill-finder).

It’s invaluable for clearing picker cluttered by temporary settings windows, solved entirely with this app.

##### Recommendation Level
★★★★★

##### Installation
###### GUI
[Witch](https://manytricks.com/witch/)

###### CLI
```shell
brew install --cask witch
```



### Conclusion
I've introduced 14 apps; what do you think?

Having used a Mac for years, I've often sought apps to solve inconvenience and found useful ones, thinking I'd have more to introduce.

Yet, after listing installed apps, I realized I use fewer frequently. Over time and through various environments, only truly necessary apps remain.

Everyone's preferences and needs differ, so not every app here will suit everyone. But if any catch your interest, I'm glad to have written this article.

This was a break from technical articles, but if you're interested, I often post technical stuff on [Zenn](https://zenn.dev/noraworld), so feel free to check it out.

Until next time!
