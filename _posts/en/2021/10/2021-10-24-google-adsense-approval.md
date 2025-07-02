---
layout: post
title: "Review of Google AdSense"
image: "https://raw.githubusercontent.com/noraworld/blog-content/main/google-adsense-approval/Screen%20Shot%202021-10-24%20at%2013.27.05.png"
date: "2021-10-24 13:10:45"
tags:
published: true
---

I decided to document what I did until I passed the Google AdSense review. By the way, at the time of starting this article, I have not yet passed the review. This article might end up being shelved.

### The First Review
In fact, I have already passed a Google AdSense review once. I created a Google AdSense account on April 12, 2021. On the same day, I applied for a review for the domain `noraworld.blog`, which was for my old blog, and was promptly rejected.

![Google AdSense Rejection](https://raw.githubusercontent.com/noraworld/blog-content/main/google-adsense-approval/Screen%20Shot%202021-10-24%20at%2013.22.48.png)

Then, about 10 days later, I reapplied without changing any content, and surprisingly got approved easily.

![Google AdSense Approval](https://raw.githubusercontent.com/noraworld/blog-content/main/google-adsense-approval/Screen%20Shot%202021-10-24%20at%2013.27.05.png)

However, this domain's review was not the main goal. The reason is that Google AdSense requires the first review (first review after account creation) to use Zone Apex. In other words, subdomains cannot be reviewed[^1].

[^1]: An exception is made for the `www` subdomain.

What I actually wanted to get approved was the `noraworld.github.io` provided by GitHub Pages.

As I mentioned in another [article](./ghost-to-jekyll), I intend to stop using self-managed domains and want to make sure the website continues to exist even if I can't manage it. For that, I wanted to get the GitHub Pages-managed `noraworld.github.io` approved by Google AdSense.

Therefore, I thought of first getting the custom domain, which is the Zone Apex, approved, and then enabling `noraworld.github.io`.

I want to run this blog at `https://noraworld.github.io/blog` instead of `https://noraworld.github.io`. Although it doesn’t have to be Zone Apex for approval of the second or subsequent domains, a website with a subpath cannot be reviewed. It must be at the top-level even with a subdomain.

I'm not overly obsessed with monetizing the blog, but thinking about the possibility of wanting to display ads in the future, doing it later would be bothersome. Once the site is published at `https://noraworld.github.io/blog`, to pass the Google AdSense review, it would need to be once again published at `https://noraworld.github.io`, and after approval, revert back.

Moreover, there are other websites I want to publish via GitHub Pages. If it passes just once at `https://noraworld.github.io`, it should apply to all future GitHub Pages-published websites, so the beginning is crucial. Even if each website needs a review later, changing the URL afterward wouldn’t be necessary, allowing a makeshift start.

### Second Domain Review
So, I decided to have `noraworld.github.io` reviewed. Prior to that, I need to transfer the blog content from `noraworld.blog` to `noraworld.github.io`.

#### Transferring the Blog
`noraworld.blog` was running on Ghost, and `noraworld.github.io` builds with Jekyll. Therefore, I used a tool to migrate from Ghost to Jekyll.

The migration of articles wasn’t too challenging. However, the tool couldn’t import images, so I spent a cumbersome amount of time downloading the entire batch of images from the Ghost server and uploading them all onto the GitHub repository.

Once completed, the articles were finally in a viewable state. Although I haven’t touched the design at all and it’s left in Jekyll’s default theme, I’ll deal with that later and first focus on getting it reviewed.

#### Initial Review
I don’t remember precisely when I initially applied for the review, but I think it was about a month ago (around the end of September).

When I applied for `noraworld.blog`, the results came the same day or 1–2 days after, but the first review of `noraworld.github.io` took over 10 days. The result was "rejection".

![Google AdSense Rejection](https://raw.githubusercontent.com/noraworld/blog-content/main/google-adsense-approval/Screen%20Shot%202021-10-04%20at%2022.15.31.png)

The reason for the rejection was "the site is down or unavailable". Honestly, I had no idea what it meant. As `noraworld.github.io` was always accessible, a site downtime was impossible. GitHub Pages indeed couldn't impose access restrictions.

Mistyping was also mentioned but wasn’t the cause.

#### Identifying the Cause
The rejection reason was cryptic, so I searched based on the rejection statement and found several seemingly solution-oriented articles.

[Solved: Google Adsense Site down or unavailable problem](https://sciencetechstudy.com/site-down-or-unavailable-problem-solved-adsense-godaddy/)

There were many articles, but they mostly suggested the same solutions as the above article.

According to this article, making the following changes would be beneficial:

1. Add a sitemap
2. Ensure `robots.txt` doesn’t block Google crawlers
3. Add the sitemap to Google Search Console
4. Verify the validity of `robots.txt` in Google Search Console
5. Redirect to the `www` subdomain when accessed at Zone Apex

Regarding 5, it’s irrelevant this time, so the main solutions are adding a sitemap and `robots.txt`.

##### Adding a Sitemap
Jekyll has a plugin called [jekyll-sitemap](https://github.com/jekyll/jekyll-sitemap) that automatically adds a sitemap. This plugin is compatible with GitHub's auto-deploy as well.

[GitHub Pages - Dependency versions](https://pages.github.com/versions/)

So, I promptly enabled it.

##### Adding `robots.txt`
Next, for `robots.txt`, it’s simply placing this file at the top level. No plugins are needed. Based on a site example, I added `robots.txt`.

##### Adding to Google Search Console
Then, I checked the sitemap and `robots.txt` on Google Search Console.

For `robots.txt`, there was no issue, but adding the sitemap resulted in an error.

[Sitemap could not be read (Couldn’t fetch) in Google Search Console](https://www.jcchouinard.com/sitemap-could-not-be-read-couldnt-fetch-in-google-search-console/)

An article with exactly the same error suggested just waiting, so I decided to leave it be.

As expected, after almost a week, the error resolved, and the status turned valid.

##### Adding SEO Tags
Additionally, I found articles suggesting adding SEO tags could be beneficial, so I decided to include them.

Regarding SEO tags, a Jekyll plugin is available, making the process as simple as installing and enabling it.

[Optimize your Jekyll powered website with these simple steps](https://vilcins.medium.com/optimize-your-jekyll-powered-website-with-these-simple-steps-b2a24d66a629)

This is also among the plugins targeted by GitHub for automatic deployment.

#### Re-Review
With preparations complete, I applied for re-review.

The result was... “rejection”. As mentioned at the beginning, "the review has not passed yet."

The reason remained "the site is down or unavailable".

Honestly, having tried every solution emerging under the error description, there seemed no further action possible.

Thus, I speculated on potential causes for rejection, with several reasons surfacing.

1. Considered duplicate content of `noraworld.blog`
2. Problems in newly added articles
3. Default sample articles were present

##### Considered Duplicate Content of `noraworld.blog`
The content I'm trying to have reviewed for `noraworld.github.io` is the same as what passed previously for `noraworld.blog`. Therefore, it might be considered duplicate content.

Of course, once `noraworld.github.io` is approved, I plan to implement a redirect for `noraworld.blog`. But since the eventual published URL will have a subpath `/blog`, I thought implementing a redirect right now wouldn't be possible.

However, if this is causing the issue, it would mean the review will never pass. Hence, I thought.

After the formal state (review passed and published as `noraworld.github.io/blog`), I plan to add a 301 redirect for `noraworld.blog`, but presently, maybe I could just put a temporary 302 redirect to `noraworld.github.io`.

A 301 is a permanent redirect, hard to cancel, but with a 302 being temporary, it should be okay.

Once the review passes, I could change the redirect from `noraworld.github.io` to `noraworld.github.io/blog`, and switch from 302 to 301 to solve the issue.

##### Problems in Newly Added Articles
I mentioned earlier that the content of `noraworld.github.io` is the same as what previously passed for `noraworld.blog`, but I've added several articles since then. Perhaps these additions are the problem.

Although I didn't intend for any low-quality articles, copying the previous review scenario is the quickest route in the context of passing a review. So, in pursuing similar conditions to the successful prior situation, I decided to temporarily unpublish newly-added articles.

In Jekyll, by adding `published: false` in the article's YAML header, one can easily make the article unpublished. Incidentally, this very article will remain unpublished until the Google AdSense review passes[^2].

[^2]: Hoping it doesn't end up shelved... 🙏

##### Default Sample Articles Were Present
When setting up Ghost or Jekyll, a sample article is typically included. Perhaps this was deemed "low-quality content".

While I unpublished the Jekyll sample article along with the new articles, the Ghost sample article still remained, so I unpublished it too.

Though when I previously passed the review, this sample article was present, so it might not be an entirely effective approach.

Plus during the last review, the content wasn't altered at all when it passed, so it's possible the guidelines vary slightly depending on the reviewer...

#### Fully Prepared
With several fixes applied, I submitted the review application again. Naturally, the application was rejected, but the review result changed.

![Google AdSense Rejection 2nd Time](https://raw.githubusercontent.com/noraworld/blog-content/main/google-adsense-approval/Screen%20Shot%202021-10-24%20at%2012.48.34.png)

Previously, it stated "the site is down or unavailable," but this time it changed to "insufficient content".

This is somewhat similar to what happened with the `noraworld.blog` review. It might be deemed "low-quality content".

Notably, there's mention of "duplicate content" here for the first time in this review process. However, since the processed content of `noraworld.github.io` is seen so far as duplicate content, likely the issue this time lies simply in being deemed low-quality.

That being said, as previously mentioned, the reviewer's standards might vary, allowing for the possibility of passing with repeated submissions.

#### Success in Multiple Attempts
Updated: Thursday, November 18, 2021

A significant period has passed since submitting the last re-review request, but on November 11th, feedback was returned.

Unfortunately, this time the result was also a rejection, but once again, the review outcome changed.

![Google AdSense Rejection 3rd Time](https://raw.githubusercontent.com/noraworld/blog-content/main/google-adsense-approval/Screen%20Shot%202021-11-18%20at%2015.39.10.png)

This time it clearly states "poor content quality". Therefore, by temporarily unpublishing articles considered low-quality, there's a higher chance of passing the review.

The challenge, however, lies in identifying which articles are considered "low-quality". Google does not provide specifics on which article has issues, leaving one to assess or continuously try unpublishing and reapplying for reviews.

I have a rough idea of which articles might be deemed low-quality, so I'll start by unpublishing those and apply for a review again.

Here are the links included in the section of the review results:

* [Policy tips for creating high quality sites (part 1)](https://adsense.googleblog.com/2012/04/tips-for-creating-high-quality-sites.html)
* [Policy tips for creating high quality sites (part 2)](https://adsense.googleblog.com/2012/09/tips-for-creating-high-quality-sites.html)
* [Webmaster quality guidelines](https://developers.google.com/search/docs/advanced/guidelines/webmaster-guidelines)
* [AdSense Program policies](https://support.google.com/adsense/answer/48182?utm_source=crs&utm_medium=email&utm_campaign=notification)

Clicking on the `low value content` part didn’t respond. The console showed a security-related error.

```
Refused to run the JavaScript URL because it violates the following Content Security Policy directive: "script-src 'report-sample' 'nonce-xxxxxxxxxxxxxxxxxxxxxx' 'unsafe-inline' 'strict-dynamic' https: http: 'unsafe-eval'". Note that 'unsafe-inline' is ignored if either a hash or nonce value is present in the source list.
```

Is this an issue on Google AdSense’s admin page?

### In Conclusion
That’s the current status as of now (2021/10/24). I’ll update further if there are any developments. Hoping this article gets to be published.

Incidentally, from what has been written so far, it might seem like there have only been three attempts in total, but actually, there have been more. As of now, a total of 7 applications have been made.
