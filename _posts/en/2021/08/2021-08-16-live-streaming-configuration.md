---
layout: post
title: Notes on YouTube Live Streaming Settings for Playing Online Games with Friends
image: "https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/streamlabs_obs.png"
date: '2021-08-16 13:27:13'
published: true
---

### What This Article Is About
There have been several occasions when I've played online games with friends and colleagues on my days off, and I plan to continue doing so in the future.

Moreover, as a record of my gameplay and memories, I always stream on YouTube Live whenever I play games.

However, I often get bogged down, mainly with audio adjustments, during the setup each time.

Therefore, to minimize hassle in the future, I decided to jot down the settings that worked well when everything was in sync.

This is primarily a personal memo, not written for anyone else, but I hope it might be of reference to anyone who stumbles upon it.

Additionally, I will update this article if I change my settings.

### Equipment Used
* MacBook Pro
* Blackmagic eGPU Pro
  * eGPU (AMD Radeon RX Vega 56)
  * An eGPU might not be necessary, but since real-time encoding during live streaming is intensive, it could be beneficial.
* CAM LINK
  * Capture board
  * Previously connected to the GPU side, but due to regular image disruptions, I use a USB-C to USB-A adapter to connect it to the MacBook.
* Audient EVO 4
  * Audio interface
* SHURE SM7B
  * Dynamic microphone

### Applications and Services Used
* Streamlabs OBS
  * Streaming software
* LadioCast
  * Virtual audio mixer
* Soundflower
  * Virtual audio
  * Tried BlackHole, but for some reason, sound from the Mac (other people's voices on Google Meet) became noisy (choppy), so I've continued using Soundflower.
* Google Meet
  * For conversations

### Streamlabs OBS Settings
#### Audio Source Settings
![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-15-at-22.14.39.png)

Prepare the following three audio sources:

* Soundflower (2ch)
  * Volume: 100% (0.0 dB)
  * Noise Suppression
      * RNNoise
  * Gain
      * 7.5
  * Compressor
      * Ratio: 10
      * Threshold: -18
      * Attack: 6
      * Release: 60
      * Output Gain: 0
      * Sidechain/Ducking Source: None
* My Voice
  * Volume: 100% (0.0 dB)
  * Noise Suppression
      * RNNoise
  * Gain
      * 10
  * Compressor
      * Same as Soundflower
* Game Audio
  * Volume: 70% (-11.2 dB)
  * No filters on game audio

#### Displaying Performance Metrics
By linking your YouTube account within the app, Streamlabs OBS settings can sync with other devices. So typically, as long as you don't tweak settings, there shouldn't be any issues.

However, the display of CPU usage, FPS, dropped frames, and upload data at the bottom left isn’t synced, so when setting up a new device, manually add them.

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-16-at-21.36.59.png)

Especially with FPS, if the streaming environment detects issues, it may change on its own (it was once automatically changed from 60 FPS to 30 FPS), so it's advisable to display it.

#### Streaming Quality Settings
These settings should sync through account linkage, but when I tweaked them previously, errors started appearing on YouTube Live, so double-check to ensure the settings are correct.

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-16-at-22.09.26.png)

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-16-at-22.09.55.png)

* Set Base (Canvas) Resolution to `1280 x 720`
  * Setting it to 1920 x 1080 caused errors (or warnings?) to appear on YouTube Live.
* Set Output (Scaled) Resolution to `1920 x 1080`
  * This becomes the resolution on YouTube, so ensure it’s 1080p.
* Set Downscale Filter to `Lanczos`
* Set FPS Type to `Common FPS Values`
* Set Common FPS Values to `60`
* Set Video Bitrate to `4500` or more
  * It’s likely initially set to `2500`, but at 1080p (60 FPS), 2500 causes a low bitrate warning on YouTube Live.
  * You can increase it to around `6000`, but that depends on the Mac's CPU performance.

#### Stream Key Settings
Due to security reasons, the stream key isn’t synced even if you link your account, so when resuming on a new device, copy and paste the stream key from YouTube Live.

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-16-at-22.10.31.png)

Setting Stream Type to `Custom Streaming Server` triggers a warning, but the recommended settings prohibit viewing YouTube Studio's live screen and setting ultra-low latency, so I opt for custom.

### Soundflower Settings
Configure as shown in the image below.

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen%20Shot%202021-10-10%20at%2018.20.04.png)

* Input 1: Soundflower (2ch)
  * Output only to Main
  * +6 dB
  * Verify the numbers in the left of the volume gauge are `1` for L and `2` for R
* Main Output: ZOOM U-44 Driver
  * Specify the speaker for listening to your audio
  * Keep both the knob and the black gauge at maximum

### Google Meet Settings
Configure as shown in the image below.

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-16-at-21.12.15-1.png)

* Microphone: EVO4
* Speaker: Soundflower (2ch)

It's crucial to set the speaker to Soundflower (2ch)! If you specify a headphone, etc., for listening to the audio, the sound will not be input to the streaming software, so be cautious.
