---
layout: post
title: "Google AdSense の審査"
image: ""
date: "2021-10-24 13:10:45"
tags:
published: false
---

Google AdSense の審査に合格するまでにやったことをメモとして残しておこうと思う。ちなみにこの記事を書き始めている現時点ではまだ審査は通っていない。もしかしたらこの記事はお蔵入りになるかもしれない。

# 一番最初の審査
実は、すでに一度、Google AdSense の審査に合格している。2021 年 4 月 12 日に Google AdSense のアカウントを開設した。同日、旧ブログ用のドメインである `noraworld.blog` に対し審査を申請したところ、見事に落ちた。

![Google AdSense 審査落ち](https://raw.githubusercontent.com/noraworld/blog-content/main/google-adsense-approval/Screen%20Shot%202021-10-24%20at%2013.22.48.png)

その後、10 日ほど経ったあと、全く内容を変えずに再審査したら、なんとあっさり通ってしまった。

![Google AdSense 審査合格](https://raw.githubusercontent.com/noraworld/blog-content/main/google-adsense-approval/Screen%20Shot%202021-10-24%20at%2013.27.05.png)

ただし、このドメインに対しての審査は実は本命ではなかった。というのも、Google AdSense は、一番最初の審査 (アカウント作成後の初めての審査) では、必ず Zone Apex を用いなければならない。つまり、サブドメインは審査できないということだ[^1]。

[^1]: ただし例外としてサブドメインが `www` の場合は認められている。

筆者が審査に合格させたかったのは、GitHub Pages で GitHub が提供する `noraworld.github.io` である。

前にも [別の記事](./ghost-to-jekyll) で書いたが、今後は独自ドメインを用いた Web サイトの運用をやめ、自分自身が管理不能になっても残り続けるようにしたいと思っている。そのため、GitHub Pages で使える管理不要の `noraworld.github.io` を Google AdSense の審査に合格させたかった、というわけだ。

そのため、まずは Zone Apex である独自ドメインで審査に合格し、そのあとに `noraworld.github.io` を使えるようにしようと思ったわけだ。

このブログ自体は `https://noraworld.github.io` ではなく `https://noraworld.github.io/blog` で運用したいと考えている。2 つめ以降のドメインを承認してもらう際には、Zone Apex である必要はないのだが、サブパスがついている Web サイトを審査してもらうことはできない。サブドメインでもトップレベルである必要があるのだ。

別にブログの収益にそこまで固執しているわけでもないのだが、将来的に広告を貼りたいとなった場合に、あとからだとめんどくさいと思ったからだ。なぜなら、一度 `https://noraworld.github.io/blog` で公開してから、Google AdSense の審査に合格するためにはいったん、`https://noraworld.github.io` で公開し直して、合格後にまた戻す必要がある。

それに、このブログ以外にも、GitHub Pages で公開したい Web サイトはいくつかある。一度 `https://noraworld.github.io` で審査に通ってしまえば、今後 GitHub Pages で公開するすべての Web サイトに適用されるはずなので、最初が肝心だと思った。仮に Web サイトごとに審査が必要だったとしても、あとから URL を変える必要はなくなるので、見切り発車でも良くなるわけだ。



# 2 つめのドメインの審査
というわけで、`noraworld.github.io` を審査してもらうことにした。その前に、`noraworld.blog` のブログ記事内容を `noraworld.github.io` に移す必要がある。

## ブログの移行
`noraworld.blog` は Ghost で動いており、`noraworld.github.io` は Jekyll でビルドする。なので、Ghost から Jekyll に移行するツールを使った。

記事の移行はそれほど難しくなかった。ただ、画像まではツールではインポートできないので、Ghost サーバから画像を一式ダウンロードしてきて、それらをすべて GitHub リポジトリ上にアップロードする、という作業は時間がかかりめんどくさかった。

それも終わり、ようやく記事として見られる状態にはなった。まだデザインなどは全くいじっておらず、Jekyll のデフォルトテーマそのままなのだが、それは後々やるとして、まずは審査に通すところから始めた。

## 最初の審査
最初に審査に出したのがいつだったかはっきりとは覚えていないが、たしか 1 ヶ月ほど前 (9 月末あたり) だったと思う。

`noraworld.blog` のときは申請当日や 1 〜 2 日後に結果が来ていたが、`noraworld.github.io` の最初の審査は 10 日以上かかった。そしてその結果は「不合格」だった。

![Google AdSense 審査落ち](https://raw.githubusercontent.com/noraworld/blog-content/main/google-adsense-approval/Screen%20Shot%202021-10-04%20at%2022.15.31.png)

審査落ちの理由は「サイトがダウンしているか、利用不能」である。正直、なんのことかさっぱりわからない。`noraworld.github.io` にアクセスすれば常に見られる状態になっていたからダウンはありえない。アクセス制限なんて GitHub Pages だからもちろんかけられるはずもない。

タイピングミスをしているかもしれないとも書かれているが、それも関係なかった。

## 原因解明
理由が意味不明だったので、審査落ちの文言で検索したら、いくつかそれらしき解決策の記事がヒットした。

[Solved: Google Adsense Site down or unavailable problem](https://sciencetechstudy.com/site-down-or-unavailable-problem-solved-adsense-godaddy/)

他にもたくさん記事が出てきたが、どれも上記の記事と本質的には同じことを書いているものが多かった。

この記事によると、以下を変更する良いとのこと。

1. サイトマップを追加する
2. `robots.txt` で Google のクローラーをブロックしないようにする
3. サイトマップを Google Search Console に追加する
4. `robots.txt` が有効かどうか Google Search Console で確認する
5. Zone Apex でアクセスした際に、`www` サブドメインにリダイレクトすること

5 に関しては今回は関係ないので、サイトマップと `robots.txt` の追加が主な解決策となる。

### サイトマップ追加
Jekyll には [jekyll-sitemap](https://github.com/jekyll/jekyll-sitemap) サイトマップを自動で追加してくれるプラグインがある。しかもこのプラグインは GitHub 側の自動デプロイでも使えるようになっている。

[GitHub Pages - Dependency versions](https://pages.github.com/versions/)

ということでさっそく有効化した。

### `rubots.txt` 追加
次に `robots.txt` だが、これは単にこのファイルをトップレベルに置くだけで良いので、プラグインなども不要だ。サイトの例に従い、`robots.txt` を追加した。

### Google Search Console に追加
そして、サイトマップと `robots.txt` を Google Search Console で確認してみた。

`robots.txt` のほうは特に問題なかったが、サイトマップを追加したらエラーになってしまった。

[Sitemap could not be read (Couldn’t fetch) in Google Search Console](https://www.jcchouinard.com/sitemap-could-not-be-read-couldnt-fetch-in-google-search-console/)

全く同じ内容のエラーで解決策が書かれている記事を見てみると、ただ待つだけで良い、としか書かれていなかった。

まあそうなのだろうと思い、1 週間近く待っていたら、エラーが消えて有効な状態になっていた。

### SEO タグ追加
それから、SEO タグを追加すると良いという記事も見かけたので、ついでにそれも追加することにした。

SEO タグに関しても Jekyll のプラグインが用意されており、それをインストールして有効化するだけで簡単に使えた。

[Optimize your Jekyll powered website with these simple steps](https://vilcins.medium.com/optimize-your-jekyll-powered-website-with-these-simple-steps-b2a24d66a629)

これも GitHub の自動デプロイ対象のプラグインだ。

## 再審査
準備は整ったので、再審査を申請した。

その結果は……、「不合格」だった。まあ冒頭で「まだ審査は通っていない」とネタバレしちゃってるけどね。

内容は相変わらず同じで、サイトがダウンしているか利用不能というものだ。

正直、このエラー内容で出てくる解決策は全部試したので、他に手の打ちようがなかった。

なので、審査が落ちる可能性について考えてみた。いくつかの理由が思い浮かんだ。

1. `noraworld.blog` のコピーコンテンツと見做されている
2. 新たに追加した記事に問題がある
3. デフォルトのサンプル記事が混ざっている

### `noraworld.blog` のコピーコンテンツと見做されている
今、審査を通そうとしている `noraworld.github.io` の内容は、以前審査に通った `noraworld.blog` と一緒だ。つまり、コピーコンテンツとして扱われてしまっているのではないかと思い至った。

もちろん `noraworld.github.io` の審査が通ってしまえば `noraworld.blog` はリダイレクト処理を入れておこうと思っていた。でも、最終的に公開する URL は `/blog` というサブパスがついているので、現時点でリダイレクト処理を入れるわけにはいかないと思っていた。

しかし、もしこれが原因なら、いつまで経っても審査が通らないことになる。そこで、考えた。

正式な状態 (審査が通り `noraworld.github.io/blog` として公開) になったあとは、`noraworld.blog` に 301 リダイレクトを入れるつもりだが、とりあえず現時点では `noraworld.github.io/blog` ではなく `noraworld.github.io` に対し、302 リダイレクトを入れておけばよいのではないか、と。

301 は永久リダイレクトなので取り消すのが難しいが、302 なら一時的なので問題ないだろうと判断したわけだ。

審査が通ったあと、`noraworld.github.io` へのリダイレクトを `noraworld.github.io/blog` に変え、302 を 301 にすれば解決である。

### 新たに追加した記事に問題がある
`noraworld.github.io` の内容は、以前審査に通った `noraworld.blog` と同じ、と書いたが、`noraworld.blog` の審査に合格したあとにも記事をいくつか追加しているので、それが原因になっているのではないかと考えた。

もちろんそこまで質の低い記事を書いたつもりはないが、こと審査を通すという観点においては、前回通ったという実績を利用するのがてっとり早い。だから、前回と同じ状況をなるべく再現するために、新しく追加した記事に関しては一時的に非公開にすることにした。

Jekyll だと、記事の YAML ヘッダに `published: false` を追加するだけでその記事を非公開にすることができる。ちなみにこの記事自体も、Google AdSense の審査が通るまでは非公開にする予定だ[^2]。

[^2]: 非公開のままお蔵入りにならないことを祈る…… 🙏

### デフォルトのサンプル記事が混ざっている
Ghost や Jekyll を立ち上げたときに、サンプル記事が 1 つ入っている。それが「質の低いコンテンツ」として見做されている可能性がある。

Jekyll のほうは新しい記事を非公開にするのと一緒に非公開にしたが、Ghost のサンプル記事はまだ残ったままなのでこっちも非公開にした。

まあ、前回の審査に通ったときはこのサンプル記事があったので、あまり有効打ではないかもしれないけど。

しかも前回は全く内容を変えずに再審査したら通ったので、審査する人によってもここらへんの基準が若干変わるのかもしれない……。

## 満を持して
いくつかの修正を加え、もう一度、審査の申請をした。もちろんこれも不合格だったわけだが、審査結果が変わった。

![Google AdSense 審査落ち 2 回目](https://raw.githubusercontent.com/noraworld/blog-content/main/google-adsense-approval/Screen%20Shot%202021-10-24%20at%2012.48.34.png)

先ほどまでは「サイトがダウンまたは利用不能」になっていたが、今回は「十分なコンテンツが存在しない」に変わっている。

これは前回の `noraworld.blog` のときと似たような感じになっている。いわゆる「質の低いコンテンツ」と見做されている可能性がある。

一点、気になるのは、ここに来て「コピーコンテンツ」に言及した文言が入っている。むしろ今までが `noraworld.blog` のコピーコンテンツ扱いとなっているはずなので、おそらく今回の理由はそこではなく単純にコンテンツの質が低いと見做されているのではないかなと推測している。

ただ、これは何回か書いているが、審査する人によって基準が変わる可能性があるから、何回か申請を試していれば通る可能性がなくはない。

# さいごに
というわけで、ここまでが現時点 (2021/10/24) までの進捗だ。また何か進展があったら追記する。この記事が公開されることを願って。

ちなみに、ここまでの内容を見ると、あたかも合計 3 回しか申請を行ってないように見えるが、実はもっと申請している。現時点で合計 7 回申請している。
