---
layout: post
title: ブラウザ版 1Password がデスクトップ版と連携できないときの解決法
date: '2021-08-25 12:58:01'
published: false
---

# はじめに
会社の PC では、仕事用とプライベート用でブラウザを使い分けている。仕事用では Google Chrome、プライベート用では Google Chrome Beta を使用している。

最初に PC にインストールした Google Chrome では、デスクトップ版 1Password との連携が最初から可能だったのだが、Google Chrome Beta ではなぜか連携できなかった。

それを 1Password に問い合わせてみたところ、見事解決したので、備忘録としてやり方を残しておく。

# 連携すると何が嬉しいのか
端的に言うと、MacBook の場合は Touch ID (指紋認証) が使えることだ。

デスクトップ版では、設定で Touch ID を有効にすると、マスターパスワードを入力する代わりに Touch ID でロックを解除することができる。ブラウザ版では、デスクトップ版との連携をオンにすることによって、同様の機能を利用することができる。

![](https://raw.githubusercontent.com/noraworld/blog-content/main/1password-desktop-app-integration-not-work/Screen-Shot-2021-08-25-at-21.16.23.png)

セキュリティ上、5 〜 10 分間が経過したら 1Password を自動的にロックするようにしておきたい。しかし、毎回マスターパスワードを入力するのはめんどくさい。そのため、Touch ID でのロック解除は非常に重宝している。

# 設定を有効にする
そもそも設定を有効にしていない場合は当たり前だが利用できないので、まずは設定で有効にする。

デスクトップ:

![](https://raw.githubusercontent.com/noraworld/blog-content/main/1password-desktop-app-integration-not-work/Screen-Shot-2021-08-25-at-21.22.06.png)

ブラウザ:

![](https://raw.githubusercontent.com/noraworld/blog-content/main/1password-desktop-app-integration-not-work/Screen-Shot-2021-08-25-at-21.11.11.png)

補足: 日本語だと「1Password アプリと連携」という名称になっている

通常ならこれで連携機能が使えるはずだが、Google Chrome Beta を利用している場合なのか、2 つ以上のブラウザの利用している場合なのかは不明だが、この機能が正常に動作しない場合がある。その場合は、以下に紹介する方法を試す。

# デスクトップ連携用の JSON ファイルをコピーする
ターミナルを開いて、以下のコマンドを実行する。

```shell:Shell
cd ~/Library/Application\ Support/Google/Chrome/NativeMessagingHosts
mkdir -p ~/Library/Application\ Support/Google/Chrome\ Beta/NativeMessagingHosts
cp 2bua8c4s2c.com.agilebits.1password.json com.1password.1password7.json ~/Library/Application\ Support/Google/Chrome\ Beta/NativeMessagingHosts
```

その後、Chrome Beta と 1Password (デスクトップアプリ) を再起動する。

再起動後、デスクトップ連携が有効になっていることを確認する。

なお、Chrome Beta ではなく、以下に示す別のブラウザを使用している場合は、適宜 `~/Library/Application\ Support/Google/Chrome\ Beta/NativeMessagingHosts` の部分を読み替えること。

* Google Chrome Beta: `~/Library/Application\ Support/Google/Chrome\ Beta`
* Google Chrome Dev: `~/Library/Application\ Support/Google/Chrome\ Dev`
* Google Chrome Canary: `~/Library/Application\ Support/Google/Chrome\ Canary`
* Microsoft Edge Beta: `~/Library/Application\ Support/Microsoft\ Edge\ Beta`
* Microsoft Edge Dev: `~/Library/Application\ Support/Microsoft\ Edge\ Dev`
* Microsoft Edge Canary: `~/Library/Application\ Support/Microsoft\ Edge\ Canary`

# 参考
https://support.1password.com/could-not-connect/
