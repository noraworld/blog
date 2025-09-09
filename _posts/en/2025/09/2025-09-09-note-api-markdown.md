---
layout: post
title: "Reasons I Want to Use note But Can't Use It, and What I'd Like to Ask the Management"
author: [
  "noraworld"
]
description: "An attempt to summarize why I have wanted to use note for many years but haven't been able to commit to using it consistently."
date: 2025-09-09 00:25:00 +09:00
tags: []
published: true
---

### Introduction
There are reasons why I want to use [note](https://note.com) and reasons why I don't (or can't). I'd like to summarize those things today.

I intended to keep it short, but it ended up being a lengthy, rambling post. Long story short, I wish note had an official API (especially for posting articles) and complete markdown support. Meeting these two needs would make me want to use note seriously, and I predict many engineers feel the same way.

### Reasons to Use It
First, let me explain why I want to use it.

#### It's Widely Seen
I think most Japanese people who use the internet know about note. It's rare to search for something online and never come across a note article. When you want to express your thoughts or daily experiences online, platforms like Ameblo and Hatena Blog come up as options, and now note is among them. That shows how much the user base and recognition have grown.

Naturally, writing on note means that more people are likely to see my content compared to launching my own blog. Since it’s a popular service, it has advantages with search engines like Google (SEO), and within the platform itself, content can be recommended to reach many eyes.

#### You Can Write Paid Articles
This is one of note's major strengths. Previously, blog services offered places to write for free but rarely provided options to monetize. Publishing books was a high hurdle to earn from writing.

However, with note, you can post articles like a blog and set them as paid, allowing anyone to easily monetize their writing. As Horiemon mentioned, this can be seen as a "democratization of earning through writing."

Implementing this on a personal blog would be quite challenging. You would need to implement your own payment system or use a service like Stripe. Either way, it’s well beyond just starting a casual blog.

When asking readers to pay, you must also strictly define terms of service and privacy policies. Implementing such a payment system while using static site generators to host a blog can be technically difficult.

For personal blogs, earning usually means relying on ads, which brings its constraints. You can't write articles that upset advertisers, and you must conform to platforms like Google AdSense.

This often shifts focus from writing meaningful content to chasing page views, resulting in many trivial articles scattered across the internet. While I'm not against ad revenue models like on YouTube, it doesn't always seem like the best way to deliver value to humanity.

Moreover, ads clutter the web, reducing readability and ruining aesthetics. The way your blog appears to readers with different ads can be frustratingly unknown.

Also, totally unrelated ads may still display, with massive traffic spent just to show them. This too can be seen as a kind of pollution.

Critiquing ads aside, a model where readers pay directly is more likely to result in content truly written for them. That's possibly one reason why note caught on. It’s not just “profitable,” but the quality content system creates synergy between readers and authors.

### Reasons Not to Use It (or Can't)
Honestly, the desire to write daily thoughts and events on note is strong. I have plenty to say and I enjoy writing (not that I'm good at it). Being seen by many and potentially earning from it would be highly motivating.

However, as mentioned at the beginning, there are reasons I don’t use it. "Can't use it" is misleading, but I have policies for data retention, and note doesn’t currently meet those, so it’s more accurate to say I choose not to use it.

So what are these policies?

#### I Want to Manage My Articles with Git / GitHub
Git is a version control system widely used by programmers (engineers) to manage source code. GitHub is the most famous platform for hosting code managed by Git, allowing collaborative development. I’ll skip explaining version control here as it's irrelevant to this article.

Although Git is for code, it can manage any file type, including text data like this article if saved and written on your computer.

GitHub offers a convenient service called GitHub Pages, allowing you to publish such articles online. It’s useful as you can manage article content and changes thoroughly while displaying it on a website.

I love this service, but it's essentially a personal blog, so you'll start with bare SEO potential. Unlike a platform like note, there’s no internal recommendation system, so it’s about sharing links via social media or hoping they spread.

Because of this, unless you consistently write excellent articles and gain popularity, or you're already an influencer, getting seen isn’t easy. Even if many see it, monetization remains difficult.

You could manage the article's original data with Git / GitHub and then publish it on note to have others view it. However, manually managing files on your computer with Git / GitHub and separately publishing them on note is cumbersome and becomes double management. Editing existing articles would involve editing and copying them to note again, a tedious process each time.

API automation could solve this. APIs, which I'll avoid explaining due to length, could automate:

1. Writing the article file on your computer
2. Adding it to Git
3. Pushing (uploading) it to GitHub
4. Using GitHub Actions to publish externally

This would automatically upload Git-managed articles to services like note, and edits could be automated similarly.

#### No Official API
However, note requires an API to post articles via programs, and note unfortunately doesn’t officially support one.

[Does note Officially Publish an API? – note Help Center](https://www.help-note.com/hc/ja/articles/46643492548121-note%E3%81%8C%E5%85%AC%E5%BC%8F%E3%81%A7%E5%85%AC%E9%96%8B%E3%81%97%E3%81%A6%E3%81%84%E3%82%8BAPI%E3%81%AF%E3%81%82%E3%82%8A%E3%81%BE%E3%81%99%E3%81%8B)

Researching briefly, I found unofficial APIs. They let you use note's internal API endpoints (like entry points) in your code to perform operations equivalent to note's web interface.

[2024 Unofficial note API List｜Egglass](https://note.com/ego_station/n/n1a0b26f944f4)

But these are “unofficial.” Official APIs provide documentation on available endpoints, expected input, and resulting operations. Developers follow these documents to automate tasks or collect data.

With official support, sudden unavailability is unlikely; API versioning often ensures older versions still work amid changes.

Note's unofficial nature means unexpected changes with no announcements. You’d need to rewrite code each time, and without official documentation, you’d self-investigate modifications. This becomes costly if used consistently.

There's another problem. To automate note uploads with Git, you need an article API endpoint, but it seems there isn’t one...

I glanced at unofficial APIs without deep research or trials, so I can't confirm. Some articles mention sample codes to automate postings.

[How to Auto-Post Articles on note Unofficial API: For Dummies｜taku_sid🐰Agent](https://note.com/taku_sid/n/n1b1b7894e28f)

Yet, I found articles showing attempts ending with manual posting due to 404 Not Found errors.

* [API Article Post Function Verification and 404 Error (Dev Diary No.054)](https://zenn.dev/centervil/articles/2025-04-23_054_dev-diary)
* [Abandoning note API Posting and Redirecting to Markdown Auto-Generation (Dev Diary No.055)](https://zenn.dev/centervil/articles/2025-04-24_055_dev-diary)

Even if a smooth setup to automate postings existed, codes require updates with every spec change. Sample login code involves scraping (virtual browser control), which breaks with minor HTML updates, being even more vulnerable than unofficial APIs. Plus, scraping can burden servers, risking restrictions or preventive measures.

Based on this, I concluded that building a sustainable article autoposting system on note isn’t realistic now.

#### Markdown Isn't Fully Supported
Another reason to shy away from note is its incomplete markdown support.

Markdown is a simplified formatting language that lets you structure text content with ease. For instance, writing `# Heading` makes a heading, or `[note](https://note.com)` creates a link: [note](https://note.com). With various formats like images, bold text, tables, and more, it’s popular among engineers.

Although note supports some markdown, it’s not comprehensive.

[Markdown Shortcuts – note Help Center](https://www.help-note.com/hc/ja/articles/4410617032217-Markdown%E3%82%B7%E3%83%A7%E3%83%BC%E3%83%88%E3%82%AB%E3%83%83%E3%83%88)

For example, inserting images (supported in standard markdown) isn't supported in note's markdown. Tables also can't be inserted via markdown.

[Three Ways to Insert Tables on note｜K.TOMI](https://note.com/katomi95/n/ne279c3805948)

This makes proper integration with Git-managed article data difficult. You can't neatly display plain text files in note, so if you want to add tables or images, it requires manual handling on note after pasting base text. This strays far from automation.

On a side note, note’s editor is WYSIWYG (What You See Is What You Get), meaning markdown or formatting selections instantly affect displayed text. Sections like headings visually change as you type them.

I personally dislike WYSIWYG because auto-formatted text makes it harder to insert unformatted text nearby or limits flexibility. I prefer plain writing and want clean formatting only in the final product. Whether it’s code or blog posts, I want to type everything plainly.

### Summary
To sum up why I'm reluctant to use note:

* No official API → Automation is tough → Can't manage with Git / GitHub
* Markdown's not fully supported → Can't fully manage article as text files → Can't manage with Git / GitHub

Indeed, I want to manage articles with Git / GitHub. Git management allows:

* Detailed change history of articles
* Storing original data on your PC and servers like GitHub
* Easy replication from server if you change PCs (similar to note's export feature)
* Independence from specific service data formats (easier migration)

I aim to avoid relying on specific services for data (articles). Any service could end anytime, and regular service exports are painstaking. Exported data formats vary. Facing a better service and wanting to switch may hit format issues blocking easy migration—services lacking export features are non-starters.

Services should thus serve as interfaces, with crucial data managed by Git. API availability and full markdown support are crucial needs.

### Conclusion
I fully acknowledge these are views from an engineer's extreme perspective. Note isn’t just for engineers but targets a broad user base, giving little incentive to satisfy niche requests.

However, many technical note users exist, proving its engineering support. Various people create unofficial API lists, indicating demand.

If these two needs met, note could become my main interface. Five years passed since creating my account without even an official API, maybe I should abandon note... or compromise my principles and conform for small profits...

This may seem critical, but note is fascinating and promising, which is why I hope this reaches note’s management and these features improve.
