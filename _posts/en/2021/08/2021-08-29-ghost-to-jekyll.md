```yaml
---
layout: post
title: "Migrated Blog from Ghost to Jekyll"
date: "2021-08-29 22:33:27"
tags:
published: true
---
```

I migrated my blog that started on March 15, 2016 (Tuesday). I previously used a blogging system called [Ghost](https://ghost.org/), and this time, I moved to a static site generator called [Jekyll](https://jekyllrb.com/).

### The Reason for Migrating
Compared to five years ago, my way of thinking has changed significantly. If you look at [the very first article when I started my Ghost blog](/start-blog), you can see that back then, I wanted to experience the presence of a "unique blog just for me" by doing everything from server setup to deployment myself.

But now, things have changed. Hosting a blog system by renting a server yourself means everything is under your control. While this allows you to create a blog exactly how you want, it also poses a risk.

For example, if I were to leave this world, there would be no one to manage the blog. Since I'm the only one managing it, this is only natural. This means the lifespan of my blog is until the point when I can no longer maintain it in my lifetime. In fact, there were times when I left the Ghost blog unattended for a while, during which the SSL certificate expired, and access was unavailable.

Nonetheless, personally, I wish for all the content I’ve woven until now to be preserved for future generations, not just this blog. It might sound strange, but I wish to leave something that persists long beyond my lifetime.

This philosophy contradicts the idea of managing everything myself. So, I thought of leaving the blog in a way that it would persist without me managing it.

How can this be achieved? To be honest, it's impossible to guarantee 100% eternal existence. This is because I cannot know what will happen to the world after my death and it's beyond my control. However, after considering, I concluded that hosting on [GitHub Pages](https://pages.github.com/) might be the best approach for a likely chance of long-term preservation.

Nowadays, next-generation blogging services like [Note](https://note.com/) and [Medium](https://medium.com/) have emerged, but from the perspective of leaving the blog for future generations, the following disadvantages can be highlighted:

* Since you don't physically own the blog articles, there's a possibility they can be deleted at the discretion of the management or mistakes in data management by the management.
* As time changes, the service might end, causing everything to be lost.

Of course, the above two points do not mean they don't exist on GitHub Pages. Even with GitHub Pages, the servers are managed by GitHub, Inc., so you don’t actually own the hosted blog site, and there's a possibility of data loss due to database management errors. Also, the possibility of GitHub Pages disappearing cannot be ruled out.

However, that applies everywhere. There is no absolutely safe place. The reasons why I chose GitHub Pages are as follows:

* [GitHub Archive Program](https://archiveprogram.github.com/) has announced that it will maintain source code over the next 1,000 years.
* By executing `git pull`, all copies can be instantly downloaded to your local machine.
* Being managed by the large corporation Microsoft, it is unlikely that the service would end anytime soon.

The above relates more to the permanence of the data rather than the hosting by GitHub Pages, but the data will exist both locally and on the server (GitHub) as the articles will be written and published on my local machine. Moreover, even if you renew your local environment by changing your PC, you can quickly restore a copy to your local machine by simply executing a single `git pull` command in the CLI.

Furthermore, GitHub itself is quite a significant infrastructure within the IT community, making it hard to imagine GitHub Pages ending easily.

Based on the above, I concluded that hosting blog data on GitHub and publishing with GitHub Pages is currently the safest and most sustainable way to keep data available online over time.

I didn't arrive at this conclusion recently but have thought about doing it for 1 to 2 years. However, I couldn't bring myself to carry it out until now.

### Importing Data from Ghost
Now, to migrate the blog, importing data is necessary, but this was surprisingly easier than anticipated.

I found two tools for migrating from a Ghost blog to Jekyll. One is the official Jekyll importer, and the other is an importer introduced by the official as an alternative method.

- [jekyll-import](https://import.jekyllrb.com/docs/ghost/)
- [jekyll_ghost_importer](https://github.com/eloyesp/jekyll_ghost_importer)

Both are easy to use. Simply download the database file or exportable JSON file from the Ghost server, install the gem, and execute a few or just one command.

I tried both, but the official [jekyll-import](https://import.jekyllrb.com/docs/ghost/) had the following issues:

- The blog publication date couldn’t be imported correctly.
- The path of the article's thumbnail image couldn’t be imported.
- Tags of articles couldn’t be imported.

Taking a diff of the article files generated by each importer revealed that the article contents themselves were exactly the same, so I decided to adopt the import result of [jekyll_ghost_importer](https://github.com/eloyesp/jekyll_ghost_importer) since it accurately retrieved more information.

### Not Using a Custom Domain
The Ghost blog initially started with the domain `blog.noraworld.jp` and later changed to `noraworld.blog`.

I'm really fond of this domain itself, but from now on, I will try to refrain from using custom domains.

The reason, as mentioned earlier, is that using a custom domain requires "management."

Even if the blog articles and hosting remain, if the domain renewal expires and is left as is, no one will be able to access the site. In the end, it's the same as managing everything yourself and crumbling the moment you can't manage it.

Therefore, I decided to thoroughly eliminate anything that generates "management costs," which means items that can't be accessed unless managed continuously by yourself.

I’ll utilize the default domain provided by GitHub Pages. This way, I don't need to manage it, so at least the site won’t become inaccessible because I can no longer manage it.

### Reasons for Choosing Jekyll
It's good to leave the site available without the need for personal management, but the next question is how to construct the blog. The more you depend on external tools and technologies, the more likely the site won’t display as intended if their support ends.

For example, if a CDN is used to load CSS frameworks or JS libraries, the site won't display as intended if that CDN service ends, or support for those frameworks or libraries ends.

So, I hardly want to rely on such things either.

To be honest, it would be ideal if I could avoid using static site generators altogether, but that's not realistic. Writing HTML every time I write a new article is out of the question.

Then, the optimal choice for a static site generator is Jekyll because GitHub, which I’ve talked about at length, supports it.

Furthermore, Jekyll is Ruby-based, which I'm most familiar with, making it quite compatible. So, there was no hesitation.

Moreover, with Jekyll, GitHub Pages supports building, so you don't have to pre-build HTML locally before pushing. As long as you publish the source (such as markdown), GitHub's server will automatically build and publish the page.

The possibility of its support ending does exist, but if that happens, then like any other generator, I would just switch to building HTML myself before pushing, and there would be no problem.

#### Not Overusing Plugins
Jekyll has a plethora of plugins, but overusing them might lead to the possibility of being unable to use them in the future due to support ending, as mentioned repeatedly. So, I will try to avoid using them as much as possible.

If GitHub side automatically builds, you'll only be able to use a limited set of plugins. This is probably due to security concerns. If any plugins could be used for building, someone could create a malicious plugin and execute it on GitHub's server, causing harm.

You can check the list of Jekyll plugins supported by GitHub's automatic build on the following page:

[Dependency versions](https://pages.github.com/versions/)

I plan to operate with those listed, but if absolutely necessary, I consider building locally myself and publishing the built files on GitHub Pages.

### Motivation for Hobby Development and Future Plans
Due to the reasons discussed, I have recently been storing technology articles and personal private notes as GitHub repositories.

If I plan to not manage my content on personally rented servers, my motivation for hobby developing service diminishes entirely.

Naturally, if I develop a web service personally in the future, there's still the risk of losing data stored in the service's database if I can no longer manage it. This thought makes it unappealing to engage in hobby development that involves managing your data.

The diary I published on August 10, 2016 (Wednesday), was developed with a strong motivation to have my original diary site, and since then, I have periodically improved and operated it. However, considering it should be moved to GitHub Pages in the future, my motivation for diary service development has completely disappeared.

I'm very fond of this system personally, and I think it's the best diary service I've created, but more important are the everyday diaries written so far. Considering the importance of leaving valuable data for a long time, it would be safer to leave it on GitHub rather than managing it on rented servers.

Therefore, moving forward, I plan to steer towards hobby development of media that do not require managing data myself, such as smartphone apps, browser extensions, libraries, engineer tools, rather than web services, etc.

Recently, I've been inclined to engage in hobby development projects such as the following:

- Creating a static site for planning poker
  * There was an opportunity to do planning poker at work
- Creating a Pomodoro app for macOS
  * I currently use an app called Be Focused. Since I can't find an app that automatically enables Do Not Disturb during a Pomodoro session, I'm thinking of making one myself.
  * I stopped using the Pomodoro Technique a few years ago, but recently started using it again and found it very comfortable.
- Bug fix PR for [vscode-ruby-rubocop](https://github.com/misogi/vscode-ruby-rubocop)
  * Fix for https://github.com/misogi/vscode-ruby-rubocop/issues/155
- Developing a Chrome extension that allows copying the embedded iframe tag and Twitter share video title and video link from the YouTube Studio video management page
  * Due to [this](https://zenn.dev/noraworld/articles/access-restriction-using-dnsmasq) restricting access to YouTube until nighttime, I couldn't use iframe tags or sharing features.

With macOS and iPhone apps, I can create and use what I want to use, and since there's no need to manage hosting, the app won't stop working because I can't manage it. Of course, there might be compatibility issues as OS versions upgrade, but at least there won't be incidents where valuable data from a database gets lost.

### In Conclusion
I’ve barely updated the blog at all, but recently I've started to leave my own personal notes as a sort of memo on the blog. I’ve started thinking that it's okay to publicly release personal notes on the internet as long as they're not problematic if anyone sees them, even though they are private notes for myself.

This way of thinking is different from the past. In the past, I had to ensure the state was adequately perfect before releasing something external. I still have a perfectionist tendency but have developed a mentality where I can now more easily release something more lightly even if it's informal.

In the future, I want to utilize this blog as both a blog and a personal memo. I hope this blog’s content remains for future generations and helps at least one person even a little.
