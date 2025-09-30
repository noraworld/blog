---
layout: post
title: "Can't Believe What Happened with mail.com"
author: [
  "noraworld"
]
description: "I lost my email address because my mail.com account was deleted. This is my frustration about it."
image: "https://noraworld.github.io/box-ivysaur/2025/09/30/0dac85c6608b620d29dcab58d4501c75.png"
date: 2025-09-30 16:15:00 +09:00
tags: []
published: true
---

My `mail.com` account got frozen. I'm in the middle of contacting support, but it seems like it won't come back.

Right now, I use Gmail for my email needs. However, I have a paid Google account, Google Workspace, and I use a custom domain for my email address. I've been using the domain I got in July 2018 for over 7 years now with Google Workspace.

I really like this email address. It's got my long-used internet username as a domain and a simple local part[^local_part]. I've grown attached to it over the years.

[^local_part]: The part before the `@` in an email address. In `mail@example.com`, `mail` is the local part.

Recently, I've started thinking again that maybe I shouldn't use a custom domain. This isn't a new thought; I felt this way before, and that's why I don't use a custom domain for websites anymore. Recently, I've organized my DNS records for my main domain and deleted all A records. I haven't set up any CNAME for GitHub Pages either; I use the default `github.io` for this blog.

But for email (MX records), since I use it every day, I never thought of stopping. I don't maintain a portfolio anymore, and my blogs and journals have always been on `github.io`. But since I use email every day, I can't just stop. Changing my email address now would be a huge task since I've used it for so many online accounts. It's like moving on the internet. Even with a grace period, I would need to transition everything eventually. It's a massive undertaking.

With websites, the idea was to avoid using a custom domain for longevity without management costs. But for email, since I check it myself, it's only necessary while I'm alive. After I'm gone, it's okay if emails don't reach me. It's just for me, so if I'm not checking, it's unnecessary.

However, it bothers me that there's a recurring cost. I'm paying about 3,000 yen a year to renew the custom domain, plus 3,000 yen a month for Google Workspace. It's not for business, so it's out of pocket.

This leads to the fear of "what if I can't continue paying for the service?" Google Workspace might allow resuming service after payment, but for a custom domain, if you don't renew, it might get taken by someone else. If that happens, unless they let go of it, you can never use that email address again. If they even create the same email on another service, emails meant for me could go to them.

You might think just keep paying, but if you can't or decide not to, you'd lose that email address. And this risk grows the longer you use the email. The longer you use it, the more connections you have, so you're compelled to keep paying these running costs indefinitely.

Plus, there's no guarantee services will always deliver at the same price. Google Workspace's cost has risen over the years. When I checked my subscription history, it showed that as of March 26, 2022, Google Workspace cost 1,360 yen/month[^before_2022], and now (as of my August 2025 bill) it's risen to 3,300 yen/month. The recent hike might be due to a weak yen, but it's been creeping up even before that. It's likely that the cost of Google Workspace (formerly G Suite) itself is rising. I can't justify continuing to pay for it just because I have an email address, which is exactly what Google wants.

[^before_2022]: It was probably cheaper before that, but I'm not digging up old records just to explain this now.

While I plan to write another post about this, I'm now organizing DNS records related to my main custom domain and Google Workspace. During this, I questioned if maintaining the email long term is necessary.

To reduce dependency and costs, I could use a free email. Most non-business users likely do this. The most straightforward choice would be to stop using Google Workspace, create a free Google account, and use Gmail there. With Gmail, the differences between free and paid are likely just the custom domain, AI features (Gemini), and storage capacity. In terms of usability, they should be the same.

However, that raises the concern: is it okay to rely so heavily on Google? Google is super convenient with lots of services. With the extra storage, I use Google Drive a lot. On Mac (I don't know about Windows or Linux), the desktop app mounts it like a NAS without downloading all files, making it super convenient. [^dropbox]

[^dropbox]: Maybe other storage services offer this too? I haven't used Dropbox since switching to Google Drive, so I don't know.

But linking many services to one account is risky. If something happens to that account, I lose everything. Losing access to storage (Google Drive) and email (Gmail) would be catastrophic, so I want to lessen this dependency.[^not_hate_google_per_se]

[^not_hate_google_per_se]: It's not that I want to avoid Google. Their services are great, and I want to use them. But I don't want to rely on one service for critical things like storage and email.

Regarding email, I thought of reviving `mail.com`, which I used back in college. After using Google Workspace, it got neglected, but I kept the login info safe, and I like the email address second only to my current main one. Reviving it seemed like a solution.

But, when I tried to log in, I couldn't. It said the email address or password was incorrect. I've saved those in 1Password, so that's unlikely. When trying to reset the password, it required sending a code to a phone number, which seemed unfamiliar and showed Vietnam's country code.

Feeling uneasy, I contacted support. The initial response was just a typical FAQ, like "try these before reaching out." Basically, "don't bother us unless necessary." My situation wasn't addressed, so I replied asking for human support.

Their reply: "Your account was deleted due to 6 months of inactivity, as per our terms. Once deleted, you might not be able to use the same email address." Really??

This response was disappointing. `mail.com` lets you get `@mail.com` addresses for free, which is about the simplest and most elegant domain. That's why I picked it over Gmail back in college. It offers other simple domains like `@email.com`, `@asia.com`, and more, primarily for free.

Long inactivity leading to such policy is frustrating, especially for such a neat domain. I logged into Yahoo.com recently (far more neglected than `mail.com`), and it was only inactive until next login, not deleted. Filing the same fate for `mail.com` after just 6 months seems harsh.

Is 6 months too short? An unexpected accident causing a temporary incapacity could go over 6 months. Emails manage access to countless online services, yet something so critical can be erased easily, making me wary about using this service.

Back when I steadily used it, this issue never arose. Even if I somehow get the address back, this makes me second-guess making it primary again. The appeal's gone.

More than service name-bearing domains like `@yahoo.com`, `@mail.com` should be handled better. Unfitting for its brilliant domain, it should transition to a reliable company. Historically, I only used it for the great domain and never thought highly of the service. It's inadequate for a domain of this caliber.

Moreover, the mismatch of an unknown phone number during reset, versus "can't reuse the email" isn't clarified. If deleted for inactivity means letting anyone claim it, why a mystery number linked during reset? No other service compromised my 1Password data, and the password strength defies easy breach. Their "account deleted" statement rules out a hack.

Perhaps after account deletion, the email becomes reclaimable, explaining subsequent ownership by someone else, hence unavailable for me. Asterisk-laden stuff might mean "can't reuse due to someone else taking it," leaving this ambiguity.

Despite ongoing correspondence, I'm arguing this perturbs other linked services that entail this email. The "reclaimable" issue heightens as well. 

Hopeful of using `mail.com` again from this restructuring idea, aspirations now shattered.

Unhappy with blogging services means switching options, not limited by the vast spectrum. Changing email, however, disrupts the ecosystem of login access, laden with its system of domain restrictions – bad service with premium domains is nauseating. I wish it moves to a credible firm.

Assuming an advance notification of deletion, coming via the unused email, won't reach us. Email, unlike others, warrants deletion caution, yet act aloofly. Ironically, usernames on Twitter or Instagram linger inactive for years, unstirred beyond a decade when email can't make 6 months…

Big company risk redundancy persuades exclusive email provision, yet elusive mails yield distinct threats here, rendering trust groundless …
