---
layout: post
title: "一時的に iCloud の自動バックアップを無効にして iPhone で写真を撮影する方法"
author: [
  "noraworld"
]
description: "iCloud に保存してほしくない写真を iPhone で撮影する方法について紹介する。"
image: "https://noraworld.github.io/box-ivysaur/2025/07/09/0e0a1ecbf87caacaf46bd35bc1aff86e.jpg"
date: 2025-07-09 20:30:00 +09:00
tags: [
  "how-to"
]
published: true
---

### はじめに
iCloud に保存したくない写真を iPhone で撮影したいことがときどきある。その手の写真はもっぱら AirDrop で Mac に転送して処理するのだが、iPhone で撮影して Mac に転送するまでの間に iCloud に自動でバックアップされてしまうのが怖い。別に一時的にでも iCloud に保存されちゃっても問題ない写真ならいいのだが、そうじゃない写真の場合は、すぐ消すのにいちいち iCloud に保存されてしまうのは困る。AirDrop は Wi-Fi またはモバイル通信を使用するので機内モードにしてしまうと AirDrop も使えなくなってしまう。

そこで今回は iCloud に自動バックアップされないように iPhone で写真を撮影する方法を個人的な備忘録としてまとめておく。

### 手順
といっても手順は簡単で、写真アプリでモバイル通信を行えないように設定を変更したのち、Wi-Fi をオフにしてモバイル通信のみを有効にして撮影すればいい。具体的な手順は以下のとおりだ。

1. 設定アプリを開く
2. モバイル通信の項目を選択する
![](https://noraworld.github.io/box-ivysaur/2025/07/09/20ce93e1cfb036671b19ff3ca8ddcde1.jpg)
3. アプリごとの使用量が表示されるセクションからすべて表示を選択する
![](https://noraworld.github.io/box-ivysaur/2025/07/09/1c476000b488112a47698af4c42c5045.jpg)
4. 写真アプリのスイッチをオフにする
![](https://noraworld.github.io/box-ivysaur/2025/07/09/e15d39fc2daf5bb1f6b02719e3b81f4b.jpg)
5. Wi-Fi をオフにする（設定アプリの Wi-Fi の項目でスイッチがオフになっていなくてもコントロールセンターで無効化していれば問題なし）
![](https://noraworld.github.io/box-ivysaur/2025/07/09/c0359117843086a767c4407a123e58a2.jpg)
6. 写真アプリを開き iCloud への同期がポーズされていることを確認する
![](https://noraworld.github.io/box-ivysaur/2025/07/09/0e0a1ecbf87caacaf46bd35bc1aff86e.jpg)
7. 写真を撮影する
8. AirDrop で転送する
9. 写真を削除する
10. 最近削除した項目から写真を完全に削除する
![](https://noraworld.github.io/box-ivysaur/2025/07/09/37a90409ed72c8ac40325ef21d48532e.jpg)
11. バックアップがポーズされている写真がないことを確認してから Wi-Fi を有効にする
![](https://noraworld.github.io/box-ivysaur/2025/07/09/0e0a1ecbf87caacaf46bd35bc1aff86e.jpg)
12. （普段はモバイル通信でもバックアップしてほしい場合）1 〜 4 の手順の逆の操作を行い再度写真アプリ内でのモバイル通信を有効化する

手順 6, 10 でバックアップがポーズされているかどうか、また、ポーズされている写真がないかどうかは、写真アプリ右上のプロフィールアイコンから確認できる。削除後、ポーズされているアイテムがなければ Wi-Fi をオンにして良い。

| OK | NG |
| :---: | :---: |
| ![](https://noraworld.github.io/box-ivysaur/2025/07/09/0e0a1ecbf87caacaf46bd35bc1aff86e.jpg) | ![](https://noraworld.github.io/box-ivysaur/2025/07/09/dab0354f8ae13729e8f4564e7a94c033.jpg) |

手順 9 で最近削除した項目から写真を完全に削除しているが、これをしないとポーズされているアイテムがゼロにならないことがあるので必要。これをやってもゼロにならなかったら、いったん写真アプリを再起動してみると良い。

手順は簡単だが操作をちょっとでも間違えると一瞬であっても iCloud に保存されてしまう危険性があるのでそこは注意が必要だ。一時的にでも iCloud に保存されたくない写真の場合は十二分に気をつけること。

### 余談
余談だが、最初はモバイル通信の設定で iCloud Backup を無効にすれば写真を新たに撮影しても Wi-Fi がオフになっていれば同期されないと思っていた。しかしなぜかこれをオフにしてもモバイル通信でも写真を撮ったらすぐにバックアップされてしまった。iCloud Drive のほうも同様。どういうことなんだろうか。

![](https://noraworld.github.io/box-ivysaur/2025/07/09/05db7016f526d946ec4416b7e42c2358.jpg)

ちなみに一時的に iCloud Photos を無効にするっていう方法もあるけど、写真を撮ってすぐにもとに戻すことを考えるとこれは現実的じゃないな。

![](https://noraworld.github.io/box-ivysaur/2025/07/09/c5c4cc26c3bc4cda7becb6f0daa4ea98.png)
