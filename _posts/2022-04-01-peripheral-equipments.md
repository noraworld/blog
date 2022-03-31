---
layout: post
title: "我が家の周辺機器"
image: ""
date: "2022-04-01 00:49:00 +09:00"
tags:
published: true
---

# はじめに
我が家の周辺機器の接続経路が複雑化してきたなと思ったので、ここいらでまとめることにした。せっかくなので公開することにした。

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
    usb_dac2(Zoon U-44 2)

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

いつも目にしているのでわかってはいたが、改めて図にしてみると結構ごちゃごちゃしている。

| Device                      | Description | Note |
| --------------------------- | ----------- | ---- |
| Fire TV                     | ストリーミングデバイス | • YouTube や VOD を視聴する |
| Nintendo Switch             | ゲーム機 | |
| Raspberry Pi 4              | シングルボードコンピュータ | • オーディオサーバ<br>• DNS サーバ<br>• DHCP サーバ |
| USB Hub                     | | |
| USB Dongle Hub 1            | | |
| USB Dongle Hub 2            | | • Bluetooth 経由で音声を受け取ることができるが今はあまり使われていない |
| USB Dongle Hub 3            | | • Bluetooth 経由で音声を受け取ることができるが今はあまり使われていない |
| USB Dongle Hub 4            | | • Bluetooth 経由で音声を受け取ることができるが今はあまり使われていない |
| HDMI Switcher               | HDMI 切替器 | • ケーブルを抜き差ししなくても映像を切り替えることができる |
| HDMI Audio Splitter         | HDMI 音声分離器 | • 音声を USB-DAC に送ること (ミキシング & ヘッドフォンに音を送ること) ができる<br>• モニターの電源を切っていても音声だけを聴くことができる |
| HDMI Splitter               | HDMI 分配器 | • ゲーム映像録画時に遅延しないフルの映像を見つつ録画もすることができる |
| Zoom U-44 1                 | USB-DAC | • 本当はオーディオインターフェースだが USB-DAC としても使える<br>• 音声入力をミキシングして出力する |
| Zoon U-44 2                 | USB-DAC | (同上) |
| Bluetooth Audio Transmitter | Bluetooth オーディオトランスミッタ | • あらゆる音声が集約されてここに届く |
| SONY WH-1000XM3             | Bluetooth ヘッドフォン | • あらゆる音声を同時に聴くことができる |
| MacBook Pro                 | PC | • 作業用マシン |
| Blackmagic eGPU Pro         | eGPU | • Mac のグラフィック性能を補助する |
| EVO 4                       | オーディオインターフェース | |
| Preamplifier                | プリアンプ | • できる限りノイズを入れずにマイクの音声を増幅する (Shure SM7B は拾う音が小さすぎるので) |
| Shure SM7B                  | ダイナミックマイク | |
| Cam Link                    | キャプチャボード | • ゲームプレイ時に録画する |
| Logitech C920n              | ウェブカメラ | • オンラインミーティング時に使用する |
| Mistel MD600v3 RGB          | キーボード | |
| Logicool MX ERGO            | トラックボール | |
| BenQ EW3280U                | モニター | |
| LG 27UL850-W                | モニター | |
| iPhone 13 Pro               | スマートフォン | |
