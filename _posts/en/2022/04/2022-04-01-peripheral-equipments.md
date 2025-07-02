---
layout: post
title: "Peripheral Devices in Our Home"
date: "2022-04-01 00:49:00 +09:00"
tags:
published: true
---

### Introduction
I thought the connection path of the peripheral devices in our home had become quite complex, so I decided to summarize it. Since I went to the trouble, I decided to make it public.

```mermaid
flowchart TD
    %% Begin elements part
    firetv(Fire TV)
    switch(Nintendo Switch)

    pi(Raspberry Pi 4)
    pi_usb_hub(USB Hub)
    pi_usb_dongle_hub_1(USB Dongle Hub 1)
    pi_usb_dongle_hub_2(USB Dongle Hub 2)
    pi_usb_dongle_hub_3(USB Dongle Hub 3)
    pi_usb_dongle_hub_4(USB Dongle Hub 4)

    hdmi_switcher(HDMI Switcher)
    audio_splitter(HDMI Audio Splitter)
    hdmi_splitter(HDMI Splitter)

    usb_dac1(Zoom U-44 1)
    usb_dac2(Zoom U-44 2)

    transmitter(Bluetooth Audio Transmitter)
    headphone(SONY WH-1000XM3)

    mac(MacBook Pro)
    egpu(Blackmagic eGPU Pro)

    audio_interface(EVO 4)
    preamplifier(Preamplifier)
    microphone(Shure SM7B)
    capture_card(Cam Link)
    camera(Logitech C920n)
    keyboard(Mistel MD600v3 RGB)
    mouse(Logicool MX ERGO)
    monitor1(BenQ EW3280U)
    monitor2(LG 27UL850-W)

    iphone(iPhone 13 Pro)
    %% End elements part



    %% Begin connections part
    firetv -- Picture & Audio --> hdmi_switcher
    switch -- Picture & Audio --> hdmi_switcher
    pi -- Picture --> hdmi_switcher

    hdmi_switcher -- Picture & Audio --> hdmi_splitter
    hdmi_splitter -- Picture & Audio --> audio_splitter
    hdmi_splitter -- Picture & Audio --> capture_card
    audio_splitter -- Picture --> monitor1
    audio_splitter -- Audio --> usb_dac1

    usb_dac1 -- Audio --> usb_dac2
    pi -- Audio --> usb_dac1
    usb_dac2 -- Audio --> transmitter
    egpu -- Audio --> usb_dac2
    pi_usb_hub -- Audio --> pi
    transmitter -. Bluetooth / Audio .-> headphone

    mac <-- Picture & Audio & Input Info --> egpu
    audio_interface -- Audio --> egpu
    preamplifier -- Audio --> audio_interface
    microphone -- Audio --> preamplifier
    camera -- Picture --> egpu
    keyboard -- Input Info --> egpu
    mouse -- Input Info --> egpu
    egpu -- Picture --> monitor1
    egpu -- Picture --> monitor2
    capture_card -- Picture & Audio --> mac

    iphone -. Bluetooth / Audio .-> pi_usb_dongle_hub_1 -- Audio --> pi_usb_hub
    pi_usb_dongle_hub_2 -- Audio --> pi_usb_hub
    pi_usb_dongle_hub_3 -- Audio --> pi_usb_hub
    pi_usb_dongle_hub_4 -- Audio --> pi_usb_hub
    %% End connections part
```

Although I already knew this because I see it every day, seeing it diagrammed anew still makes it look quite cluttered.

| Device                      | Description | Note |
| --------------------------- | ----------- | ---- |
| Fire TV                     | Streaming device | • Used to watch YouTube and VOD |
| Nintendo Switch             | Game console | |
| Raspberry Pi 4              | Single-board computer | • Audio server<br>• DNS server<br>• DHCP server |
| USB Hub                     | | |
| USB Dongle Hub 1            | | |
| USB Dongle Hub 2            | | • Can receive audio via Bluetooth but is not used much now |
| USB Dongle Hub 3            | | • Can receive audio via Bluetooth but is not used much now |
| USB Dongle Hub 4            | | • Can receive audio via Bluetooth but is not used much now |
| HDMI Switcher               | HDMI switcher | • Allows switching of video without having to plug and unplug cables |
| HDMI Audio Splitter         | HDMI audio splitter | • Can send audio to the USB-DAC (for mixing & sending sound to headphones)<br>• Can listen to audio even if the monitor is powered off |
| HDMI Splitter               | HDMI splitter | • Can watch the full video without delay while recording game footage |
| Zoom U-44 1                 | USB-DAC | • Actually an audio interface, but can also be used as a USB-DAC<br>• Mixes audio inputs and outputs |
| Zoom U-44 2                 | USB-DAC | (Same as above) |
| Bluetooth Audio Transmitter | Bluetooth audio transmitter | • All audio is aggregated and sent here |
| SONY WH-1000XM3             | Bluetooth headphones | • Can listen to all audio simultaneously |
| MacBook Pro                 | PC | • Work machine |
| Blackmagic eGPU Pro         | eGPU | • Supports the graphic performance of the Mac |
| EVO 4                       | Audio interface | |
| Preamplifier                | Preamplifier | • Amplifies microphone audio without introducing noise as much as possible (since the Shure SM7B picks up very small sounds) |
| Shure SM7B                  | Dynamic microphone | |
| Cam Link                    | Capture card | • Used to record while gaming |
| Logitech C920n              | Webcam | • Used during online meetings |
| Mistel MD600v3 RGB          | Keyboard | |
| Logicool MX ERGO            | Trackball | |
| BenQ EW3280U                | Monitor | |
| LG 27UL850-W                | Monitor | |
| iPhone 13 Pro               | Smartphone | |
