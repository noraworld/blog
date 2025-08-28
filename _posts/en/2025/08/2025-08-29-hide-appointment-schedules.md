---
layout: post
title: "How to Hide Only the Appointment Slots in Google Calendar"
author: [
  "noraworld"
]
description: "If the appointment schedules on Google Calendar are cluttering the calendar with too many entries, here's how you can hide them."
date: 2025-08-29 01:43:00 +09:00
tags: [
  "how-to"
]
published: true
---

### TL;DR
You can turn off the appointment slots by following these steps:

1. Open Google Calendar in your browser.
2. Click the drop-down menu where you can switch views like day, week, month, or year.
3. Uncheck "Show appointment schedules" at the bottom of the drop-down menu.

Here are some additional notes:

* You can still use the appointment schedules even if you hide the slots.
* Not supported on iPhone app (I'm not sure about Android).



### The Convenience of Appointment Schedules
Google Calendar has a feature called "appointment schedules." This allows others to book appointments with you during times you've pre-set. For example, during job hunting, you can share a link to your appointment schedule with HR. They can then book a meeting at a time you're free, which eliminates tedious exchanges like:

* HR: "Please tell us your available times."
* You: "I'm available on XX day from △△ to □□ and on ●● day from ▲▲ to ■■..."
* HR: "Let’s schedule for ●● day from ▲▲ to ■■. Please confirm."
* You: "Thanks for arranging. Looking forward to it."

This simplifies communication and saves time, making it a win-win for both sides. Some might find this impersonal, but you don’t need to worry about those who don’t appreciate productivity.



### The Problem with Appointment Schedules
Despite being useful, appointment schedules have one downside: they display too many slots.

![Calendar with visible appointment slots](https://noraworld.github.io/box-ivysaur/2025/08/28/48c11890a78948d21b441fb311220b96.png)

These aren’t actual appointments but available slots set by the appointment schedule feature. For instance, the times at 12, 15, and 17 in the image above are just open slots for bookings.

Seeing both real appointments and empty slots together is confusing. Plus, these slots simply show availability, which being displayed constantly doesn’t make sense. If you set many slots, your calendar can end up looking cluttered.

I wanted to hide these, but finding the solution wasn’t easy. So, I'm sharing how to do it here as a memo.



### How to Hide Appointment Slots
It's easy to set up. Just open Google Calendar in your browser, click the drop-down menu that lets you switch views, and uncheck "Show appointment schedules" at the bottom.

| English | Japanese |
| :---: | :---: |
| ![Hide appointment slots (English)](https://noraworld.github.io/box-ivysaur/2025/08/28/768bdd75aa94b65b9b20938a550fbf29.png) | ![Hide appointment slots (Japanese)](https://noraworld.github.io/box-ivysaur/2025/08/28/ad98d5b857291899a28a5ca33e92e6bb.png) |

Once unchecked, your slots will be hidden.

![Calendar with hidden appointment slots](https://noraworld.github.io/box-ivysaur/2025/08/28/d7ea5ebffd57c7630d728dbba6c7c5fa.png)

Don’t worry—this only hides the slots. Appointment schedules themselves are still active, and your shared links will keep working. Real appointments booked via these links will still show up.

![Appointment schedule](https://noraworld.github.io/box-ivysaur/2025/08/28/3bea8f8e8b3322f8b57d64257e656284.png)

It’s a simple fix, but why is it so hard to find this information? I even got incorrect info claiming it "can't be done" from [ChatGPT](https://chatgpt.com/share/68b08316-650c-8004-99ca-1cf0955e5f41), and misleading instructions from [Google Gemini](https://gemini.google.com/app/d2a61c40fb6a3296) [^gemini] before finally getting the answer. It seems quite unhelpful for a big name like Google.

[^gemini]: Google Gemini doesn’t allow link generation with Google Workspace (paid edition) accounts because of limitations. It's surprising that a paid version lacks such a feature.

Note that this method **only works in the browser, not the iPhone app**. I’m not sure about Android, since it might be incentivizing people to choose Android over iPhone. Such a great feature, it’s a shame.

### The Inconvenience of Appointment Slots
Also, while you can set intervals to avoid back-to-back bookings (like avoiding a 12 to 1 PM booking right after a 1 to 2 PM one), this feature feels a bit clunky. The slots start as if back-to-back booking isn’t possible.

For example, if you set 1-hour slots between 12 PM and 8 PM with a 1-hour interval, appointments can’t be consecutive. If you have a 12 to 1 PM appointment, the next open slot begins at 2 PM.

While this is logical, if a slot starts at 12, booking between 13 and 14 isn’t available even if the earlier slots are empty. It's no surprise, it's always unavailable initially.

Is it challenging to design a system where overlapping isn’t a thing? Even using external resources could cause scheduling delays. Yet, if Google oversees all, it seems plausible to let bookings reschedule automatically after confirming slots don’t conflict.

I've been a bit ranty towards the end here. Despite it all, I’ve detailed how to hide appointment slots in Google Calendar. It's a handy feature and deserves some improvement.



### The Evolution and Clash of Scheduling Tools
Before Google Calendar's launch of this feature, many scheduling services competed, making users unsure of which to choose. Many offered free versions but charged for detailed scheduling options. Subscribing during a job hunt for rare appointments seemed unnecessary, especially without steady income.

That's why I was happy when a major company like Google added this feature to a tool as widely used as Google Calendar. I used to rely on [YouCanBookMe: Free Online Scheduling Tool](https://youcanbook.me/), but now that Google Calendar has added this function, I no longer need it.
