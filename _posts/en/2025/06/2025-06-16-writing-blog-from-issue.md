---
layout: post
number: 1
title: "An Attempt to Blog on GitHub Issues"
author: [
  "noraworld"
]
description: "An Attempt to Blog on GitHub Issues"
date: 2025-06-16 23:54:51 +09:00
tags: []
published: true
---

This article was automatically translated from Japanese to English by ChatGPT. Please note that some nuances or information may not be accurately reflected.

It's been a while again since the last blog update. The last update was at the end of last year, so this is my first post this year.

### Building a System for Casual Blog Updates
However, this time, the interruption of blog updates might be somewhat alleviated. This is because I have finally built a system that allows me to update the blog with ease. I had this idea for a while, but I couldn't quite consolidate it or get started. Recently, though, the desire to update my blog has grown again, and while thinking about various things, I came up with what seems like a reasonably easy-to-use system and proceeded to implement it.

By "easy," I mean I'd like to be able to write on my iPhone. I use my Mac almost daily, but often, when I intend to write, I find it cumbersome on the Mac. If I wanted to write more casually, I wanted a system that would allow me to write just as easily on my iPhone.

### The Hassle of Deciding File Names First
One thing that felt like an obstacle when writing on both iPhone and Mac was the need to create a file first. It's been a while since I've moved the blog to GitHub, and managing it in a GitHub repository means that blog posts are managed as files. And that means creating a file first and then writing the content of the article into it.

What feels cumbersome is having to decide on a file name first. Of course, it needs to be decided eventually, but often before starting to write, I don't have a clear idea of the content. Sometimes, as I write, it expands and differs from the initially planned title. Other times, I vaguely know what I want to write about but am not sure about the specifics, and it gradually takes shape as I start writing.

In such cases, the title is ambiguous, making it hard to determine the file name. This blog uses a static site generator called Jekyll, which involves a file naming convention like `yyyy-mm-dd-slug.md` where the string used in the URL is included. For my blog, this is usually a descriptive name summarizing the content, so it's often unclear until I've finished writing.

But having to decide on a file name and create a file before starting to write felt like a hassle.

### The Limitations of Writing Directly into Files
Of course, there are several solutions to this. One suggested method is creating a file with a provisional name like `2025-06-16-foo.md`, anticipating later renaming; however, changing the file name breaks the history associated with the file. While it's not a major issue, as a perfectionist, I feel uneasy seeing the history being broken when looking back later. I considered squashing commit histories when merging pull requests, but having multiple commits consolidated into one when they already exist felt somewhat unsatisfying.

Another method is temporarily creating a draft file locally and copying it to the repository when it's relatively complete. But this is awkward on an iPhone. Though writing temporarily in a memo app would be fine, considering I record most things, even memos, on GitHub, I don't use memo apps. Moreover, deleting entries in a memo app later can be cumbersome.

And the biggest drawback is not being able to upload images. GitHub is primarily a place for managing and publishing source code, and naturally, editors like VS Code aren't designed for image uploads. The typical method involves uploading an image to the repository and then manually copying the URL for reference, which is quite cumbersome to do manually on an iPhone.

Given these drawbacks, this approach was not adopted.

### Making Use of GitHub Issues
So, I utilized an issue-based method I also use for journals, enabling updates in this way. Specifically, I decided to use [Issue Recorder](https://github.com/noraworld/issue-recorder), a GitHub Action I created myself.

This was initially made to convert diary entries written as issues into files. Since diaries are divided by day and can require multiple updates within the same day, making updates in a 파일 could be cumbersome, leading me to come up with the idea of using issues.

While for blogging, each entry becomes a separate article (file), the idea of using issues didn't naturally come to mind. However, I thought maybe the same system used for diaries could be adapted for blogs, leading me to set up the environment. Hence, this article is being published as a blog post from a comment written in an issue. By the way, this is the first article of its sort, so operation verification hasn't been done. I'd hope it gets successfully converted and deployed.

Moreover, the Issue Recorder provides an option to automatically save images attached to issues as files in the repository, making image uploads a breeze. Images can be uploaded to issues, so posting from the GitHub app for iOS is not a problem.

### Background for the Desire to Resume Blog Updates
Seeing articles by [Mr. catnose from Quiet Internet](https://sizu.me/catnose) made me reconsider how it's nice to regularly share updates and events, reigniting my desire to update the blog.

Although Quiet Internet is slightly different from blogs, I perceive it to have a similar nature. Among these, entries written by Mr. catnose often end in a few paragraphs, even though some are quite extensive. Some entries end in just one sentence, making me feel astounded thinking, "It's okay to be this short." It's not a critique for being short; rather, it's a forgiving realization for the perfectionist in me that it's okay to write blogs this freely. If it's okay to have entries of this length, I might be more consistently able to write, which offers a re-triggering reason for resumption. Although admittedly, this entry is already quite lengthy.

Moreover, while I typically write down what I think or events of the day swiftly in my journal, sometimes I manage to write something valuable. Journals encompass various topics and can inadvertently bury good content among other parts. For instance, writing about feeling hot today ends up written down as "It's hot today," or after turning on the air conditioning, it gets written as "Air conditioning is on," purely for record-keeping. Still, amidst such musings, impressions, or realizations yielding personal impact get mixed, causing a sense of loss for being restricted there.

Additionally, while journals are set to be published three years after the entry date, writing something good only for it to stay out of sight for three years feels a bit sad.

Thus, when I manage something notably good, I increasingly feel like transferring that portion into blog entries.

GitHub Issues have a "Reference in new issue" function, allowing the creation of a new issue from the content of comments. Using this, if I write something well in a journal, I could easily make it a blog entry by transferring that comment to the blog post repository's issue. For someone as lazy as myself, having content turn into entries that weren’t initially planned to be blog posts presents significant ease.

### Abandonment of Ad Revenue Ideas
Short content has the downside of likely failing to pass Google AdSense reviews, but given I repeatedly attempted and ultimately failed years ago, I'll abandon thoughts of ad revenue. While I'd ideally want to be independent through ads or, like Mr. catnose, create and monetize personal products, it might not be necessary here. I'm unlikely to write entries that can sustain a living, and the ad revenue market is a red ocean.

Moreover, implementing ads imposes content restrictions. You wouldn't be able to write articles deemed unsuitable for ads. Those standards reportedly grow stricter each year. Personally, I want this blog to mention my antithesis towards the world and discuss contentious topics. I don't want such constraints imposed when the potential for earning is slight. It's clearer without accepting token money like ad revenue.

### Avoiding Other Platforms
The services Mr. catnose creates are all exquisitely and stylishly designed. Additionally, there's a higher likelihood of visibility by affiliating with a reasonably adopted platform. I considered starting anew on Quiet Internet as a blog-like platform, but fundamentally, I've always felt that for writings that transform into memories and records — akin to a blog —I want to manage and operate them firmly without relying on another platform.

Even though I tried posting just one article on Quiet Internet to get a feel for it, designed to focus on simplicity, I found markdown usage to be quite limited. Only part of it was usable, and it felt off using the WYSIWYG method, which I'm not fond of, either. Notably, images couldn't be pasted by specifying the URL, adding concern over managing images if transitioning to another platform, marking a significant downside for me personally.

Individual-operated services might end anytime, leading to hesitation in fully committing important data or using them extensively.

This is not to negate Mr. catnose. In fact, I'm deeply impressed by the excellence of the services he creates. But regardless of anything anyone creates, unless this fundamental belief wavers, I can't bring myself to earnestly engage.

Platforms like note, apart from Quiet Internet, exist, but since they could end any day, I don't particularly want to use them. If either Quiet Internet or note had an end-point for publishing with an API, mirroring posts there wouldn’t be a bad idea. Yet, even with such end-points, if markdown can't be utilized, writing constraints seem unsatisfactory. Therefore, I still prefer the adaptable aspects of personal blogs.

As such, I'll continue with GitHub Pages for publication without transitioning to a new platform.

### Random Numbers and Hash Values Rejected
Earlier, I mentioned a file naming format like `yyyy-mm-dd-slug.md`, but another idea considered involved using random numbers or hash values for the `slug` part. This method of naming URLs is quite common and would eliminate the need to devise slugs manually, resolving previous issues. Plus, it simplifies entry creation.

But after further consideration, I ultimately discarded it. While hosting and operating on GitHub Pages is a goal, I also value the state in which files are stored in the repository. In GitHub Pages, this only impacts the URL usage, so that's okay, but in the repository, it affects the file name. When looking through articles on the repository, having filenames filled with random sequences makes it hard to discern the content without opening each file.

Even though I aim to host and operate on GitHub Pages, if, by chance, the need arises to move away from GitHub in the future, performing a `git pull` allows for bulk download; however, having file names that obscure article content seems inefficient for mastering the state as files.

### Using the Partial Private Function for Writing as Desired
As mentioned earlier, with Issue Recorder, image posting is not problematic. Moreover, a partial private function allows certain text to be masked on the blog, as in the case of [^pvt_a8b0580].

Since blogs are written with the expectation of immediate public viewing, I intend to keep in mind the manner of writing suitable for sharing with others. Within this, though, there are parts I want to retain as a personal record, like personal information or details concerning others' privacy. For example, if writing about going out somewhere with a friend, and that friend requests anonymity, it can't be publicized. However, needing to record who I went with for personal reference, the partial private function becomes invaluable. Though initially intended for journaling, it seems usable for blogs as well, making it likely I'll write anything I wish to, deciding on what to publicize on a case-by-case basis, relieving me of much deliberation when writing.

### Avoiding Striving for Perfection in Writing
I'm pleased to have created a conducive environment for casual blogging. Truth is, there have been topics I wanted to blog about but found cumbersome, eventually leaving them unwritten until now. With this conducive environment set, writing those would be good.

Yet, it's crucial not to forget not to aim for perfect writing. It's a thought perfectionists like myself easily fall into — regardless of setup enabling casual writing, sincere attempts to write each article thoroughly will not be sustainable. In fact, writing this entry is already boring me now, to be honest.

Like the articles by Mr. catnose on Quiet Internet, even brief entries are okay. I desire to share with someone on the internet and have it remain as a memory for myself. Nothing is left if I avoid writing because I get lazy trying to write well.

One writing tip I've thought of to ease the process is prewriting desired content as headings to guide filling them with text; amidst writing this through issues as I described earlier, I considered dividing comments by paragraph. A long comment makes it irritating to find the spot when you wish to add more, and even if comments separate, they merely divide paragraphs while consolidating as one file, enhancing ease in writing them divided. Given the reduced risk of app crashes leading to full re-writes, and easier editing when adding headings, I might benefit from actively splitting comments.

### No Implementation of Automated Sharing to SNS
Moreover, I considered automating sharing the posts on SNS like Twitter upon publication, but since I don't feel like sharing every single article on SNS, I'll avoid it. Like antitheses mentioned earlier or controversial topics often misunderstood, only those deliberately seeking such content should see it. There should be hidden, exclusive information. That's where I wish to place some niche data or special insights.

### Keeping Drafts Private
Further, this setup can technically be done within a public repository, so I briefly considered utilizing issues within the same repository where this blog is published, but decided against it. Allowing anyone to create or comment on issues could lead to misuse. In practice, such issues, as well as plans and to-do lists shared with issues, are managed via a private repository for these reasons.

Also, while quick to publish, the idea of being viewed amidst writing is slightly discomforting. Therefore, it was made within a private repository.

Actually, I just realized, given the premise of using a partial private function, it simply can't be public.

### Design
Back in my university days when I was running my blog, it was initially novel having juniors from the same university viewing it, so I intricately crafted the design to be stylish. Before university, interactions remained mostly online. During this period, I hosted my blog service on a rented VPS.

However, after joining the workforce and those ties gradually thinning, I felt resistance in voluntarily telling work colleagues about blogging due to wanting separation of work and personal life, making real-life acquaintance viewership rare.

It marked the start of a declining update frequency. In the midst of that, after [migrating to Jekyll in 2021](https://noraworld.github.io/blog/ghost-to-jekyll), redesigning was necessary. Although I sporadically wrote as a personal memo record, the motivation to redesign was completely absent. The incentive to record occasionally existed, presuming nobody noticed the design, thinking retaining memories sufficed.

Yet, contemplating consistent future updates, having a stylish design would likely heighten my enthusiasm and, given that the chic design on Quiet Internet is a catalyst to wanting to write, I plan to ~~imitate~~ learn from its design.

Frankly, I don't currently possess the motivation for a complete design overhaul, but as I keep updating, that might change. I certainly feel inclined to have an aesthetic design. Hence, perhaps growing fond of the blog through continuous writing could spur on initiating design improvement.

### Conclusion
I feel like there were various things I wanted to write but ended up focusing on constructing the setup, letting time pass, leading to somewhat disjointed thoughts and sentences. Still, it's fine. Trying too hard to write properly only leads to discontinuation. Without plans for monetization, stumbling through impromptu expression is enough. Just making them viewable without forcing the viewers’ experience suffices. Even eccentric enough individuals viewing such a blog are fine. With such a mindset.
