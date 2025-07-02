---
layout: post
title: How to Solve the Browser Version of 1Password Not Integrating with the Desktop Version
image: "https://raw.githubusercontent.com/noraworld/blog-content/main/1password-desktop-app-integration-not-work/Screen-Shot-2021-08-25-at-21.11.11.png"
date: '2021-08-25 12:58:01'
published: true
---

### Introduction
On the company PC, I use different browsers for work and private use. I use Google Chrome for work and Google Chrome Beta for private use.

With the Google Chrome that was first installed on the PC, integration with the desktop version of 1Password was possible from the start, but for some reason, it couldn't integrate with Google Chrome Beta.

I contacted 1Password about this issue, and they provided a solution, so I'm documenting the method as a memo.

### Benefits of Integration
In short, for MacBook users, it allows the use of Touch ID (fingerprint authentication).

In the desktop version, by enabling Touch ID in settings, you can unlock instead of entering the master password. The browser version can use the same functionality by turning on the integration with the desktop version.

![](https://raw.githubusercontent.com/noraworld/blog-content/main/1password-desktop-app-integration-not-work/Screen-Shot-2021-08-25-at-21.16.23.png)

For security reasons, I want 1Password to automatically lock after 5 to 10 minutes. However, typing the master password every time is annoying. Therefore, unlocking with Touch ID is extremely valuable.

### Enable the Setting
Of course, if the setting is not enabled, it cannot be used, so first enable it in the settings.

Desktop:

![](https://raw.githubusercontent.com/noraworld/blog-content/main/1password-desktop-app-integration-not-work/Screen-Shot-2021-08-25-at-21.22.06.png)

Browser:

![](https://raw.githubusercontent.com/noraworld/blog-content/main/1password-desktop-app-integration-not-work/Screen-Shot-2021-08-25-at-21.11.11.png)

Note: In Japanese, it's called "1Password App Integration."

Normally, this should allow you to use the integration feature, but sometimes it doesn't work properly, possibly when using Google Chrome Beta or multiple browsers. In such cases, try the method introduced below.

### Copy the JSON File for Desktop Integration
Open Terminal and execute the following command.

```shell:Shell
cd ~/Library/Application\ Support/Google/Chrome/NativeMessagingHosts
mkdir -p ~/Library/Application\ Support/Google/Chrome\ Beta/NativeMessagingHosts
cp 2bua8c4s2c.com.agilebits.1password.json com.1password.1password7.json ~/Library/Application\ Support/Google/Chrome\ Beta/NativeMessagingHosts
```

Then, restart Chrome Beta and 1Password (desktop app).

After restarting, confirm that the desktop integration is enabled.

If you are using a browser other than Chrome Beta as shown below, replace `~/Library/Application\ Support/Google/Chrome\ Beta/NativeMessagingHosts` appropriately.

* Google Chrome Beta: `~/Library/Application\ Support/Google/Chrome\ Beta`
* Google Chrome Dev: `~/Library/Application\ Support/Google/Chrome\ Dev`
* Google Chrome Canary: `~/Library/Application\ Support/Google/Chrome\ Canary`
* Microsoft Edge Beta: `~/Library/Application\ Support/Microsoft\ Edge\ Beta`
* Microsoft Edge Dev: `~/Library/Application\ Support/Microsoft\ Edge\ Dev`
* Microsoft Edge Canary: `~/Library/Application\ Support/Microsoft\ Edge\ Canary`

### Reference
https://support.1password.com/could-not-connect/
