---
layout: post
title: "Google AdSense Review Checklist"
date: "2021-10-26 13:47:36"
tags:
published: true
---

The Google AdSense review process seems to be getting stricter each year. Furthermore, if your application is rejected, you're not given specific reasons, making it unclear what needs to be fixed. 

As a result, you often have to gradually repair potential issues indiscriminately. Here, I've compiled a checklist of items to verify during that process.

Some items with low certainty are mentioned in articles about getting approved for Google AdSense, but it's unclear if they truly have any effect.

### Certainty: High
* Ensure that ad codes are correctly placed
    * Verify that they are installed on every page being reviewed
    * Ensure they are placed between `<head>` and `</head>`
* Check for any policy violations
    * Refer to "[About Policies](#ポリシーについて)" section below
* Add a `robots.txt` file
    * Make sure it does not block Google's crawlers
* Check the effectiveness of `robots.txt` using Google Search Console
* Categorize content
    * Clearly distinguish between articles and other types of pages (such as profile or contact pages)
    * Consider using a menu bar for clear distinction
* Exclude login pages from the review target
    * Specifically ensure the following:
        * Add URLs for login pages, etc., to `Disallow` in `robots.txt`
        * Do not place ad codes within `<head>` of login pages
        * Exclude login pages from the sitemap or feed
    * If login pages are reviewed, they might be considered low-quality content
    * Besides login pages, if hosted on GitHub Pages, check that README, Gemfile, etc., are not mistakenly published

### Certainty: Medium
* Add a feed
    * In case of Jekyll, you can use [`jekyll-feed`](https://github.com/jekyll/jekyll-feed)
        * [Available with GitHub Pages auto-deploy](https://pages.github.com/versions/)
* Add SEO tags
    * In case of Jekyll, you can use [`jekyll-seo-tag`](https://github.com/jekyll/jekyll-seo-tag)
        * [Available with GitHub Pages auto-deploy](https://pages.github.com/versions/)
* Add a sitemap
    * In case of Jekyll, you can use [`jekyll-sitemap`](https://github.com/jekyll/jekyll-sitemap)
        * [Available with GitHub Pages auto-deploy](https://pages.github.com/versions/)
* Add a sitemap to Google Search Console and confirm it is effective
    * Initially, an error saying "Couldn't fetch" might occur, but if no issue, it will become valid automatically in 1-2 weeks
* If relocating from another blog (different URL) with the same content, incorporate redirect processing on the previous blog
    * If redirecting is undesirable purpose solely for review, use a 302 redirect instead
* If the review domain includes `www`, ensure that accessing without `www` redirects to with `www`
    * Example: `example.com` → `www.example.com`
    * It's not mandatory to have `www`, but if used, ensure redirect processing for access attempts without `www`

### Certainty: Low
* Add a contact page
    * Might slightly increase approval chances, but not essential for passing
* Add a privacy policy page
    * Might slightly increase approval chances, but not essential for passing
* Add author location, affiliation, and profile information
    * Not essential to provide location and affiliation, but a profile page might be beneficial
* Implement a comment feature
    * Can use external tools like Disqus
* Categorize articles
* Add a breadcrumb trail
    * Might slightly increase approval chances, but not essential for passing

### Items not subject to review
* Number of articles
    * It’s said that even around 5 articles can pass the review
    * More articles might cause:
        * More content to review increases chances of issues being flagged, leading to rejection
        * Hard to identify which article has an issue if rejected
* Period before re-review
    * Rumors suggest waiting a bit before applying again after rejection, but it's not related
    * Feel free to apply for review immediately after fixing issues upon rejection notice
* Affiliate marketing
    * Having affiliate articles doesn’t mean rejection; it’s a misconception
    * However, excessive promotion might lead to low-quality content perceptions
* Photos
    * No issue with featuring photos
    * Unapproved reproduction from other sites might cause policy violations and rejection

### Points for passing review
* Try not to alter site content during review
    * Not that changes lead to rejection, but it might delay the review
* Ensure stable site availability
    * Temporary unavailability or poor responses during review might make passing difficult
* Try reducing the number of articles
    * High article count makes identifying problematic ones hard; set doubtful articles as private temporarily
    * No need to delete; just set as non-public through CMS or blog settings

### About Policies
“Check for any policy violations” is among "Certainty: High" items, but explaining specific procedures isn't feasible.

Therefore, I can only advise reading documents detailing Google AdSense policies.

Key points to note are the following three:

* Ensure no low-quality content
    * Thin content articles (too few words)
    * Articles perceived as not valuable enough to display ads
* Ensure no plagiarized content from other sites
    * Reproductions
    * Contents almost identical to other sites (lack of originality)
* Ensure no misleading guidance 
    * Mixing article pages with other pages
    * Indistinguishable navigation from external sites

Here are some documents related to Google AdSense policies:

* [How to get your site approved for AdSense?](https://www.youtube.com/watch?v=lZUG0XGlZZY)
    * YouTube video (English)
    * Concise points to pay particular attention to
    * This video covers everything mentioned here
* [AdSense Program policies](https://support.google.com/adsense/answer/48182)
* [AdSense Site Approvals series](https://www.youtube.com/playlist?list=PLbAFD4oU9Ycr4j1pViNjkS82rhbF293H8)
    * YouTube video play series on site approval procedure (English)
* [Google AdSense Help Community](https://support.google.com/adsense/community)
* [Your AdSense Page](https://support.google.com/adsense/answer/10568458)
