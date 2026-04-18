---
layout: post
title: "Reasons Why I Can't Use Note and What I Want from the Management"
author: [
  "noraworld"
]
description: "After years of wanting to use Note, here is an attempted summary of why I can't commit to continuous use."
# https://chatgpt.com/share/69e33102-8134-83a9-8603-c9962e89f335
image: "https://noraworld.github.io/box-venusaur/2026/04/18/24435486a6aa49f0a43d89f2a63a9341.png"
date: 2025-09-09 00:25:00 +09:00
tags: []
published: true
note_published: true
note_id: 125458771
---

### Introduction
There are reasons why I want to use [Note](https://note.com) and reasons why I don't (or can't). I'd like to summarize those reasons here.

Although I intended to keep it brief, I ended up writing a long piece as usual. In conclusion, I'd like Note to have an official API (especially an endpoint for posting articles) and full Markdown support. If these two aspects were fulfilled, I'd be enthusiastic about using Note, and I predict many engineers feel the same.

### Why I Want to Use It
First, let me explain why I want to use it.

#### High Visibility
I don't think many Japanese people using the internet are unaware of Note. It's rare to search for something online and never come across a Note article. When you want to express your thoughts, feelings, or daily happenings like a blog, traditional services like Ameba Blog or Hatena Blog come to mind. However, lately, Note has become one of the options among them. I believe its user base and recognition have expanded that much.

As a result, writing on Note likely gives you more visibility than starting your own blog. Its popularity as a service helps it rank higher on search engines like Google (strong SEO), and it gets recommended on the Note platform itself, exposing your work to a wider audience.

#### The Ability to Write Paid Articles
This is one of Note's significant strengths. A while back, blog services provided a space to write for free, but opportunities to monetize were scarce. Earning from writing required high barriers like publishing a book.

With Note, you can post blog-like articles online and easily monetize by setting them as paid content. To borrow from Horie's words, this can be called the "democratization of monetizing through writing."

To implement paid features on a personal blog can be challenging. You'd either have to create a payment system yourself or use a service like Stripe. Both options stray far from the realm of starting a simple blog.

Moreover, when charging readers, terms of service and privacy policies must be well-defined. Implementing such a payment system when hosting a blog using a static site generator can be technically challenging.

Traditional personal blog monetization mostly revolved around ads, but earning from them imposes heavy constraints on each article. You can't upset advertisers, and you have to conform to platforms like Google AdSense.

Furthermore, the focus often shifts from "writing beneficial content for others" to "maximizing views," resulting in trivial articles scattered online written purely for numbers (though, I don't claim that's always the case). While I don't deny the prevalence of ad revenue models like on YouTube, when considering humanity's value offerings, it doesn't always seem the best fit.

Ads are also considered contaminating. Ad-heavy web pages lack readability and look messy. It's unsettling not knowing how readers see even your blog due to differing displayed ads.

Additionally, irrelevant ads might show up, yet significant traffic is spent displaying them. This too might be a form of contamination.

Although I ended up criticizing ads, unlike them, models that seek direct reader contributions encourage writing genuinely for them. That’s likely part of Note's popularity. It's not just about "earning money," but offering high-quality content that creates a positive feedback loop between readers and writers.

### Why I Don't (Can't) Use It
Frankly, I have a strong desire to write daily thoughts, ideas, and events on Note. I have plenty to say. Since I enjoy writing (though not proficiently), if many people could see it and I could potentially earn from it, I'd be highly motivated.

However, I also have reasons for not using it as mentioned earlier. Rather than "can't use," it's more accurate to say I won't use it due to a personal policy for data storage that Note currently can't meet.

So, what is this policy?

#### Managing Written Articles with Git / GitHub
Git is a version control system widely used by programmers (engineers) to manage source code. GitHub allows hosting and collaborative development of Git-managed code on servers, making it a world-renowned platform. While this doesn't directly relate to this article, understanding version control systems isn't necessary here.

Initially designed for managing source code, Git can technically manage any file, including text data like blog articles written and saved on your PC.

Furthermore, GitHub offers GitHub Pages, enabling these articles to be published online. This lets you manage content revisions and publish it on the web.

It's a handy service that I dearly enjoy. However, as an almost personal blog, you'd have to start with a clean slate in terms of SEO. Also, without a platform like Note, there aren't built-in recommendation features that others also using Note would easily find, except perhaps through shared links on social networks.

Unless you consistently write outstanding articles gaining attention or already have a known influencer status, getting a wide readership is challenging. Even with a following, monetizing can be tough without integrated features.

A possible approach would be managing base article data with Git / GitHub while posting it on Note for others to read. However, managing files locally with Git / GitHub and posting the same on Note manually requires extra effort and becomes double management. Editing existing articles means copying updates every time.

A solution to this would be using APIs to automate. Delving into APIs would veer this article away from its purpose, but with APIs, you could:

1. Write articles in local files
2. Add them to Git
3. Push to GitHub
4. Post on external services (e.g., Note) using GitHub Actions

Automating this way means articles pushed to GitHub could be automatically shared on blog services (like Note), even updating this way remains hands-free.

#### No Official API Offered
Yet, posting articles programmatically on Note requires an API provided by Note, something they unfortunately don't officially support.

[noteが公式で公開しているAPIはありますか？ – noteヘルプセンター](https://www.help-note.com/hc/ja/articles/46643492548121-note%E3%81%8C%E5%85%AC%E5%BC%8F%E3%81%A7%E5%85%AC%E9%96%8B%E3%81%97%E3%81%A6%E3%81%84%E3%82%8BAPI%E3%81%AF%E3%81%82%E3%82%8A%E3%81%BE%E3%81%99%E3%81%8B)

A little research reveals unofficial APIs. These utilize Note’s internal API endpoints through custom code to perform web actions equivalently.

[2024年版 note API 非公式一覧表｜えっぐらす](https://note.com/ego_station/n/n1a0b26f944f4)

Still, it's "unofficial." Officially provided APIs come with documentation outlining endpoints and their parameters, making automation feasible for engineers.

Official APIs ensure stability during service or spec changes, often maintaining backward compatibility (e.g., versioning APIs).

Without official support, Note's unofficial APIs risk sudden adherence to breaking changes without notice, introducing continuous costs in terms of code maintenance.

A further complication: using Git-managed articles to automatically post on Note demands an endpoint for creating articles, which seemingly doesn’t exist for Note?

Although some reports claim to have successfully scripted article auto-posting using Note's APIs, others cite 404 errors or manual fallback due to such hurdles.

* [API経由記事投稿機能の動作確認と404エラー（開発日記 No.054）](https://zenn.dev/centervil/articles/2025-04-23_054_dev-diary)
* [note API投稿断念とMarkdown自動生成への方針転換（開発日記 No.055）](https://zenn.dev/centervil/articles/2025-04-24_055_dev-diary)

Even successful automations risk costly changes upon updates, given the unofficial API. Reports also suggest authentication done through scraping (using code to emulate browser manipulation instead of API calls) is fragile, breaking upon HTML changes.

Thus, my current conclusion is that establishing a note-auto-posting structure for steady usage seems impractical.

#### Markdown Isn’t Fully Supported
Another deterrent from using Note is its incomplete Markdown support.

Markdown is a syntax for easily structuring text, where, for example, writing `# Heading` results in a heading, and `[note](https://note.com)` creates a [note](https://note.com) link. It includes various markup commands (images, tables, bolding, etc.), praised among engineers for its intuitive, controlled writing.

While Note partially supports Markdown, its limitations mean table inserts or image placements involve manual interventions outside Markdown.

[noteでの表の貼り方3種について｜K.TOMI](https://note.com/katomi95/n/ne279c3805948)

This presents challenges for managing article data with Git. Markdown-incompatible elements like tables or images complicate presentation purely through text files, requiring note post-editing.

Notably, Note's editor isn't designed for Markdown-first, instantly rendering text with styling. This WYSIWYG (What You See Is What You Get) interface isn't my favorite as it immediately alters unstyled text, making subsequent unstyled additions cumbersome.

Though I’d like my writings to look polished for readers, I prefer unstyled drafting, be it code or blogs. I'm part of the faction that writes everything in raw text, appreciating the fuller control, visibility, and transferable value structure offers.

### Conclusion
So, here are the reasons I choose not to use Note (even if I want to):

* No official API → challenging automation → infeasibility with Git / GitHub management
* Incomplete Markdown support → incomplete text file management → infeasibility with Git / GitHub management

Ultimately, I want to manage articles with Git / GitHub. Git allows:

* Detailed change logs
* Storing original data on local as well as server (GitHub)
* Easy duplication on a new computer from server-stored content (potential equivalent to Note’s export feature)
* Service export format independence (easy migration)

I hope to avoid specific service dependency for data (Note's articles in this case). Services come and go; performing regular exports across multiple services is taxing. Additionally, export formats differ; service mismatches affect migration feasibility.

In that respect, services are for interfacing; my data must remain Git-managed. Hence, an API and complete Markdown support fulfill vital criteria for me.

### In Closing
Of course, this is a strictly engineer-centric perspective. Note isn't specifically an article posting service for engineers but targets a broader user base. Hence, from Note's standpoint, fulfilling these niche needs might not incent them much.

Nonetheless, many Note users engage in technical writings, confirming engineer support. Furthermore, unofficial API listings attest to a tangible demand.

If only these two aspects were met, I could use Note as my primary platform. Though it's been five years since creating my account, the lack of an official API disheartens me—should I abandon thoughts of using Note? Or should I conform to Note's style, setting aside my policies to earn small income? 

This might sound critical of Note, but it reflects its appeal and the expectations I harbor. I hope this reaches Note's management, leading to the provision and improvement of these features.
