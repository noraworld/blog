---
layout: post
title: "Organizing DNS Records for noraworld.com"
author: [
  "noraworld"
]
description: "Reflecting on the records once used for noraworld.com and summarizing the process of organizing them."
image: "https://noraworld.github.io/box-ivysaur/2025/10/06/7d22edad40c0dfe5feb8c9c72fab7419.png"
date: 2025-10-05 03:00:00 +09:00
tags: []
published: true
---

### Introduction
As I mentioned in [Domains I Used to Own as a Domain Enthusiast](https://noraworld.github.io/blog/former-domains), I used to own 15-20 domains, but now I only have `noraworld.com`. I managed various websites in the form of subdomains under `noraworld.com`. Also, some settings for sending system emails from when I ran a Mastodon server were still registered as DNS records. I recently decided it was time to organize them as part of tidying up my online presence. This work is now complete, so I am summarizing the process here for the record.

### The Reason
The trigger was a subdomain of `noraworld.com` that was still registered in the Website (URL) section of the GitHub repository managing the source code for an old diary system. I realized that if I wasn't operating it anymore, I should not only update the URL but also delete the subdomain and other DNS settings. Initially, I considered setting up redirect processes since I still owned `noraworld.com`, but I concluded that since traffic was low, SEO wasn't a big concern. Thus, I decided to delete them altogether for a cleaner setup. More details can be found in [Why I Don't Trust Cloudflare](https://noraworld.github.io/blog/cloudflare-distrust).

### DNS Records Before Organizing
Deleting DNS records impacts the functionality of websites and emails and is irreversible, so I documented them. The websites were either closed or ones I could close, so there were no concerns. However, I had been using the email address with this domain since July 2018, so I made sure to record everything before making changes. The list is as follows.

⚠️ As in [Domains I Used to Own as a Domain Enthusiast](https://noraworld.github.io/blog/former-domains), please note that the IP addresses shown here are no longer under my management, so please do not access them without caution.

| No.  | Type   | Name                                                   | Data                                                                  | TTL    | Priority |
| ---: | :----: | :-----------------------------------------------------: | :-------------------------------------------------------------------: | :----: | :------: |
|    1 | `A`    | `@`                                                    | `185.199.108.153`                                                     | 1 hour |          |
|    2 | `A`    | `@`                                                    | `185.199.109.153`                                                     | 1 hour |          |
|    3 | `A`    | `@`                                                    | `185.199.110.153`                                                     | 1 hour |          |
|    4 | `A`    | `@`                                                    | `185.199.111.153`                                                     | 1 hour |          |
|    5 | `A`    | `blog`                                                 | `133.130.119.194`                                                     | 1 hour |          |
|    6 | `A`    | `diary`                                                | `34.193.61.173`                                                       | 1 hour |          |
|    7 | `A`    | `mastodon`                                             | `34.193.61.173`                                                       | 1 hour |          |
|    8 | `NS`   | `@`                                                    | `ns29.domaincontrol.com.`                                             | 1 hour |          |
|    9 | `NS`   | `@`                                                    | `ns30.domaincontrol.com.`                                             | 1 hour |          |
|   10 | `CNAME`| `aujwxh36le3265fgt4vzzxilh22ptv5u._domainkey.mastodon` | `aujwxh36le3265fgt4vzzxilh22ptv5u.dkim.amazonses.com.`                | 1 hour |          |
|   11 | `CNAME`| `deletegappsnotbefore20180711utc`                      | `case-16314121-for-noraworld.com-at.google.com.`                      | 1 hour |          |
|   12 | `CNAME`| `hcbxfz3tsjjouvwloswwtaykgt73hdaa._domainkey.mastodon` | `hcbxfz3tsjjouvwloswwtaykgt73hdaa.dkim.amazonses.com.`                | 1 hour |          |
|   13 | `CNAME`| `yrbgqtc3epusxf3uopbxo63enjoknlpl._domainkey.mastodon` | `yrbgqtc3epusxf3uopbxo63enjoknlpl.dkim.amazonses.com.`                | 1 hour |          |
|   14 | `SOA`  | `@`                                                    | `ns29.domaincontrol.com.`                                             | 1 hour |          |
|   15 | `MX`   | `@`                                                    | `aspmx.l.google.com.`                                                 | 1 hour |    1     |
|   16 | `MX`   | `@`                                                    | `aspmx2.googlemail.com.`                                              | 1 hour |   10     |
|   17 | `MX`   | `@`                                                    | `aspmx3.googlemail.com.`                                              | 1 hour |   10     |
|   18 | `MX`   | `@`                                                    | `alt1.aspmx.l.google.com.`                                            | 1 hour |    5     |
|   19 | `MX`   | `@`                                                    | `alt2.aspmx.l.google.com.`                                            | 1 hour |    5     |
|   20 | `MX`   | `mastodon`                                             | `inbound-smtp.us-east-1.amazonaws.com.`                               | 1 hour |   10     |
|   21 | `TXT`  | `@`                                                    | `google-site-verification=bp89Vrxvl2qhx3XRYU0gnPmeVGoXEBsXsM2PF8-HdAs`| 1 hour |          |
|   22 | `TXT`  | `@`                                                    | `v=spf1 include:_spf.google.com ~all`                                 | 1 hour |          |
|   23 | `TXT`  | `_amazonses.mastodon`                                  | `XO8q8MpQ9Ix0eYu+Y4RMa1ai1BXPr525s4crW/aky7c=`                        | 1 hour |          |

The "No." is for convenience for further explanation. These numbers do not actually exist, nor is the order important.

<details>
<summary>Screenshots</summary>

<img width="2880" height="9552" alt="Image" src="https://noraworld.github.io/box-ivysaur/2025/09/16/d572782ea1ee85821a0dd755cfac5a4d.png" />
</details>

#### A Records
The most basic records for setting up websites.

Nos. 1 to 4 are GitHub Pages IP addresses. By setting DNS records for a domain you want to use with GitHub Pages like the above, enabling GitHub Pages for the repository, and writing that domain into the `CNAME` file, GitHub Pages becomes available on that domain.

[Managing a Custom Domain for your GitHub Pages site - GitHub Docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)

These were used with the repository [`noraworld/noraworld.com`](https://github.com/noraworld/noraworld.com), but I'd lost motivation for making a portfolio and left it untouched for over five years. During tidying up, I decided there was no need to keep even GitHub Pages and deleted the DNS records.

Nos. 5 to 7 are for the websites on each subdomain, but none are currently active, although you can probably guess their functions from the subdomain names. No. 5 is a ConoHa VPS IP address, and Nos. 6 and 7 belong to Amazon AWS Lightsail. I started with ConoHa VPS, then later switched to AWS after trying Sakura VPS for unrelated purposes.

ConoHa VPS had been canceled long ago, leaving only the DNS records unattended. The Lightsail IP address changed several times. Despite having a Static IP associated with my Lightsail, access issues eventually forced a reboot that changed the IP address. This was probably the third IP address.

#### NS Records / SOA Record
Records specifying which DNS server to query.

Since `noraworld.com` was both registered and managed with GoDaddy and the name server has not been transferred, `NS` at Nos. 8 and 9 use GoDaddy's default settings. Similarly, `SOA` at No. 14 has remained default, with no changes made.

#### CNAME Records
Records assigning aliases (alternate names) to subdomains. They have various uses, which can be easily found by searching, so details are omitted here.

Nos. 10, 12, and 13 are DKIM settings used to send system emails while running a Mastodon instance with Amazon SES.

As for No. 11, I'll elaborate later, but it's unclear. It’s certainly related to Google Workspace (formerly G Suite), but I don't remember the specifics, and even Google Workspace's support team couldn't explain it.

#### MX Records
Records for email settings, enabling the use of custom domain email addresses.

Nos. 15 to 19 are settings to use Gmail with a custom domain via Google Workspace. This setup allows sending and receiving emails through Gmail using a custom domain.

No. 20 is for sending emails through Mastodon, linked to AWS.

#### TXT Records
Memo-like records used for specific purposes, such as verifying domain ownership.

These are various TXT records. No. 21 was prompted by Google to verify domain ownership. By registering this string in a TXT record, it shows that the domain is rightfully owned.

As explained in [How I Acquired the Premium Domain noraworld.com for 300,000 Yen](https://noraworld.github.io/blog/get-noraworld-com), `noraworld.com` was once a premium domain. Although unclear if the previous owner used Google Workspace (then G Suite), I had to prove domain ownership to Google for Google Workspace accessibility after acquiring the domain.

No. 22 is the SPF record for Google Workspace, crucial for preventing sent emails from being marked as spam when using Gmail with this domain. I have kept this since I still use Gmail.

No. 23, if I remember correctly, was to verify domain ownership with Amazon AWS for sending emails through Mastodon. It's similar to No. 22 in purpose but for Mastodon (Amazon AWS version).

### About Google Workspace (Formerly G Suite) Records
While websites were no longer in use, allowing the deletion of A records, and with the Amazon SES settings related to Mastodon also removable since it was no longer operational, the Google Workspace settings caught my attention.

I learned during this DNS organizing process from help pages that, post-2023, Google Workspace now directs setting `smtp.google.com` as a single MX record.

[Setting Up MX Records for Google Workspace - Google Workspace Admin Help](https://support.google.com/a/answer/16004259?hl=en)

Previously, back when our domain began Google Workspace (then G Suite) usage in July 2018, the five MX records were required as shown above.

So, previously:

| Type | Name | Data                      | TTL     | Priority |
| :--: | :--: | :------------------------:| :-----: | :------: |
| `MX` | `@`  | `aspmx.l.google.com.`     | 1 hour  |    1     |
| `MX` | `@`  | `aspmx2.googlemail.com.`  | 1 hour  |   10     |
| `MX` | `@`  | `aspmx3.googlemail.com.`  | 1 hour  |   10     |
| `MX` | `@`  | `alt1.aspmx.l.google.com.`| 1 hour  |    5     |
| `MX` | `@`  | `alt2.aspmx.l.google.com.`| 1 hour  |    5     |

Now, it’s:

| Type | Name | Data              | TTL     | Priority |
| :--: | :--: | :---------------: | :-----: | :------: |
| `MX` | `@`  | `smtp.google.com.`| 1 hour  |    1     |

It's much simpler. If domains or accounts established before 2023 can switch to the updated record, it would significantly tidy up the setup. If undergoing such an organizing process, an update to the simplified new MX records seemed worthwhile.

Moreover, for Google Workspace (then G Suite) related records No. 11 and No. 21, although previously considered for deletion after domain verification, I wasn't entirely certain since they'd remained unchanged since July 2018.

Therefore, I decided to consult with Google Workspace support. This instance is where a paid version with comprehensive support comes in handy. Initially, I trusted AI responses but recognized the risk of AI errors; DNS record modification/deletion carries high risk, and operations could potentially disrupt ongoing Gmail usage. For accuracy, I opted to inquire directly with the support team. [^google_workspace_support]

[^google_workspace_support]: Personal Note: [Seeking Confirmation on DNS Record Deletion and Updates](https://support.cloud.google.com/portal/cases/details;name=customers%2FC01b5sgj1%2Fcases%2F63332382)

#### Support Response
The support team provided the following response.

Regarding MX records, they confirmed that the new record `smtp.google.com.` was usable even for domains and accounts created before 2023. The steps for implementing this are as follows:

1. Add `smtp.google.com` to MX records.
2. Wait longer than the TTL to ensure DNS changes propagate.
3. Delete the existing five MX records (Nos. 15-19).

Even though simply waiting for the TTL would suffice, I took extra caution and waited over 72 hours, as cited in the [help page](https://support.google.com/a/answer/16004259?hl=en), at each DNS record change stage. Gmail had no downtime, and everything functioned properly post-change.

The TXT record for No. 21 already verified domain ownership and was safe for deletion, as confirmed by the support team.

As for the CNAME record No. 11, the support team couldn't identify its purpose but confirmed it wasn't necessary for email settings, allowing for deletion. Despite the elapsed time, I still associate it with Google Workspace (then G Suite) due to the `google` keyword. However, the domain ownership should have been fulfilled by No. 21 alone, leaving its purpose unclear. Scanning past emails didn't provide further insights. It's a mystery.

Regardless, No. 21 and No. 11 were deleted while confirming no adverse effects, which seemed reassuring.

Aware of the necessity, I verified I shouldn't delete No. 22 and received confirmation to keep it intact. Thus, I duly retained it.

[Setting Up SPF - Google Workspace Admin Help](https://support.google.com/a/answer/33786?hl=en)

### DNS Records After Organizing
Here’s the final outcome—remarkably tidy. A and CNAME records were thoroughly scrubbed. Subdomains also vanished, naturally, as websites stopped using them.

| Type | Name | Data                                 | TTL     | Priority |
| :--: | :--: | :----------------------------------: | :-----: | :------: |
| `NS` | `@`  | `ns29.domaincontrol.com.`            | 1 hour  |          |
| `NS` | `@`  | `ns30.domaincontrol.com.`            | 1 hour  |          |
| `SOA`| `@`  | `ns29.domaincontrol.com.`            | 1 hour  |          |
| `MX` | `@`  | `smtp.google.com.`                   | 1 hour  |    1     |
| `TXT`| `@`  | `v=spf1 include:_spf.google.com ~all`| 1 hour  |          |

<details>
<summary>Screenshots</summary>

<img width="1073" height="772" alt="Image" src="https://noraworld.github.io/box-ivysaur/2025/10/05/11bc3973b7d42874651a974423ed4ae1.png" />
</details>

### Conclusion
The Google Workspace support team pointed out that while transitioning to the new MX record posed no issues, it wasn’t necessary unless desired. Likewise, outdated or obsolete records may remain unless causing practical issues. However, AI responses suggested avoiding erroneous deletions of essential records. For some, the risk of accidental deletion offers enough reason to leave them be.

Nonetheless, leaving unnecessary settings indefinitely feels uncomfortable. The same goes for outdated and redundant records. Borrowing an analogy, "not cleaning the bathroom because it'll just get dirty again" doesn't sit right with me. Tidying up provides a sense of accomplishment and relief once completed.

I’ve relinquished domains other than `noraworld.com` [^domain_decluttering], and with minimal DNS records now on `noraworld.com`, I feel I've embraced a "legacy" positively or negatively. Though digital legacies abound, if I can sort everything before I die, that would be ideal.

[^domain_decluttering]: Though, this was done quite a while ago.
