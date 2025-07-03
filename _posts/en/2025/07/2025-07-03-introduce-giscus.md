---
layout: post
title: "Changed the Comment System from Disqus to giscus"
author: [
  "noraworld"
]
description: "I have been using Disqus since the blog's inception, but I have recently switched to giscus. I would like to inform you about this change and discuss the reasons behind it."
image: "https://noraworld.github.io/box-ivysaur/2025/07/03/13d31b90edcf21030d2e46394593eee5.png"
date: 2025-07-03 19:50:00 +09:00
tags: [
  "info"
]
published: true
---

### Transition
[This blog began with a CMS called Ghost](start-blog) and later [transitioned to Jekyll (GitHub Pages)](ghost-to-jekyll). [Disqus was introduced as a comment system fairly early on when I started the blog with Ghost](import-disqus). Unlike all-in-one CMS like WordPress that come with a built-in comment feature, Ghost, being new at the time and in its 0.x version, did not have a comment feature implemented[^ghost].

[^ghost]: I wonder if it has been implemented now? Since moving to Jekyll, I haven't followed the updates at all, so I haven't researched how it has evolved since.

And because GitHub Pages is a static site hosting service, it obviously can't have a built-in comment function. So, just like with Ghost, a comment system like Disqus was necessary, and I carried it over. Well, even though I say I carried it over, after moving to Jekyll, the frequency of updates drastically decreased, and I hadn't implemented it for a long time. More recently, as my motivation to update the blog increased, I reintroduced it, which would be more accurate.

However, as part of a blog overhaul this time, the comment system was also migrated from [Disqus](https://disqus.com/) to [giscus](https://giscus.app/). It has already been implemented, and you can view and post reactions and comments from the bottom of this article.

![Comment Section](https://noraworld.github.io/box-ivysaur/2025/07/03/6e51a4e72b7614047eda64f2ce17b988.png)

### The Trigger
The trigger was [migrating the theme (design) to Chirpy](support-english-entries). The comment systems supported by default vary depending on the theme, and with the previously used [Minima](https://github.com/jekyll/minima), I think only Disqus was supported. Well, even if the theme didn't support the corresponding comment system, it could be used with any theme by embedding a script tag manually. However, since [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) officially supports giscus, I looked into it and thought it seemed good, which led to its adoption. I had actually seen websites (mainly blogs) implementing this comment system before, but it was the first time I learned it was giscus.

In addition to Disqus, Chirpy supports [utterances](https://utteranc.es/) and giscus, and this giscus is the comment system introduced this time, which uses GitHub Discussions to manage comments. Incidentally, utterances use GitHub Issues for its system, and it seems that giscus was inspired by this. Although giscus came later, it is actively developed, popular, and allows for customization, such as categorizing comments through GitHub Discussions, so I decided to adopt giscus.

Well, since Disqus is also supported, continuing to use Disqus would have been fine, but being deeply immersed in the GitHub ecosystem myself, the charm of managing everything, including comments, on GitHub could not be beaten. Naturally, giscus requires a GitHub account to leave comments, which might be a bit of a burden for non-engineers. This is because non-engineers are likely not to use GitHub frequently and therefore might not have an account, and excluding the engineering demographic, Disqus is generally more widely utilized.

Creating a GitHub account just to leave comments can be a psychological burden for some, thus I do have concerns that the barrier might become narrower. Additionally, not all articles in this blog are targeted at engineers, and I am actually considering sharing it with online English conversation teachers. With that in mind, Disqus seemed more user-friendly, but nonetheless, the allure of managing comments on GitHub won out. Well, it's my blog, so I think it's okay for it to be about self-satisfaction as well.

### Out of the Box
Before writing this article, I had already completed the implementation, temporarily posting this article empty as a trial to check the functionality with a test comment. It was confirmed to be working without issue.

The installation was extremely simple. As long as one is accustomed to using the GitHub service itself, it is easy to install even for non-engineers. This truly embodies "out of the box." The design philosophy of being immediately usable without requiring complex setup is personally very appealing, which is another happy point.

For installation, I referred to [Introducing a Comment System to Hugo using giscus | Konsome Engineering](https://engineering.konso.me/articles/hugo-comments-with-giscus/), but honestly, the explanation on the [installation page](https://giscus.app/) seems sufficient. The previously mentioned article suggests setting the GitHub Discussions category to `Open-ended discussion`, but I believe `Announcement` is better. This is because `Open-ended discussion` allows anyone to create discussions, which could risk cluttering it. With `Announcement`, only maintainers or admins can create, making it safer. In fact, the giscus installation page also recommends using `Announcement`.

The article above uses Hugo, another static site generator, but the installation process is basically the same as with Jekyll. If the theme supports giscus, it can be configured accordingly, and if not, the script tag generated on the installation page can be embedded to place it at the bottom of articles. Using Chirpy, it can be easily installed by [modifying `_config.yml` like this](https://github.com/noraworld/blog/commit/311bde396e89637fcb39c2d051716ea8e09f5ebc). Of course, IDs, etc., need to be changed to suit the individual environment.

### Struggling with Repository Naming
Although the implementation itself can be done in about an hour, it took almost a week from deciding to implement to actual implementation. The reason was pondering a suitable name for the new repository to be created.

Initially, or rather at a stage where I still didn’t fully grasp the workings of giscus, I thought it would be sufficient to implement this on the [blog repository](https://github.com/noraworld/blog). However, in the future, when introducing it to technical articles, it will also need to be implemented there. While this is fine, I thought it might be more streamlined to create a separate repository to manage comments, unifying comments from the blog and technical articles where giscus has been implemented. This notion was actually mentioned in the previous article.

Therefore, it was necessary to create a new repository, but deciding on a repository name was quite challenging, which eventually took me almost a week. I spent that entire time contemplating it. Being somewhat of a perfectionist or indecisive in such intricate details is one of my weaknesses, but considering these names will be used long-term, I didn't want to decide arbitrarily.

#### Naming Candidates
There were various candidates. Among the strong contenders were:

* `rapport`
* `affinity`
* `echo`
* `chamber`
* `threads`
* `agora`
* `whisper`

`rapport` conveys [a relationship where preferences and feelings are in sync](https://eow.alc.co.jp/search?q=rapport) and also signifies a sense of trust. Viewing comments as a drive to continue with the blog rather than a place for debate, hoping for supportive comments or those merely acknowledging the blog, `rapport` didn’t seem bad at all. In fact, it was a strong candidate in my mind until mid-selection. But from the perspective of a place managing comments, it seemed a bit too abstract, so it was ultimately rejected. `affinity` was rejected for similar reasons.

Next, considering `echo`, in Japanese, when one's creations impact the world, we express it as having "resonance," so using `echo` :meaning "resonance" in English seemed quite fitting. Additionally, it signifies [expressing agreement](https://eow.alc.co.jp/search?q=echo), which pairs well with a comment management project. While selecting a name, [I received help from ChatGPT and Gemini](https://chatgpt.com/share/685fd69d-cfa8-8004-8361-82a39a1a245d), both suggested this candidate from the start, and it remained a strong contender until later stages.

However, upon consulting an online English conversation teacher (a native American English speaker), I found out that using `echo` in the context of "having resonance" isn't as common in English. Although both ChatGPT and Gemini included it as a dictionary meaning, I couldn’t be sure of its common use, and ultimately, considering my teacher indicated it wasn't generally used in this context, I leaned toward not selecting it.

Furthermore, in such a context, `echo chamber` could be evoked, which may not come across as a positive impression as mentioned by both the teacher and ChatGPT. So, it was ultimately not chosen. Regarding `chamber`, it was momentarily considered since it could mean a conference room or a particular space, but for similar reasons, it wasn’t selected.

Moreover, among candidates suggested by ChatGPT, there were `threads` and `agora`, both seemingly decent; however, `threads` overlaps with a social media service operated by Meta Corporation[^echo], and regarding `agora`, considering its use as a comment management project name, it may evoke a debate-like impression, leading to its disuse.

[^echo]: Admittedly, `echo` also overlaps with [a Go framework](https://github.com/labstack/echo).

Regarding `whisper`, it wasn’t bad at all, but it was already [taken](https://github.com/noraworld/whisper), leading to its early rejection.

Digging deeper with my native English teacher, I learned that the Japanese equivalent of saying "having resonance" in English is "ripples in a pond." Translating directly, it means "Ripples spreading across a pond," aptly representing the Japanese context of having resonance, as when metaphorically casting a stone (content like blogs) into a pond, ripples naturally spread across the surface. While in Japanese “rippling effects” is often used in negative contexts, `ripple` is also known as a cryptocurrency, and it didn’t quite resonate with me. In fact, the term was suggested initially by ChatGPT, but I remained unconvinced.

Returning to the drawing board, I asked my teacher to review [previous ChatGPT exchanges (suggested names)](https://chatgpt.com/share/685fd69d-cfa8-8004-8361-82a39a1a245d), asking which they preferred among them. They suggested `vox` might be good. Actually, `vox` wasn’t originally among ChatGPT's suggestions, but rather an invention inspired by `voxa`—derived from Latin meaning `voice`. It seems “vox pops” is an English term from "voice of the people," akin to what we call street interviews.

Indeed, searching in a dictionary, `voice` means "opinion" besides "voice." In Japanese, terms like "user's voice" bear resemblance, fitting well with the comment concept, I thought. While `voice` might appear bland, `vox` with its Latin origin conveys a bit of charm, appearing sophisticated as a project name (repository name).

It turns out that from a native perspective, `vox` suited a comment project name perfectly. After further reflection overnight, I settled on adopting `vox`.

[noraworld/vox: Thank you for making your vox heard! 😉](https://github.com/noraworld/vox)

> Thank you for making your vox heard! 😉

was a pun I used to express gratitude for the feedback received throughout this decision process. Many thanks for indulging in my personal, intricate concerns 🙏

Once the repository name was decided, implementation proceeded swiftly. It was fast from creating the repository to implementing it.

### The Blog Revamp Plan is Now Complete
All goals of the recent blog overhaul plan have been addressed. In the entry [Redesigning the Blog and Supporting English Entries](support-english-entries), the steps taken to automatically translate past articles, fix thumbnail displays, adjust past article headlines, and change Japanese tags to English have all been realized, and the comment system incorporation has now been completed.

From here on, I intend to focus on writing blog articles. Recently, I have engaged more with people, going to different places and experiencing new things. I want to document these experiences in my blog. I even have several topics in mind already, but have yet to write due to prioritizing these tasks. Finally, having these tasks wrapped up, I am delighted to be ready to start writing.

### Seeking Reactions
Also, I'm now prepared to share this blog with my online English conversation teachers and plan on sharing it with them moving forward. If they visit regularly, being able to support English (auto-translation) will be worthwhile.

Of course, if those reading this in Japanese enjoyed it, I am happy. Fundamentally, I write what I want to write and how I want to write it, not always keeping others' usefulness in mind when composing articles. However, if everyone held back in self-expression, potentially valuable content might never be shared and simply fade away, which would be a waste. Based on this belief that self-expression and dissemination are important, I plan to continue writing not only in this blog but in various areas in the future.

That said, it would be sad if no one at all read it or if there were no reactions, so even just a reaction (emoji selection) would encourage continuation. Well, since a GitHub account is needed, I don’t wish for non-engineers to create an account just for this, but if one already has an account or decides to make one for other reasons, I would be grateful if they leave a reaction or comment here as well. By pressing the `Sign in with GitHub` button while logged into a GitHub account, a confirmation screen for linking with the giscus application will appear, and upon approval, one should be able to comment on this blog.
