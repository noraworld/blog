---
layout: post
title: 友人とオンラインゲームをやる際の YouTube Live 配信設定メモ
image: "https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/streamlabs_obs.png"
date: '2021-08-16 13:27:13'
published: true
---

# これは何の記事
休日に友人や同僚とオンラインでゲームをする機会が今までに何度かあり、今後も継続していこうと思っている。

そして、ゲームプレイや思い出の記録として、ゲームをプレイするときは YouTube Live で毎回配信するようにしている。

ところが、毎回セットアップする際に、主に音響周りで音量の調整に手間取ったりしている。

そこで、今後はなるべく手間を取らないようにするために、うまく調整できていたときの設定状態をメモしておこうと思う。

あくまで個人用のメモなので、誰かのために書く記事ではないが、これを見た人の参考になれば幸いだ。

また、設定を更新した場合はこの記事も更新する。

# 使っている機材
* MacBook Pro
* Blackmagic eGPU Pro
  * eGPU (AMD Radeon RX Vega 56)
  * eGPU がなくても問題なさそうだが、ライブ配信時のリアルタイムエンコードは重い処理なのであったほうが良いかも
* CAM LINK
  * キャプチャボード
  * 以前は GPU 側に接続していたが、映像が定期的に乱れる現象が発生したため、USB-C to USB-A アダプタをかませて MacBook に接続している
* Audient EVO 4
  * オーディオインターフェース
* SHURE SM7B
  * ダイナミックマイク

# 使っているアプリケーション・サービス
* Streamlabs OBS
  * 配信ソフト
* LadioCast
  * 仮想オーディオミキサー
* Soundflower
  * 仮想オーディオ
  * BlackHole も試してみたが、なぜか Mac からの音声 (Google Meet の他の人の声) がノイズだらけ (飛び飛び) になってしまったので、Soundflower を以前から継続して利用している
* Google Meet
  * 会話用

# Streamlabs OBS の設定
## 音声ソースの設定
![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-15-at-22.14.39.png)

以下の 3 つの音声を用意する。

* Soundflower (2ch)
  * 音量: 100 % (0.0 dB)
  * ノイズ抑制 (Noise Suppression)
      * RNNoise
  * ゲイン (Gain)
      * 7.5
  * コンプレッサー (Compressor)
      * Ratio: 10
      * Threshold: -18
      * Attack: 6
      * Release: 60
      * Output Gain: 0
      * Sidechain/Ducking Source: None
* 自分の声 (My Voice)
  * 音量: 100 % (0.0 dB)
  * ノイズ抑制 (Noise Suppression)
      * RNNoise
  * ゲイン (Gain)
      * 10
  * コンプレッサー (Compressor)
      * Soundfolower と同じ
* ゲーム音声 (Game Audio)
  * 音量: 70 % (-11.2 dB)
  * ゲーム音声にフィルターはかけない

## パフォーマンスメトリクスの表示
Streamlabs OBS の設定は、アプリ上で YouTube アカウントと連携することによって、他のデバイスとも同期できる。なので、基本的には設定をいじらなければ問題はないはず。

ただし、左下の、CPU 使用率、FPS、コマ落ち、アップロードデータ量の表示有無は同期されないらしいので、新しいデバイスで設定をし直す場合は手動で追加すること。

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-16-at-21.36.59.png)

特に FPS は、配信環境に問題があることを検出すると、勝手に変わったりすることがある (60 FPS → 30 FPS に勝手に変更されていたことがあった) ので、表示することをおすすめする。

## 配信のクオリティの設定
ここらへんの設定はアカウント連携で同期されるはずだが、以前にいじったら YouTube Live 上でエラーが出るようになってしまったので、設定が間違っていないか今一度確認すること。

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-16-at-22.09.26.png)

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-16-at-22.09.55.png)

* Base (Canvas) Resolution を `1280 x 720` に設定する
  * 1920 x 1080 に設定したところ、YouTube Live でエラー (警告？) が表示されるようになる
* Output (Scaled) Resolution を `1920 x 1080` に設定する
  * これが YouTube 上の解像度になるので、1080p になるようにしておく
* Downscale Filter を `Lanczos` に設定する
* FPS Type を `Common FPS Values` に設定する
* Common FPS Values を `60` に設定する
* Video Bitrate を `4500` 以上に設定する
  * 初期だとおそらく `2500` になっているが、1080p (60 FPS) で 2,500 だと YouTube Live 上でビットレートが低いという警告が出てしまうので
  * `6000` くらいまで上げても良いが、そこは Mac の CPU 性能との相談かな

## ストリームキーの設定
セキュリティ上の観点からか、さすがにここの値はアカウント連携しても同期されないので、新しいデバイスで再開するときは YouTube Live からストリームキーをコピーして貼り付ける。

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-16-at-22.10.31.png)

Stream Type を `Custom Streaming Server` に設定すると警告が出るが、推奨設定のほうだと YouTube Studio のライブ画面が見れなかったり、超低遅延が設定できなかったりして不便なので、カスタムにする。

# Soundflower の設定
以下の画像のように設定する。

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen%20Shot%202021-10-10%20at%2018.20.04.png)

* Input 1: Soundflower (2ch)
  * 出力先は Main のみ
  * +6 dB
  * 音量ゲージの左側の数字が、L は `1` で R は `2` になっていることを確認すること
* Main Output: ZOOM U-44 Driver
  * 自分が音声を聴くためのスピーカーを指定する
  * ツマミも黒いゲージもマックスにしておく

# Google Meet の設定
以下の画像の用に設定する。

![](https://raw.githubusercontent.com/noraworld/blog-content/main/live-streaming-configuration/Screen-Shot-2021-08-16-at-21.12.15-1.png)

* Microphone: EVO4
* Speaker: Soundflower (2ch)

スピーカーを Soundflower (2ch) にすることが重要！ 自分が音声を聞くヘッドフォンなどを指定してしまうと、配信ソフト側に音が入らないので注意。
