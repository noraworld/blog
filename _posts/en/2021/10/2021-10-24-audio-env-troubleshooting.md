---
layout: post
title: "Troubleshooting Audio Issues"
date: "2021-10-24 19:05:24"
tags:
published: true
---

### The Beginnings
Around 6 p.m. today, the audio from my Mac, Raspberry Pi, and Fire TV became distorted.

A few days ago, the audio interface connected to my Mac stopped capturing sound. The cause was unknown. This was the first time this issue had occurred.

Ultimately, this issue was resolved by reconnecting the USB, but since it happened a few days ago, I mistakenly thought this new problem could be related.

However, this time reconnecting the USB did not help, and I realized the same problem was affecting both the Raspberry Pi and Fire TV.

I remembered experiencing a similar issue while setting up audio aggregation on Raspberry Pi's PulseAudio.

I ended up resolving that past issue by reinstalling Ubuntu.

Though initially discouraged, suspecting a repeat of the previous issue, I decided to investigate further.

All devices, including the Mac, Raspberry Pi, Fire TV, and Bluetooth transmitter, were connected, leaving the root of the problem unclear. So, I decided to isolate the components and check each one individually.

The issue persisted even when only connecting the Mac to the Bluetooth transmitter, and the same happened when connecting just the Raspberry Pi.

At this point, I finally realized the issue wasn't with the Mac or Raspberry Pi but with the Bluetooth transmitter.

Though it may seem simple to reflect on now, it took me about an hour to reach this realization.

To avoid wasting time in the future, I decided to compile a personal troubleshooting guide for when audio problems occur.

This is a completely personal note, but I hope it might serve as a reference for readers.



### Troubleshooting
1. Suspect the Bluetooth transmitter
2. Suspect the audio separator
3. Suspect the Mac
4. Suspect the Raspberry Pi

#### Suspect the Bluetooth Transmitter
##### Possible Symptoms
* Distorted sound
* Audio dropouts

##### Verification Method
* Connect a single audio source to the transmitter for testing
    * However, the individual audio source could also be faulty, so it's advisable to test various audio sources individually

Verification scenarios are as follows:

* HDMI audio from devices like Fire TV
    * Directly connect the S/PDIF from the audio separator to the transmitter
* Mac
    * Directly connect the S/PDIF from the audio interface connected to the Mac to the transmitter
* Raspberry Pi
    * Directly connect the S/PDIF from the audio interface connected to the Raspberry Pi to the transmitter

##### Solution
* Turn off the headphones, disconnect from Bluetooth, wait about a minute, then turn the headphones back on and reconnect

To be honest, it feels like it might be better to do this before checking anything else...

##### Notes
This was, in fact, the underlying cause of the issue this time.

The Bluetooth transmitter at my home is the TaoTronics TT-BA09.

With this transmitter, if you try to reconnect to the headphones immediately after disconnecting, the described issue occurs. It's unclear if this is a defect with this product or if I got a defective one.

Since I use two pairs of headphones, I knew for some time that if I turn one off and immediately connect the other, this issue frequently occurs.

Waiting about a minute usually resolves the problem, so it hadn't been much of a concern. Yet, for some reason, it never occurred to me this time. I can't believe I overlooked this aspect, despite repeatedly encountering it.

I was about to include an Amazon link, but it’s been discontinued. Could it be a faulty product after all…?

Anyway, first determine if the Bluetooth transmitter is causing the problem.

#### Suspect the Audio Separator
##### Possible Symptoms
* (No issues observed yet)

##### Verification Method
* Connect the S/PDIF from the audio separator directly to the transmitter, and check if audio from HDMI devices is audible
    * Remember that the HDMI switch upstream could be problematic, so connecting directly to a single HDMI device is preferable
    * Testing with Fire TV seems helpful; if trouble seems to stem from it, also check with a Nintendo Switch for certainty

##### Solution
* Turn off the power once, wait a minute, then turn it back on
* Unplug and plug back in the HDMI cable

##### Notes
So far, the audio separator has not been a problem, but it must be considered as a potential issue, being a piece of equipment involved in audio processing.

When recently unable to capture sound through the audio interface connected to my Mac, I considered whether the audio separator might be at fault as a precaution.

#### Suspect the Mac
##### Possible Symptoms
* Audio becomes completely inaudible

##### Verification Method
* Check if the `SYNC` lamp on the S/PDIF of the audio interface connected to the Mac is on

##### Solution
* Disconnect the USB between the Mac and the audio interface, wait a few seconds, then reconnect it

##### Notes
Recently, there was an incident where passing audio through the audio interface connected to the Mac rendered all sound inaudible, requiring suspicion of a fault here.

Such an event had never happened before the recent issue, so the cause remains undetermined.

#### Suspect the Raspberry Pi
##### Possible Symptoms
* Distorted sound
* Audio dropouts
* Audio becomes completely inaudible

##### Verification Method
* Connect the Raspberry Pi directly to the transmitter and play sound from the Raspberry Pi

```shell:Shell
marlin play
ojt test
```

##### Solution
* Check if the daemon is running correctly
* Ensure PulseAudio settings are correct and verify them
* Attempt a reboot and see if it resolves the issue

```shell:Shell
marlin health
pacmd list-sinks
```

##### Notes
Reaching this point can be quite troublesome.

PulseAudio can suddenly develop mysterious issues, so if it’s the cause, finding a solution might be difficult.

Previously, the solution involved reinstalling Ubuntu, which I’d rather not do again.
