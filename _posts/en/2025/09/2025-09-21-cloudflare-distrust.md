---
layout: post
title: "Cloudflare Can't Be Trusted"
author: [
  "noraworld"
]
description: "I logged into Cloudflare for the first time in about nine years. I found it to be quite unfriendly, with many dangers that could potentially lead to account lockout. Here’s a summary of my complaints."
image: "https://noraworld.github.io/box-ivysaur/2025/09/21/ca4d56a675d919e345c8e3a90c332141.png"
date: 2025-09-21 14:00:00 +09:00
tags: []
published: true
---

### Introduction
Recently, I logged into Cloudflare after a long time because I wanted to consider transferring my domain to Cloudflare or setting up DNS on Cloudflare. I ultimately decided it wasn't necessary, but during this process, I became skeptical about using Cloudflare. Here’s why.

### Purpose
Let me explain my purpose in more detail.

#### About the Main Domain I Use
I own a domain called `noraworld.com`, managed with GoDaddy. I acquired it on July 1, 2018. More details are in a blog post from that time.

[Paid 300,000 Yen for the Premium Domain noraworld.com - Noraworld Blog](https://noraworld.github.io/blog/get-noraworld-com)

I've used this domain as my main one, but as noted in another post, [Migrated Blog from Ghost to Jekyll - Noraworld Blog](https://noraworld.github.io/blog/ghost-to-jekyll#%E7%8B%AC%E8%87%AA%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AF%E4%BD%BF%E7%94%A8%E3%81%97%E3%81%AA%E3%81%84), I’m now reducing the usage of custom domains. However, I've continued to use this domain with a Google Workspace account, originally a G Suite, making `noraworld.com` my primary Gmail address.

#### Attempted to Set Up Redirects
Since I'm no longer using the website, I thought about cleaning up by deleting DNS records. However, I considered redirecting traffic to the current website instead. After learning from ChatGPT that GoDaddy supports redirects, I tried it out.

However, it wasn't what I expected. It only redirects the root, not specific paths. For example, it can redirect `blog.noraworld.com` to `noraworld.github.io/blog/`, but not `blog.noraworld.com/slug` to `noraworld.github.io/blog/slug`. Accessing a specific path results in a 404 error.

I researched if other registrars offered better options. Having owned 15-20 domains managed by different registrars, including Google Domains (now transitioned to Squarespace), I checked Squarespace.

Unfortunately, Squarespace didn't support wildcard redirects either, confirmed by their quick-responding support. Their service was incredibly fast; it didn't use live chat but provided responses within an hour by email.

For Squarespace, redirects could be set up for specific paths but not as wildcards like `blog.noraworld.com/$1` to `noraworld.github.io/blog/$1`. During my research, Cloudflare was the only major registrar with this capability, motivating me to consider using them.

### Previous Use
This wasn't my first time using Cloudflare. Around nine years ago as a student, GitHub Pages didn’t support HTTPS, and I used Cloudflare to achieve HTTPS indirectly. I wrote about this back in October 2016.

[SSL for GitHub Pages with Cloudflare - Noraworld Developers Blog](https://noraworld.github.io/devlog/use-ssl-on-github-pages-with-cloudflare)

Once GitHub Pages offered HTTPS support, I stopped using Cloudflare. It's been about nine years since I created my Cloudflare account, which I haven’t used since.

### Logging In Again
When I logged in this time, I wanted to update outdated information like the email address. I encountered issues changing my email.

#### Struggling with Email Change
Initially, I couldn’t change my email because it required authentication from the old email (clicking a link in an email).

The old email was Yahoo.com (not Yahoo! JAPAN). I logged into Yahoo.com, which I hadn’t used in a while, to find messages could no longer be received, a common Yahoo feature for inactive accounts. After reactivating the account, I still didn’t get the authentication emails, so I contacted Cloudflare.

It took a few days for Cloudflare to respond, ultimately allowing the email to come through. Without detailed explanations, it seemed prolonged inactivity had blocked email sending.

#### Strengthening Security, Backups, and Verifications
I then set up two-factor authentication, saved API keys securely, and verified domains. No domains were registered, probably because I’d let go of almost all domains except for `noraworld.com`, which itself wasn’t associated with Cloudflare.

### Decided Not to Use Cloudflare
After re-assessing my account, I decided I didn’t need Cloudflare. My domains weren’t actively used, and redirects weren't necessary. Using an old URL with redirects doesn't ensure a permanent solution.

### Distrust in Cloudflare
The issues I faced led to distrust in Cloudflare. Here's why:

#### What If You Can't Access Your Old Email?
My main concern is, what if you can’t access your old email? You need it to authenticate for essential actions like changing emails or accessing domains, which is problematic if you lose access.

I stored my login info, preventing issues this time. But if it had been an older email, I might have been locked out. Security concerns leading to accessibility issues aren't ideal. Being blocked by security is ironically insecure.

#### Handling Errors Is Too Unfriendly
Also, Cloudflare was unfriendly when errors occurred. When I didn’t receive the authentication email, I had no indicator that Cloudflare was withholding it. Even after Yahoo reactivated, emails didn’t arrive, confirmed only after contacting Cloudflare.

Their resend button can lock you out with no error message—just a console error 429 Too Many Requests. An average user wouldn’t check the console, potentially contacting the wrong support. The same retries leading to another lock made it all more tedious.

#### It's Hard to Use and Risky
Then there's compatibility issues. I couldn’t type in the email change field with my extension, Video Commander, enabled. Disabling it worked, suggesting Cloudflare uses custom fields instead of standard ones.

Additionally, changing passwords was problematic. I was logged out mid-process, not realizing until my password manager had updated to the new one. Fortunately, I could revert it, but if not, I’d be locked out, fearing I wouldn’t get the reset email.

### Conclusion
Cloudflare’s unfriendly and risky issues deterred me from transferring my main domain there, even for wildcard redirects. Setting up my own server for this wasn’t viable, so I would have searched elsewhere.

Previously, Cloudflare worked smoothly for HTTPS on GitHub Pages. But recent use has been frustrating, making me distrust a seemingly popular service.

While I might not need to redirect anymore and have decided against Cloudflare, I’ll avoid their services like their DNS (`1.1.1.1`) as well. Goodbye, Cloudflare.
