---
layout: post
title: Notes on a Dual USB-DAC Setup
date: '2021-08-21 05:41:59'
published: true
---

Recently, I introduced another Zoom U-44. I already had one, and decided to purchase a new one.

The Zoom U-44 is an audio interface, but I use it as a USB-DAC. The one I already had is connected to a Raspberry Pi, and further connects to audio output devices like Fire TV, Nintendo Switch, and PS 4 via an audio separator that outputs through an optical audio jack. In other words, I was mixing audio sent to the Raspberry Pi via Bluetooth with the audio from Fire TV, Nintendo Switch, and PS 4 to listen through this setup.

This was a comfortable audio setup, but occasionally, the Bluetooth connection between the work MacBook Pro and the Raspberry Pi didn't function smoothly. If it happened just before an online meeting, I would end up connecting the MacBook Pro to headphones using a stereo mini-plug for a wired listening experience.

This was quite inconvenient, so I wanted the MacBook Pro audio connection to be stable and not rely on Bluetooth with the Raspberry Pi. Thus, I introduced another Zoom U-44 to mix the audio.

Initially, I routed the audio output from the Zoom U-44 used with the Raspberry Pi to the new Zoom U-44, connecting the new one to the MacBook Pro to mix and listen to the audio.

However, with this setup, when switching video on Fire TV, Nintendo Switch, or PS 4 (these three automatically switch using an HDMI switcher), an unpleasant noise like buzzing would occur. The noise was loud and quite surprising.

Even when changing the bitrate in the MacBook Pro's `Audio MIDI Setup`, there was a slight reduction in noise, but it was still noticeable.

So, I decided to mix the audio from the MacBook Pro, Fire TV, Nintendo Switch, and PS 4 with the new Zoom U-44 connected to the Mac. The output was then sent to the Raspberry Pi side for listening.

This seemed to eliminate the unpleasant noise for now.

Additionally, mixing audio from the MacBook Pro and game audio with the MacBook Pro side Zoom U-44 allows for equal volume levels. This makes balancing audio levels during game streaming or when gaming with others easier—a benefit I hadn't realized before.

Ultimately, if the Bluetooth audio transmitter sends audio from the MacBook Pro's Zoom U-44, even if something goes wrong on the Raspberry Pi side (as I don't fully trust the Raspberry Pi's audio), at least the MacBook Pro audio will be audible, which seemed like a good idea. However, even in testing, noise still occurred. It made me realize you never really know until you try.
