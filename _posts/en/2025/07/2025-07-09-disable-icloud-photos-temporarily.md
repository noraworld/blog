---
layout: post
title: "How to Temporarily Disable iCloud Auto Backup When Taking Photos on iPhone"
author: [
  "noraworld"
]
description: "Introducing a method to take photos on your iPhone that you don't want saved to iCloud."
image: "https://noraworld.github.io/box-ivysaur/2025/07/09/0e0a1ecbf87caacaf46bd35bc1aff86e.jpg"
date: 2025-07-09 20:30:00 +09:00
tags: [
  "how-to"
]
published: true
---

### Introduction
There are times when you want to take photos on your iPhone that you don't want saved to iCloud. For such photos, I usually transfer them to my Mac using AirDrop, but it's worrying that they might automatically back up to iCloud between taking them on my iPhone and transferring them to my Mac. It's fine if they are photos that wouldn't be a problem even if stored temporarily in iCloud, but for those that aren't, it's troublesome if they're saved to iCloud only to be deleted afterwards. AirDrop uses Wi-Fi or mobile data, so if you enable Airplane Mode, you can't use AirDrop.

Therefore, this time I'll summarize how to take photos on your iPhone without them being automatically backed up to iCloud as a personal note.

### Steps
The steps are simple: change the settings so the Photos app can't use mobile data, then disable Wi-Fi and enable only mobile data before taking pictures. Here are the detailed steps:

1. Open the Settings app.
2. Select the Mobile Data option.
![](https://noraworld.github.io/box-ivysaur/2025/07/09/20ce93e1cfb036671b19ff3ca8ddcde1.jpg)
3. In the section displaying data usage per app, select Show All.
![](https://noraworld.github.io/box-ivysaur/2025/07/09/1c476000b488112a47698af4c42c5045.jpg)
4. Turn off the switch for the Photos app.
![](https://noraworld.github.io/box-ivysaur/2025/07/09/e15d39fc2daf5bb1f6b02719e3b81f4b.jpg)
5. Turn off Wi-Fi (even if the switch isn't off in the Wi-Fi section of the Settings app, it's fine as long as it's disabled in the Control Center).
![](https://noraworld.github.io/box-ivysaur/2025/07/09/c0359117843086a767c4407a123e58a2.jpg)
6. Open the Photos app and make sure the sync to iCloud is paused.
![](https://noraworld.github.io/box-ivysaur/2025/07/09/0e0a1ecbf87caacaf46bd35bc1aff86e.jpg)
7. Take photos.
8. Transfer them using AirDrop.
9. Delete the photos.
10. Permanently delete the photos from the Recently Deleted items.
![](https://noraworld.github.io/box-ivysaur/2025/07/09/37a90409ed72c8ac40325ef21d48532e.jpg)
11. Make sure there are no photos with paused backup, then enable Wi-Fi again.
![](https://noraworld.github.io/box-ivysaur/2025/07/09/0e0a1ecbf87caacaf46bd35bc1aff86e.jpg)
12. (If you want your photos to usually back up over mobile data) Reverse steps 1 through 4 to enable mobile data usage for the Photos app again.

You can check whether the backup is paused and if there are any paused photos via the profile icon at the top right of the Photos app. If there are no paused items after deletion, you can turn the Wi-Fi back on.

| OK | NG |
| :---: | :---: |
| ![](https://noraworld.github.io/box-ivysaur/2025/07/09/0e0a1ecbf87caacaf46bd35bc1aff86e.jpg) | ![](https://noraworld.github.io/box-ivysaur/2025/07/09/dab0354f8ae13729e8f4564e7a94c033.jpg) |

Note that it's necessary to completely delete photos from the Recently Deleted items in step 9, as failing to do so may prevent the paused items count from dropping to zero. If it doesn't become zero even after this, try restarting the Photos app.

Although the steps are simple, a slight mistake in operation could result in photos being saved to iCloud even momentarily, so caution is necessary. Be extra careful with photos you don't want saved to iCloud even temporarily.

### Bonus
As a side note, I initially thought that disabling iCloud Backup in the mobile data settings would prevent newly taken photos from syncing when Wi-Fi is off. However, for some reason, turning this off still resulted in photos backing up immediately over mobile data once taken. The same applies to iCloud Drive. What could be going on here?

![](https://noraworld.github.io/box-ivysaur/2025/07/09/05db7016f526d946ec4416b7e42c2358.jpg)

Incidentally, there is also a method of temporarily disabling iCloud Photos, but considering reverting the setting immediately after taking photos, it's not practical.

![](https://noraworld.github.io/box-ivysaur/2025/07/09/c5c4cc26c3bc4cda7becb6f0daa4ea98.png)
