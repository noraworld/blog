---
layout: post
title: "Redesigned Blog to Support English Articles"
author: [
  "noraworld"
]
description: "It's been a while since I've significantly updated my blog. I'll document the specific changes I've made."
date: 2025-06-29 18:50:00 +09:00
tags: [
  "development",
  "info"
]
published: true
---

### Introduction
As the title suggests, I've significantly updated this blog. For those unfamiliar with the previous state, and for my own record, I decided to document the specific changes I've made in this article.

### Implementation of Automatic English Translation for Articles Using GitHub Actions × ChatGPT
The idea of writing technical articles in English and posting them on [DEV Community](https://dev.to) has been around for quite some time. This is a rough summary of how I intended to achieve the same thing on this blog.

In fact, I hadn't considered making the blog English-compatible until recently. Unlike technical articles, I didn't have much desire for many people to see or appeal to it; I was content for those who wanted to read it to come to it, maintaining a lighthearted approach. Moreover, writing technical articles in English might be meaningful, but writing my personal blog in English would have no demand, and I'd mostly be sharing it only on SNS with a predominantly Japanese audience. It just wouldn't be worth the effort to write in English when no one is reading it — nor was it something I wanted to do initially.

However, the recent advancements in AI are remarkable, and for simple text-based tasks, AI can handle most of them, including English translation. Therefore, I thought that by asking ChatGPT, I could have my Japanese blog articles translated into English with almost no effort.

On social media, I don't have much interaction with people overseas, but having done online English classes for many years, I have a few close teachers. They feel more like friends now. I thought this blog could be a means to share my thoughts and experiences with them. When I recently asked these teachers if they'd be interested if they could read my blog in English, they expressed interest, so I thought there might be value in publishing English versions too.

After having ChatGPT translate using GitHub Actions and OpenAI (ChatGPT API), I managed to automate it well, so I decided to implement this feature on my blog. The code is as follows:

* [ChatGPT Feedback](https://github.com/noraworld/chatgpt-feedback/tree/67fb97626c2a4b9b92295b0a2586f0084ed358b0) [^chatgpt-feedback]
* [`.github/workflows/translate.yml`](https://github.com/noraworld/blog/blob/d01135f6c7b72871b93ba1ce3ce5bf5291673f17/.github/workflows/translate.yml)

[^chatgpt-feedback]: The usage has changed significantly from the original plan, so this repository name might change in the future.

ChatGPT Feedback was originally created to automate receiving feedback from ChatGPT about emotions recorded in a diary. However, I felt uncomfortable having something I didn't write myself in the diary, and since it takes some time to get feedback, I found myself not checking it often, leading it to become obsolete. So, I abolished it. However, when I decided to implement the English translation feature (using ChatGPT) on my blog, I thought that with some tweaks, I could still use it, so I improved it. The initial implementation was simple enough, just accepting a prompt via GitHub Actions and returning a result from ChatGPT, so the improvements weren't substantial.

So, upon posting a Japanese blog article, I created a workflow that automatically submits the content along with a prompt to translate it into English to ChatGPT, then saves the returned result into a folder for English articles. What I'm doing is genuinely simple, and I carried it out with ChatGPT's assistance.

On a technical note, when multiple Japanese article files are pushed to GitHub, I need a loop to translate each one into English. However, YAML doesn't have any looping capabilities, so I initially thought I'd have to handle looping over multiple files on the ChatGPT Feedback side and advanced implementation with that in mind for a while. But I wanted to keep ChatGPT Feedback's design as simple as just returning results for prompts. In the future, I intend to use it to summarize the contents of online English classes into diary issues, so I didn't want to include any file-specific implementation for pushes.

While exploring for a good solution, I noticed that I could use GitHub Actions' matrix strategy. While it's officially intended to build or verify operations across different environments (like Node.js v20 and Node.js v22, or Windows and macOS), what it essentially does is parallel processing, so I thought if I used it, I could effectively loop through workflows. When I actually tried it, it worked, so I adopted this design. This approach might be worth publishing as a technical article.

Although I diverged a bit from the main topic, with this setup, I've been able to publish English articles with minimal effort, allowing me to share my blog with English-speaking friends (teachers I got to know through online English lessons). I don't intend to write sensational articles for a wide audience, but knowing that many acquaintances will read it helps maintain my motivation to update the blog regularly. Just a short while ago, I thought my blog didn't need an English version, but seeing it implemented and imagining sharing it with my teachers got me excited, so I'm glad I did it.

Incidentally, I've meant to write technical articles in English for a while now, but I haven't gotten around to it, and ironically, I ended up implementing the English version on my blog first, where I hadn't intended to publicize an English version at all until recently. However, from experience, life often works this way. Things don't always go as planned, so it's crucial to at least try what I want to do, even if it's a bit impulsive. Since the mechanism is already set up, I can surely transfer it to technical articles as well, but I didn't foresee my motivation to do so leaning towards the blog rather than technical articles.

### Changed Theme (Design)
Now, even if there is an automatically translated English article, it would be displayed alongside Japanese articles without distinction. Moreover, I hadn't separated the paths (URL structure) so the same article in Japanese and English would have the same slug (filename), causing access to the English article to redirect to the Japanese article.

Therefore, internationalization is necessary. I needed to separately display the list of Japanese articles and English articles, and be able to distinguish the display for each language. Jekyll has several plugins to achieve that, and I chose one of them called Polyglot. I'll explain the internationalization in detail later, but by introducing this plugin, I stumbled upon [Yunseo Kim's Study Notes](https://www.yunseo.kim/), a blog by someone who adopted this plugin. The design of this blog was so beautiful that I was really impressed. It turned out to be using an open-source theme called [Chirpy Jekyll Theme](https://github.com/cotes2020/jekyll-theme-chirpy). I was so enamored with the design of this theme that I decided to change the theme first, putting internationalization aside. And now (as of June 29, 2025), the theme I'm using is that one.

Certainly, it’s a stylish design, and I’m very satisfied with it from that perspective. However, I have several complaints about the design part. In short, the blog's configuration has become heavily dependent on this theme.

For example, it is based on the premise that kramdown is used for the markdown parser. When I used CommonMark instead of kramdown, some features didn’t work properly:

* The ToC’s scrolling and links didn’t function
* The layout of code blocks broke

Even though I had managed to make CommonMark usable as a markdown parser, it was very disappointing that the parser became theme-dependent. The background to avoiding kramdown is because of the strange behavior of the parser, as summarized in [Thoughts on Using GitHub Actions Instead of Jekyll on GitHub Pages](https://noraworld.github.io/devlog/ja/deploy-jekyll-with-github-actions). To summarize briefly, there are these issue points:

1. A blank line must be inserted between a headline and a table, otherwise the table will not be parsed correctly.
2. Markdown cannot be used within `<details>` tags (even if blank lines are inserted before and after).
3. There’s a bug where the `|` within a link like [Example Domain | example.com](
https://example.com/) is interpreted as a table.
4. Writing a naked URL like https://example.com does not automatically create a link.

Even without using GitHub Actions, Jekyll can be used by default with GitHub Pages. However, in that case, only kramdown can be used. I wanted to avoid this, so I switched to using GitHub Actions and even created [Jekyll Build Pages](https://github.com/noraworld/jekyll-build-pages) to simplify the process. It’s so regrettable that I have to use kramdown because of the theme.

As I want to fully utilize the features and design of this theme, I have to endure it being parsed with kramdown. Although forgiving point 3 by adding `\` before `|` like `[Example Domain \| example.com](https://example.com/)`, and point 4 by writing like `[Example Domain](https://example.com/)` is permissible, point 2 is unresolvable, so refraining from using this writing style is necessary. It's hard to accept the markdown writing style being limited by the parser. I personally find having to constantly insert blank lines when writing, as in point 1, annoying and unpleasant.

Moreover, the setup itself was quite a hassle. That's because the official setup methods provided are limited to [creating a new repository from a template repository or cloning the theme repository and using it](https://chirpy.cotes.page/posts/getting-started/#creating-a-site-repository). The documentation only describes how to create a new blog, and there is no explicit procedure for applying it to an existing blog.

I wanted to use [Jekyll Remote Theme](https://github.com/benbalter/jekyll-remote-theme), but perhaps because the implementation deviates significantly from Jekyll's philosophy, I couldn't successfully build it. Even trying to install [Chirpy Jekyll Theme](https://github.com/cotes2020/jekyll-theme-chirpy) directly hit a snag initially as no CSS was applied, resulting in a series of troubles. Part of the issue was the modification of an initial theme [Minima](https://github.com/jekyll/minima), but the lack of support for applying it to existing blogs made it user-unfriendly.

For the time being, I'm satisfied with this, but the inability to use CommonMark suggests that I might end up creating my own theme eventually, after all. Perhaps it's unreasonable to complain while using it, but I personally dislike the thought process of limiting settings and narrowing user choices. Initially, when I saw this theme, I thought, "If this theme can be used, maybe it's better to piggyback onto already amazing platforms, static site generators, plugins, and themes created by others, rather than creating something myself." But to ultimately create a site that satisfies me, I reconsidered and thought in the end, I might have to make one to some extent. Although I'm making full use of excellent existing projects like GitHub, Jekyll, and Polyglot in the end.

### Internationalization
Finally, I’ve handled internationalization. This was briefly mentioned in the previous section about the theme change, but merely placing an English article doesn't solve the issue of it being displayed together with Japanese articles or having inaccessible paths due to incorrect slugs. Improved internationalization through a plugin introduction is necessary to resolve these issues.

While I'm not sure if it's popular, among the ones that come to mind with many stars is the [Jekyll Multiple Languages Plugin](https://github.com/kurtsson/jekyll-multiple-languages-plugin). However, development for this plugin halted two years ago as of now. [Although other similar plugins exist](https://github.com/kurtsson/jekyll-multiple-languages-plugin/tree/cba063ff3a9002f35f06fd3c5c136d529828e584?tab=readme-ov-file#10-other-language-plugins), most are no longer maintained, and few have many stars.

Under such circumstances, [Polyglot](https://github.com/untra/polyglot) is still being updated. Although it has approximately half the number of stars compared to the Jekyll Multiple Languages Plugin (as of now), there are cases of adoption, and upon checking the README, it seemed designed simply, so I decided to implement it this time. Incidentally, I found [Yunseo Kim's Study Notes](https://www.yunseo.kim/) via the [Polyglot README](https://github.com/untra/polyglot/tree/bcb7525c001b410381b709e9436d271d2d14c17a?tab=readme-ov-file#other-websites-built-with-polyglot).

A concern, as described in the [How To Use It](https://github.com/untra/polyglot/tree/bcb7525c001b410381b709e9436d271d2d14c17a?tab=readme-ov-file#how-to-use-it), was

```
_posts/2010-03-01-salad-recipes-en.md
_posts/2010-03-01-salad-recipes-sv.md
_posts/2010-03-01-salad-recipes-fr.md
```

having to append language codes (such as `ja` for Japanese, `en` for English, `sv` for Swedish, and `fr` for French, representing each language in two letters) to filenames before the extension. This, like the case with Chirpy earlier, was another constraint of having to alter filenames, especially article file names, due to a plugin, which was unacceptable.

However, testing it locally revealed that my concerns were unfounded. It turned out that these suffixes are just one means of language identification, and by enabling other language differentiation methods, there's no need to alter filenames, which I realized later.

1. By associating each article file's YAML front matter with a `lang` key and language code.
2. By dividing directories per language like `_posts/ja`, `_posts/en`, and making `lang_from_path: true` effective in `_config.yml`.

I’ve chosen the method of dividing directories per language as in 2 above. Frankly, even if languages could only be divided through other methods (such as method 1), I intended to separate them into directories like `_posts/ja`, `_posts/en`, for easier readability of the repository's folder structure. Thus, adopting method 2 negated the necessity to edit all existing article files—hitting two birds with one stone.

For paths, Japanese articles remain as `/blog/<slug>`, while English ones become `/blog/en/<slug>`[^path]. It's appreciated that when accessing the English version, all links on that page begin with `/blog/en/`. Initially, due to `baseurl: "/blog/"`, it didn’t function as intended, but adjusting it to `baseurl: "/blog"` without the trailing slash resolved the issue. Now, what was I thinking with `/blog/`?

[^path]: This might change in the future but that’s how it is at present.

#### Dropdown Display for Language Switching
However, the theme itself wasn't internationalized, and Chirpy was no exception. Hence, to access an English article, one had to manually add `en` in the browser's address bar. As such, when landing on a 404 Not Found page, you would revert back to a Japanese path, so I wanted to display a menu to switch languages within the page itself. This would also be user-friendly for those landing from search engines.

For the same, I referred to [Yunseo Kim's Study Notes](https://www.yunseo.kim/), which I’ve mentioned repeatedly. His blog supported a language selection dropdown displayed in the side menu through [`lang-selector.html`](https://github.com/yunseo-kim/yunseo-kim.github.io/blob/b67074b2871b9d1c719912fea40df1e08e2b8de5/_includes/lang-selector.html), so I adopted it.

![](https://noraworld.github.io/box-ivysaur/2025/06/29/cbc7ab239f713e377d8a31b163c39167.png)

#### Annotation Indicating Automatic Translation
Additionally, regarding English articles, I'm completely relying on ChatGPT and don’t intend to write them myself[^motivation]. Although AI has evolved to generate natural text, as these are automatic translations, minor nuances, cultural expressions, or technical terms might be inaccurately translated. Actually, before writing this article, I had ChatGPT generate English versions for two articles (translation for other past articles is forthcoming), and noticed that words like SNS were directly presented. In this article too, where I’ve mentioned SNS earlier, it might not be translated accurately, because SNS (Social Networking Service) is a Japanese-English term, and in English, it's Social Media.

[^motivation]: It’s extremely cumbersome to have to write in multiple languages every time the blog is updated, and attempting anything that labor-intensive would dissuade me from blogging entirely.

Thus, to prevent misunderstandings, it seemed necessary to include cautionary notes conveying that some descriptions might be incorrectly rendered due to translation from Japanese for English articles. While I could pre-emptively inform the online English-class teachers I’m close with, there’s a non-zero chance that others globally might access it through search engines, and misleading them would be undesirable.

Initially, I intended to address this by instructing ChatGPT's prompt to add the following text at the beginning of the body:

> This article was automatically translated from Japanese to English by ChatGPT.
> Please note that some nuances or information may not be accurately reflected.

However, having this displayed with the regular text every time would feel a bit off, and as ChatGPT isn’t flawless, loading it with prompt instructions might cause it not to write precisely as intended. Therefore, I thought it would be better to convey this not through ChatGPT but via the system itself with formatting/design that clearly indicates it's an advisory note.

Asking ChatGPT about the implementation, I found an easy way to address it, so I followed suit. Simply by copying Chirpy’s `post.html` and [adding a few lines](https://github.com/noraworld/blog/commit/7c6f227b43e5831cd390353be0b69402f24fe7cd), I managed quite smoothly. The warning-style display was already facilitated by Chirpy, so I leveraged that.

![](https://noraworld.github.io/box-ivysaur/2025/06/29/4e3b79be94cbe702f0dda67091524c44.png)

With this, the internationalization meets satisfactory levels and successfully deployed.

### Future To-Dos
I could already introduce it to the teachers with "Hey, I've got the English version ready!", but even if sharing it, there are a few unfinished tasks I want to address shortly.

#### Automatic Translation for Past Articles
For new articles, the process of automatically having ChatGPT translate the Japanese articles upon push (publication) is automated, so there’s no issue here. However, for past articles, English versions don’t exist yet. Although, as the workflow is activated when articles are placed inside `_posts/ja`, merely moving past articles into `_posts/ja` would suffice. I plan to handle it bit by bit while observing API limitations or unintended behavior, rather than executing all at once.

#### Implementing the Comment System
I've been using a comment system called [Disqus](https://disqus.com/) from before. While I intended to continue using Disqus, I learned about another comment system named [giscus](https://giscus.app/) during this update. Although I had seen blogs employing this comment system before, I hadn’t realized it was giscus until this revision prompted it.

While Disqus never particularly dissatisfactory, I was quickly charmed by giscus and decided to switch from Disqus to giscus with this update. “Switch” might be more apt than “migrate,” as I’m not transferring past comments[^past-comments].

[^past-comments]: During the transition from [Ghost to Jekyll](https://noraworld.github.io/blog/ghost-to-jekyll), the changing URL resulted in losing continuity of past comments. Thus, there are currently no comments to transfer, as after switching to Jekyll, comments were not implemented for a while. Recently, when Disqus was set up on Jekyll, there were zero comments, so nothing will carry over now.

The reason I was captivated by giscus is that it’s built on the GitHub ecosystem. As described in [Switching from Ghost to Jekyll](https://noraworld.github.io/blog/ghost-to-jekyll), I have an inclination not to rely too much on other platforms. Since static sites are technically unable to have a built-in comment function, reliance on external tools is inevitable. However, giscus allows comments to be managed on GitHub, making it fitting for someone deeply immersed in the GitHub ecosystem.

Besides, I also found similar comment systems like [utterances](https://github.com/utterance/utterances) and [Gitalk](https://github.com/gitalk/gitalk), but chose giscus due to its popularity and activity. Incidentally, giscus was inspired by utterances. A major distinction between the two lies in whether GitHub Issues (utterances) or GitHub Discussions (giscus) are utilized.

Initially, whether to use GitHub Discussions didn’t matter much personally, but in cases like giscus permits segregating content under categories, which offers the advantage where comments for multiple sites, including this blog, technical articles, and diaries, could be consolidated and managed under one repository. Indeed, I plan to manage comments in one repository using this method.

The implementation itself doesn’t seem too difficult, so I planned to implement it yesterday or today. But as mentioned, to manage multiple sites under one repository, I need a new repository, and
deciding on its name has delayed progress. Despite not accomplishing much work recently, there are many things I still want to do with the blog and plenty of topics to write about. Therefore, I opted to write this article before generating any progress on that front.

Once the comment system is implemented, I’ll write an article to notify of the same.

#### Fix Thumbnail Display
Currently, several past articles lack a displayed thumbnail.

![](https://noraworld.github.io/box-ivysaur/2025/06/29/1f5da56f44b67686cad47ce4a9b1b2ec.png)

Yet here lies the issue of no image (thumbnail) ever initially existing rather than broken-links causing failed displays. The reason why non-existent image (thumbnail) reads are attempted stems from `image: ''` being within the YAML front matter configuration. As the previous vast difference between the theme called Minima and Chirpy lies in the display of thumbnails, it never posed an issue in Minima due to the absence of thumbnail displays. Now, with Chirpy showing thumbnails, such records result in attempts to read non-existing thumbnails.

This likely sneaked in when exporting unspecific article thumbnails during the migration from Ghost. While it doesn’t result in errors, it leads to a lackluster display, leaving me no choice but to fix it. Actually, as these articles currently lacking thumbnails were created without designated thumbnails, all I have to do is eliminate the `image: ''` record, but if I find any possible thumbnail-worthy images within an article, I might consider setting those as thumbnails. Though, I’ll handle such things on the fly during work.

#### Integrating Sub-headers (headlines) into h3 or Below for Past Articles
Chirpy features a ToC, yet for some reason, it does not recognize `<h1>` tags. Though unclarified if this is a theme specification or a bug casting a skeptical presumption, it spawns the need for PSDs (including `<h2>`) to interfere with headline hierarchy mismatches from potential blog article-to-diary automatic mirroring functions. Therefore, I aim to consolidate any header usage within blog articles using `<h3>` or below.

#### Changing Japanese Tags to English
Currently, tags are a mix of Japanese and English, necessitating corrections.

![](https://noraworld.github.io/box-ivysaur/2025/06/29/e9712998aae55c076201d9e56184eda4.png)

### Conclusion
For a long time, especially after switching to Jekyll, blog updates had become rare. Recently, I regained the enthusiasm to update the blog once more, and nurturing the managed blog to a favorable shape is quite gratifying. Though it might merely be self-satisfaction, creating and authoring content or articles that are etiquette of tangible clarity amplifies personal wealth. I steadfastly believe that serving a single person in its entirety provides substantial fulfillment. Thus, even if resulting in self-satisfaction, eaning money isn’t the sole evaluation criterion.
