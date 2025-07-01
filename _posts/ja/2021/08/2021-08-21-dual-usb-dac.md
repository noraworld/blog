---
layout: post
title: USB-DAC 2 台体制メモ
date: '2021-08-21 05:41:59'
published: true
---

先日、Zoom U-44 をもう 1 台導入した。もともと 1 台持っていて、もう 1 台新たに購入した。

Zoom U-44 はオーディオインターフェースだが、USB-DAC として使っている。もともと持っていた 1 台は、Raspberry Pi と接続し、さらに Fire TV や Nintendo Switch、PS 4 の音声を音声分離器で分離して光オーディオ端子で出力したものを接続している。つまり、Bluetooth 経由で Raspberry Pi に送った音声と、Fire TV、Nintendo Switch、PS 4 の音声をミキシングして音を聞いていた。

これはこれで快適な音響環境だったのだが、たまに仕事用の MacBook Pro と Raspberry Pi の Bluetooth 接続がうまくいかないときがある。オンラインミーティング直前だったりすると、結局、MacBook Pro とヘッドフォンをステレオミニプラグで接続して有線で聞く羽目になる。

これが非常に不便なので、MacBook Pro の音声は、Raspberry Pi との Bluetooth ではなく安定して聞けるようにしたい、ということで、もう 1 台 Zoom U-44 を導入し、音をミキシングすることにした。

最初は Raspberry Pi 側で使っている Zoom U-44 の音声出力先を、新しい Zoom U-44 に送って、新しいほうを MacBook Pro と接続して音声をミキシングして聞いていた。

しかし、この構成だと、Fire TV や Nintendo Switch、PS 4 で映像を切り替えたときに (これら 3 つは HDMI 切替器で自動的に切り替わるようになっている) ビリビリビリという不快なノイズが入ってしまった。ノイズの音もうるさくて結構びっくりする。

MacBook Pro の `Audio MIDI Setup` でビットレートを変えたりもしたが、多少の音の軽減はあるものの、やはり気になる。

ということで、新しいほう (Mac と接続しているほう) で MacBook Pro と Fire TV、Nintendo Switch、PS 4 の音声をミキシングし、その出力を Raspberry Pi 側に送って、音を聞くことにした。

そしたらこの不快音が、今のところ聞こえなくなった。

それから、MacBook Pro の音声とゲーム音を、MacBook Pro 側の Zoom U-44 でミキシングしたほうが、音量をぴったり半々にできるから、ゲーム配信の音量バランスとか、誰かと一緒にゲームするときの音量バランスが取りやすいかなという、気づいていなかったメリットに気づけた。

最終的に Bluetooth オーディオトランスミッタに音声を送るのは MacBook Pro 側の Zoom U-44 にしておけば、万一、Raspberry Pi 側でトラブルが起きても (Raspberry Pi の音声周りは正直信頼できていない) 最悪 MacBook Pro の音声は聞こえるので良いかなと思ったのだが、試してみるとノイズが入ってしまうことがわかった。何事も試してみないとわからないなあと思った。
