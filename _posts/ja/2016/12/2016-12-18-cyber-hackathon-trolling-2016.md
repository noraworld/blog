---
layout: post
title: サイバー犯罪被害防止ハッカソンのようすと大炎上まとめ
date: '2016-12-18 16:39:24'
tags:
- university-life
- event
- development
published: true
---

**この記事について、追加の記事を投稿しました。この記事についてTwitter等で意見を述べたりコメントを書いたりする場合は、必ず追加の記事も読んだ上で発言してください。**

[サイバー犯罪被害防止ハッカソン炎上記事の後日談](https://noraworld.blog/cyber-hackathon-trolling-2016-sequel/)

12月17日(土)〜12月18日にかけて、自分が所属するRCC主催の「サイバー犯罪被害防止ハッカソン」がありました。自分はRCCメンバーとして「圧倒的人権の欠如」というチーム名で参加しました。見事フラグを回収したことについては後々紹介していきます。

今回はRCCと京都府警が連携して行うハッカソンでした。

### どんなハッカソン？
昨今、サイバー犯罪が後を絶たない（フィッシング詐欺やランサムウェアなど）ので、なんとかしてサイバー犯罪の被害者を減らすための技術的な対策を考えるのが趣旨です。

各チーム自分たちで作ったグループに加え高校生が2人程度プラスしたチームで構成されました。高校生にうまく仕事を振り分けるのも重要な目的のようでした。

最終的に作ったものをプレゼンして、京都府警と教授陣が採点をして、その点数が高かったチームには**賞金10万円**がもらえるというハッカソンでした。ちなみに1位以外でも賞金がもらえるみたいでした。

* 1位: 10万円
* 2位: 3万円
* 3位: 1万円
* 参加賞: 1,000円分の図書カード

うちのチームでは優勝したら焼肉だったかしゃぶしゃぶに行こうみたいな話をしていました。

### つくったもの
うちのチームは認証サーバとトークンを用いた、パスワードを必要としない認証システムの開発をしました。

具体的な仕様等はここでは述べませんが、Webサービスにはパスワード等の重要な情報を保存せず、認証サーバを仲介することで認証を行い、サービス側が機密情報を漏洩してしまうリスクを低減します。

さらにパスワードの代わりに端末（スマホ）一つひとつに固有でセットされるアプリID（推測されない十分に安全な文字列）を使用して、これをパスワード代わりに使うので、ユーザが簡単なパスワードを設定して総当たり攻撃を受けたり、パスワードを使いまわして被害が拡大したりするのを防ぐというメリットがあります。

その代わり、認証サーバは複数のWebサービスの機密情報を管理するので堅牢なセキュリティ機構であることが必須条件となり、また、万が一機密情報が漏洩したときにすべてのサービスが乗っ取られてしまう、といったデメリットもありますが、それ以外は現在のサイバー犯罪の被害を少なくするための良いシステムなんじゃないかなあと考えています。

さて、このハッカソンに参加したチームは10組くらいありましたが、そのうち、うちのチームを含め3チームくらいは技術的なサイバー犯罪防止のためのシステムやツールの開発を行いましたが、残りはすべて、詐欺のシュミレーションを通して実際の詐欺を学ぶゲームアプリ開発やサイバー犯罪被害に対する啓蒙動画制作などでした。

### 大炎上
メインを早速言ってしまうと、このハッカソン、特にTwitterで**大炎上しました**。

文章で説明するよりはみなさんのツイートを見たほうが速いので、ここではぼくが見た大炎上中のツイートを貼っつけていこうと思います。

#### コードタダ売り謎系
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">某ハッカソン，終了と同時に委細告げず成果物徴収(無報酬)しにきて爆笑</p>&mdash; うつろき (@hile_net) <a href="https://twitter.com/hile_net/status/810401462668828672">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">いくらクソコードといえどもソースコードは著作物なので、それを何の目的に使うかも知らずに渡すほど人権は落ちぶれちゃいない</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810404823707201536">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">だいたい警察がハッカソンのコードを回収してどうすんだ？</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810405045904678913">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">ゲームが受賞するのは向こうの選考点によるから別にいいんだけど製作したコードを無償で徴収されるのはさすがに人権が消えてませんかね？</p>&mdash; tattaka (@tattaka_sun) <a href="https://twitter.com/tattaka_sun/status/810419781236969472">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

いやいや、技術のこと知らない人らがソースコード徴収して何するの。そもそもクソコード言ってもコードは著作物だからただでやれるかっての！ 情報リテラシのかけらもねぇ！！

#### 外部から観戦系
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">某、炎上してんの</p>&mdash; かるみす (@roma9_sgsm) <a href="https://twitter.com/roma9_sgsm/status/810405397076975616">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">こんな面白いもの見れたならサイバー犯罪防止ハッカソン見に行きたかったわ</p>&mdash; きょうとき (@egz6gldm21) <a href="https://twitter.com/egz6gldm21/status/810411390280179712">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">某ハッカソン結局燃えたのか</p>&mdash; tattaka (@tattaka_sun) <a href="https://twitter.com/tattaka_sun/status/810414253022658560">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

参加していない人たちにも十分届くくらい炎上してました。

#### 個人的
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">あの警察の押し付け間嫌い。</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810406881332051969">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">2回も弁当を無理やり食わされた</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810406993689124864">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

弁当を無理やり押し付けてくる警察がいてちょっとめんどくさかった。食えない言うてるのに…

#### 評価基準謎系
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">あれ、俺何のハッカソンに来たんだっけ</p>&mdash; うつろき (@hile_net) <a href="https://twitter.com/hile_net/status/810406991961071616">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">ほんま10万.....</p>&mdash; 人権問題 (@tkmru) <a href="https://twitter.com/tkmru/status/810407099708555264">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">友利奈緒が入賞してないの笑う<br>評価基準謎すぎる</p>&mdash; tatsuaki (@tatsuaki85) <a href="https://twitter.com/tatsuaki85/status/810407128271757312">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">セキュリティハッカソンでゲームが受賞</p>&mdash; 人権問題 (@tkmru) <a href="https://twitter.com/tkmru/status/810407363672801280">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">しかも一位TomoriNaoじゃないんかーいww</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810407469188935681">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">ぴんくさん達、めっちゃ良さそうなの作ってたのに、ゲームに負けたのwwww</p>&mdash; きりん@1日目 西み23b (@kkrnt) <a href="https://twitter.com/kkrnt/status/810407661908807680">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">社会ははアプリ開発できるホワイトハッカーを求めているんですね。</p>&mdash; 【TomoriNao】ぴんく (@PINKSAWTOOTH) <a href="https://twitter.com/PINKSAWTOOTH/status/810407086529990656">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">ゲームに負けた技術者の皆さん元気〜^ ^</p>&mdash; きひろちゃん (@aki33524) <a href="https://twitter.com/aki33524/status/810408875505553408">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">賞金つきセキュリティハッカソンで難読化されたバイナリに対してdead code eliminationを施すクソ便利なIDAプラグインの代わりにゲーム？ が受賞したマジ？</p>&mdash; 寝ると体力が回復する (@ntddk) <a href="https://twitter.com/ntddk/status/810409703117324288">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">俺たちが参加したのはサイバーハッカソンじゃなかった<br><br>ゲームハッカソンだった</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810410658789400576">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">サイバー犯罪被害防止に役に立たない技術<br>- tokenを用いた認証システム<br>- 機械学習を用いたサーバ異常検知<br>- マルウェアのデッドコード削除</p>&mdash; 【TomoriNao】ぴんく (@PINKSAWTOOTH) <a href="https://twitter.com/PINKSAWTOOTH/status/810412884748402688">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">うちの班もアイデア的には割と良いものが出来ていたと自負してますが、どうやら警察の方々には理解してもらえなかったようです（傲慢）</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810414868524208128">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">まー制作物例に動画があった時点で察するべきだったし、そもそも参加したのが間違いでしたね</p>&mdash; 人権問題 (@tkmru) <a href="https://twitter.com/tkmru/status/810418438426329090">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">見学に来た高校生をどう活用するかみたいな謎評価軸もあったし参加する前からアレなかんじだった</p>&mdash; 人権問題 (@tkmru) <a href="https://twitter.com/tkmru/status/810418893831311360">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">評価基準に新規性、有用性があったんですが</p>&mdash; 【TomoriNao】ぴんく (@PINKSAWTOOTH) <a href="https://twitter.com/PINKSAWTOOTH/status/810417780742701056">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">犯罪抑止がテーマならゲームのほうが訴求力ありそうだとは思うけど，これで賞を逃した人たちが犯罪者になると盛り上がってくる</p>&mdash; 寝ると体力が回復する (@ntddk) <a href="https://twitter.com/ntddk/status/810416046498807808">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">本日、2位発表時点でTomoriチームもImoriチームも挙がらなかった辺りからずっとただただ笑ってる</p>&mdash; うつろき (@hile_net) <a href="https://twitter.com/hile_net/status/810427058476064768">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">TomoriNao、審査員が理解してなくて評価低いのやばいと思う</p>&mdash; たかひー (@dsgkt4201) <a href="https://twitter.com/dsgkt4201/status/810434004373491712">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">ホワイトハッカーってなんだよ…</p>&mdash; 【TomoriNao】ぴんく (@PINKSAWTOOTH) <a href="https://twitter.com/PINKSAWTOOTH/status/810423608476450816">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">TomoriNao、審査員が理解してなくて評価低いのやばいと思う</p>&mdash; たかひー (@dsgkt4201) <a href="https://twitter.com/dsgkt4201/status/810434004373491712">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

これが今回の炎上のもっとも大きな原因です。そもそも相手は技術をそこまで知らない警察。そして教授も2〜3人しかいない。ほとんど技術知らない人たちが採点したらそりゃ技術的には正当に評価できるわけないでしょ。

だから本当にセキュリティ的なサイバー犯罪防止アイデアよりも、詐欺にひっかからないように訓練するゲームアプリのほうが過大評価されてしまい、大炎上不可避でした。

#### 評価基準分析系
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">今回の評価基準は教授陣のウケの良さなので、技術関係ない説濃厚</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810407688999825408">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">僕の脳内では、<br>「専門外の審査員 vs. テーマ軽視で作るものありきの参加者たち」<br>という構図が浮かび上がっています。</p>&mdash; 誠意 (@lefb766) <a href="https://twitter.com/lefb766/status/810410278638583808">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">警察とかからしたら技術よりもアイデアが欲しかったんじゃないかと…</p>&mdash; изолированный (@yujaku_aa) <a href="https://twitter.com/yujaku_aa/status/810412926691524608">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">サイバー犯罪被害防止って知識の無い人間が被害を受けにくくするにはどうすれば良いですかという話で、知識のある人間がマルウェア解析やらをやりやすくすると言うのは2次的で評価されにくい気がしますね。</p>&mdash; きひろちゃん (@aki33524) <a href="https://twitter.com/aki33524/status/810415395479769088">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">情弱用サイバーハッカソンですね</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810418976429785088">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">審査員やっぱり理解できてないんだなーって感じ</p>&mdash; ノス (@pokenoth) <a href="https://twitter.com/pokenoth/status/810434878369996800">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

技術理解できる人たちがそもそも少ないので、やはりどうしても「技術的なアイデア」よりも「エンジニアじゃない人たちにも理解できるアイデア」が評価されてしまう。

#### 炎上回避案系
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">情弱啓蒙コンテンツアイデアソンだったらそうだと書けばちゃんと想定主旨に合う成果物が出たと思うしRCCもいい迷惑なんじゃないかと思います</p>&mdash; きのうハイカラシティ、きょうは🍣 (@dolpen) <a href="https://twitter.com/dolpen/status/810426568837242881">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">防止ではなく啓蒙と書こうな</p>&mdash; 人権問題 (@tkmru) <a href="https://twitter.com/tkmru/status/810438314050236417">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

そもそも防止という表現が技術的な防止なのか詐欺的な防止なのかが曖昧だったのが炎上の元だった説。そこらへんをもっと明確にしていたら炎上はある程度免れたかもしれない。

ちなみにきつねさんは技術部門賞とかアイデア賞とか、複数の賞を用意すれば良いのではと言っていました。これには自分も同感です。ゲームアプリ的なアイデアと技術的なアイデアを分ければみんな納得行く評価になった気がします。

#### その他
<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">【投票】みなさん、今回のハッカソンどうでした？？？</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810408313267437568">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">ハッカーという単語をやすやすと使うな。</p>&mdash; 【TomoriNao】ぴんく (@PINKSAWTOOTH) <a href="https://twitter.com/PINKSAWTOOTH/status/810414304126070784">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">バスの中でもハッカソン炎上案件</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810418328015470592">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">「圧倒的人権の欠如」<br><br>見事フラグ回収</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810419646146842624">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">ハッカソンの結果不満しかない</p>&mdash; ノス (@pokenoth) <a href="https://twitter.com/pokenoth/status/810425700322660352">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">※審査の一切において、RCCは断じて関与しておりません。 <a href="https://t.co/D38Mm7o2Nu">https://t.co/D38Mm7o2Nu</a></p>&mdash; うつろき (@hile_net) <a href="https://twitter.com/hile_net/status/810428377060360192">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">ありかさんはじめ運営側恨むなんかないですよ。絶対に。あんだけのことやっていただいて恨むわけないじゃないですか。</p>&mdash; らすかる【イモリさん】 (@ehot_rascal) <a href="https://twitter.com/ehot_rascal/status/810438173792686080">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">今回のハッカソン、運営(RCC)は悪くないですよ<br><br>悪いのは京都府警と教授陣なので、恨むならそちらを</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810443032457711616">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">RCC の人たちが風評被害受けないかがわりと心配</p>&mdash; まだダメ (@utgwkk) <a href="https://twitter.com/utgwkk/status/810419919124713472">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">サイバー炎上対策ハッカソン</p>&mdash; ほほえみ108円(税込) (@hohoemi108yen) <a href="https://twitter.com/hohoemi108yen/status/810419164326297604">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

ほかにもまだまだたくさんありました。一つ強調しておきたいのは、今回の件で運営(RCC)は一切評価に関与していないので悪くないです。RCC主催という肩書きにより風評被害が出てしまわないようにこれだけは勘違いしないようにしてほしいです。

### 不満点
炎上とは別に個人的に不満だった点（というか不満のほうが多かった）をざっと紹介します。

* 食事が、弁当、弁当、おにぎり、弁当
* 参加者のほとんどが理系(BKC)なのに衣笠で開催
* 開発スペースが飲食禁止
* 発表時間が5分しかない（過ぎたら強制終了）

食事が出るだけまだマシですが、4食のうち3食が弁当で1食がおにぎりというのはお粗末じゃないですか…しかも基本的に冷めてるし地味に量が多くて油ものでヘビーなせいで、食べるだけで精神削られていく。「今は食べられないからいいです」って言っても警察の人には無理やり食わされるし…

あと、ハッカソンの事前準備として1ヶ月くらい前にアイデアソンがあったときはBKCだったのに、なんで当日衣笠になるの…聞いた話によるとBKCの宿泊施設がすでにプロジェクト団体によってリザーブされてたみたです。でも、みんなだいたいBKCの人たちなんだから、BKCでハッカソン出来るくらいは手配してほしかった。

開発スペースは飲食禁止。だから飲み物を飲むためにわざわざ廊下に行って、飲み終わったら帰ってくるって感じ。もちろんお菓子などは食べられない。汚したくないのはわかるけど、ハッカソンは基本的に開発がんばる期間なので、飲食禁止されるとつらい。

さらに2日間かけて作る成果物なのに実演も併せて発表するのに5分しかない。実際、全体の仕組みをちゃんと理解してもらうためには5分なんかじゃ絶対足りないから中途半端なところまでしか発表できないし…LTじゃないんだからせめて10分くらいは発表する時間が欲しかったのが素直な感想です。

という感じで、基本的に最低限の環境しか与えられていない状況で開発していました。歯ブラシ、タオル等は当然ないので持参だし、さらにシャワールームにはシャンプーやボディソープも置いてないので、持ってこないと身体を洗ったりできないらしい…いやだからBKCでやれよって…ｗ

もちろんシャンプーやボディソープを家から持ってくるのは難しいので、シャワーだけしか浴びれない環境でした。まあ今回は人権を失っていたのでそもそもシャワールームに入ることすらなかったんですが…

あと4人で入るのには狭すぎる寝室。ベッドと机があって、その間は人2人がぎりぎり通れるくらいの小さな部屋でした。

門限が10時までだったので初日の夜10時前にコンビニに行ってお菓子を買って帰ってきたんですが、そもそも宿泊施設が僻地なので、一番近いコンビニまで行くのに歩いて10分近くかかったりとか、とにかくツッコミポイント満載でした。

### ハッカソン1日目
1日目は10時半からの開始でした。10時半となると電車やバスで行くことを考えて、家を8時すぎ、遅くても8時半までには家を出ないといけなかったのですが、自分は盛大に遅刻をかましてしまい、**起きたのが11時**でした。急いで支度して出発して、着いたのが3時間遅れの1時半でした。いやはや、生活習慣が乱れていて遅刻グセが治らないのはつらいです(´・ω・`)

んで、3時間も遅れてしまったので急いで開発に回ろうと作業し始めたら、しばらくして例の警察の人ですよ。弁当が君の分だけ余っちゃうから食べてくれと言われて、自分は特に食べたくなかったのに食べることになりました。

しかも食べている間におやつの時間が来て、みんながドーナツやどら焼きを食べている間に自分ひとりだけ弁当を食べているという、非常に気まずい状況でした…いや自分が遅刻したのが悪いんだけどね、一人で飯食ってる所にみんなが集まってきて、おやつ食べてるわけですよ、なんであいつ弁当食ってんだみたいな感じで思われても不思議じゃないです。本当気まずかった…

というわけで1日目、開発を始めたのは3時半くらいからでした。その前にサーバの環境構築とか整えたりしてたのでコードを書き始めたのは4時過ぎだったと思います。

Androidアプリ開発（端末アプリの開発）と認証サーバの開発、それからWebサービス開発のうち、自分はWebサービス開発を担当しました。

まずWebサービスのサンプル（プレゼンで見せる部分）のページを表示して、こういうサービスにログインすることを想定しています、ということをやりたかったので、サンプルページを作りました。今回はショッピングサイトを例にして、商品の画像とか値段、購入ボタンなんかを商品ごとに表示しました。

途中からふざけ始めてRCCの人が写っている写真を商品の画像にして、値段: price less とかやって爆笑してましたｗｗ

そんなことをしながらもテンプレートを使って適当にいい感じにデザインを書いてサンプルページを完成させました。

そこからは認証サーバからのトークンとアプリからのトークンを受け取る処理とか一致しているか調べる処理とかを書き始めようとしたのですが、そのときに仕様書がよくわからなくなってきて、どう実装したらいいか悩む時間に突入しました。

そんな感じで時間が経っていき、9時が過ぎたので、とりあえずみんなでコンビニに行ってお菓子だけ買って門限10時になる前に帰ってきました。

そのあとは寝室で作業が始まるのがと思いきや高校生との相談とかもあって共有ラウンジみたいなところで作業がはじまりました。ちょうどそのあたりからやる気が出始めてプログラムをどう書けばいいか整理がついてきたので一気に書き始めました。

やる処理としてはそんなに難しくはないのですが、受け取るデータの形式とかそこらへんの細かい仕様を決めてなかったのでコーディングは思ったように進まないこともあり、そんな感じでだらだらと開発を進めていくうちに時間は夜中の3時くらいになってました。だいたいその時間くらいにある程度の処理が出来てきたので、あとはエラーを吐いていた部分とか細かい部分を修正して夜中の4時くらいに寝室に戻りました。

これだったらまあ数時間は寝れるかな、と思ったんですが、Androidアプリ側で受け取るデータ形式とかの、連携部分がうまいこと行ってなかったので、その部分を修正したりしてたら結局7時くらいになってしまい、外も明るくなり始めました。しかし、その頃ちょうどアプリ側も認証サーバ側もほとんど完成していました。

チームのほかの人たちはみんな仮眠程度に寝たのですが、自分は生活習慣が乱れているせいであまり眠れなかったのと細かい修正がまだ残っていたのでそれを修正ているうちに8時を回ってしまい、寝室を出なければいけないのは9時なので、結局寝る暇もなく朝食のおにぎり3個（お粗末…）を支給されて、そのうちの1個だけを食べて開発スペースに移動しました。

ちなみに残った2個は昼が来る前にこっそりと箱の中に戻してもらいました。

### ハッカソン2日目
開発スペースで開発を始めようとした辺りからだんだん眠くなり始めて、全く手が動かなくなりました。ただそうなる前にすでにやるべき処理は済んでいたので、プレゼンの発表準備を一緒に考えていたりしました。

ところがなぜか途中から高校生の相手をすることになり、やることも特にないので、眠い目をこすりながらHTMLやCSS, JavaScriptなんかを教えていました。教えると言っても本当に基礎的なことを部分的に説明しただけなんですけどね。でもそのあと自分が教えなくても自主的にネットで調べてたりしたので、Webに興味があるのかな？と思いました。

そんな感じで頭がぼけぼけしているうちに12時が周り、1時になり、昼食の時間がやってきました。最悪食べなくてもいいと運営側に言われたけど、チームメンバーで言ったら、またあの警察の人がいて、またもや強制的に弁当を渡されて結局食べることになりました。眠くて食事する気分じゃないんだって…

なんか今回のハッカソンでは、弁当とおにぎりしか出ないせいか、全く食欲がわかなかったです。結局無理やり食わされることにはなったけど。

お茶でご飯を流し込み駆動開発をして無事に食べ終えたので、そのからはプレゼン発表者のプレゼンをときどきチェックしたり、ぼけぼけしてました。やっぱり徹夜はダメだね、眠くなってきてからだと全然やる気が起こらない。

そんなこんなしているうちに発表の3時が訪れてきました。しかも運の悪いことに、自分のチームはトップバッターだったので一番最初に発表しました。発表はリーダーが担当したので自分は発表してませんが、5分と短い時間なのであっという間に終わってしまいました。正直あの短い時間で認証の仕組みが伝わっているかというと伝わってないように思います。

そのあとは他のチームの発表を聞いてTwitterで実況したりしてました。技術的にサイバー犯罪を防ぐ発表はおもしろかったのですが、なにせほとんどのチームはゲームアプリ開発だったので途中から退屈になりました。

すべてのチームの発表が終わった後、いよいよ順位発表になりました。自分の予想ではTomoriNaoチームが優勝で、パケット解析をしていたチームが準優勝かと思っていましたが、前述の通り、評価するのは技術者ではないので、技術的なセキュリティの内容をしていた自分のチームや、TomoriNaoチーム、パケット解析をするチームはランキング4位にも入りませんでした（同立3位がいたので、4チームが表彰され、賞金をゲットしました）。ここでTwitterで大炎上の嵐が始まりました。

なんにせよ、自分は10万円もらえると思ってなかったし、そのときはとにかく眠いしフロにも入っていないのでとっとと解散して欲しいという気持ちでいっぱいでした。

解散した後はメンバーのみんなとTomoriNaoのピンクさんと一緒のバスに乗り、炎上の話をしつつTwitterしながら帰りました。

で、無事最寄り駅まで着いた後、そのまま家に向かうと思いきや、自分はこのブログ記事を更新したかったのでピンクさんと一緒に研究室まで来ました。そして今この記事を書いています。

実はこの記事を書いている間も眠くて何度か寝落ちしているのですがなんとか書けています。

そんな感じで、2日目はとにかく眠いという感想以外ありませんでした。睡眠はやはり重要です。

### 失った人権
「圧倒的人権の欠如」というチーム名、今回のハッカソンで見事にフラグを回収しました。

* 徹夜でコード書いて寝れない
* シャワーも浴びていない
* せっかく作った成果物も技術的に正当に評価されない

こんな感じです。3つのうち上記2点は実装をもっと速くしていれば解決したかもしれないですが、設計の理解と細かい仕様と実装力の足りなさのせいで結局徹夜になってしまいました。さらにシャワーも浴びれなかった。

そして大炎上している通り、自分たちの成果物は、とてもフェアに評価されているとは言い難いです。

というわけで徹夜してコードを書いたのに優勝も準優勝も準々優勝もできずに終わってしまいました。まさに「圧倒的人権の欠如」です。

### 感想
今回はじめてハッカソンに参加しましたが、徹夜するとは思ってなかったし、正直自分には合わないかなと思いました。時間に追われて作るのとか義務的に作るようなコードは全然書く気になれないので、もっと自分のペースに合わせて自由に書ける環境のほうがいいです。

それにチーム開発ということで他の担当ともうまいこと連携を取ってやらないといけないのですが、徹夜でやっていることもあり、若干チーム内でおだやかじゃない部分があったりして個人的には楽しんで開発するという感覚はほとんどなく、むしろ苦痛を感じながらコードを書いていました。でも、楽しくないと参加する気もないし、自分からわざわざイライラするような環境でコードを書くイベントに参加するほどマゾではないです。

というわけでハッカソンの闇を体感したので、しばらくはハッカソンに参加するつもりはありません。ぶっちゃけ言うと、このハッカソンは楽しいとは言えなかったし、人権も失ったし自分にとってプラスになることがほとんどありませんでした。しいて言うなら大炎上を目の当たりにしてみんなで炎上大会に参加できたことくらいです。

兎にも角にも、運営の皆さん、それからハッカソンに参加したみなさん、本当にお疲れさまでした。

とりあえずうちに帰って風呂入って寝る…

### おまけ（Twitter）
炎上以外のツイートもたくさんあったので適当にみなさんのツイートをかいつまんでまとめます。

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">開発楽しいなあ！！(闇) <a href="https://twitter.com/hashtag/%E3%82%B5%E3%82%A4%E3%83%90%E3%83%BC%E3%83%8F%E3%83%83%E3%82%AB%E3%82%BD%E3%83%B3?src=hash">#サイバーハッカソン</a> <a href="https://t.co/DAfgoB5etS">pic.twitter.com/DAfgoB5etS</a></p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810036736453509120">2016年12月17日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr"><a href="https://twitter.com/hashtag/%E3%82%B5%E3%82%A4%E3%83%90%E3%83%BC%E3%83%8F%E3%83%83%E3%82%AB%E3%82%BD%E3%83%B3%E3%81%AE%E9%97%87?src=hash">#サイバーハッカソンの闇</a><br>やったーこれで夜を乗り越えられる <a href="https://t.co/IXYTgRBrIp">pic.twitter.com/IXYTgRBrIp</a></p>&mdash; tatsuaki (@tatsuaki85) <a href="https://twitter.com/tatsuaki85/status/810036532480356352">2016年12月17日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">サイバー犯罪被害防止ハッカソンは無事終了しました。<br>結果は以下のとおりです。<br>1位:「Rプレアデス5飯セット」<br>2位:「チームさいばっち！」<br>3位:「すばるGO」,「やきいもブラザーズ」<br><br>参加者の皆さんお疲れさまでした！</p>&mdash; 立命館コンピュータクラブ (@rits_rcc) <a href="https://twitter.com/rits_rcc/status/810427846984286209">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">某ハッカソン、準備から何まで大変そうでしたね</p>&mdash; ABCanG(阿部) (@ABCanG1015) <a href="https://twitter.com/ABCanG1015/status/810409398413574144">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">とりあえず、RCCの某ハッカソンの担当者各位運営お疲れ様でした</p>&mdash; ABCanG(阿部) (@ABCanG1015) <a href="https://twitter.com/ABCanG1015/status/810412290994380800">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">某圧倒的人権のなんとかチーム，アイデアソンの頃に「コンピュータウィルスの感染経路とかを伝える演劇を作って実演する」っていうふざけた案があった気がするどもしかしてそれやってたら良いとこ行ってた？</p>&mdash; WGG (@WGG_SH) <a href="https://twitter.com/WGG_SH/status/810410097277104128">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">サイバー犯罪防止ハッカソンの作品見てみたいなー|ω•)ﾁﾗｯ</p>&mdash; きょうとき (@egz6gldm21) <a href="https://twitter.com/egz6gldm21/status/810414953593061376">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

↑これに関してですが、RCCの方はbitbucketからコードが見れるようになってます。ただしハッカソンで切羽詰まって書いたクソコードなのであまり参考にはしないでください…自分はWebサービスの処理を書きました。

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">僕も参加してないから優勝したゲーム(多分?)がどんなものか知りたい&amp;やってみたい</p>&mdash; WGG (@WGG_SH) <a href="https://twitter.com/WGG_SH/status/810415805603184640">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">サイバー犯罪被害防止ハッカソンに参加された皆様、本当にお疲れ様でした。多くの人に色々無理を言いつつも参加してもらいました。本当にありがとうございました。<br>皆様が技術なり知識なり友人なり何か１つでも得て帰られたなら幸いです。<a href="https://twitter.com/hashtag/%E3%82%B5%E3%82%A4%E3%83%90%E3%83%BC%E3%83%8F%E3%83%83%E3%82%AB%E3%82%BD%E3%83%B3?src=hash">#サイバーハッカソン</a></p>&mdash; ありか (@arika_nashika) <a href="https://twitter.com/arika_nashika/status/810430238198874112">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">サイバー犯罪なんとかハッカソンお疲れさまでした</p>&mdash; えだまめ (@r_edamame) <a href="https://twitter.com/r_edamame/status/810454088957587457">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">現在、衣笠キャンパスにてサイバー犯罪被害防止ハッカソンが行われています。<br>大学生と高校生がサイバー犯罪の防止に貢献する制作を行っています。<br>明日の発表に向けて皆さん頑張ってください！ <a href="https://t.co/fxFxgCbxe2">pic.twitter.com/fxFxgCbxe2</a></p>&mdash; 立命館コンピュータクラブ (@rits_rcc) <a href="https://twitter.com/rits_rcc/status/810097498303803392">2016年12月17日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">RCCの皆さん運営ありがとうございました！</p>&mdash; 【TomoriNao】ぴんく (@PINKSAWTOOTH) <a href="https://twitter.com/PINKSAWTOOTH/status/810432455660294144">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

### おまけ（戦利品）
出かけるときは一切食べもの持ってきてないのに、帰ってきたときにはお菓子が大量に増えた、逆遠足状態になった。

![グリコ](https://raw.githubusercontent.com/noraworld/blog-content/main/cyber-hackathon-trolling-2016/glico_box.jpg)

![グリコ](https://raw.githubusercontent.com/noraworld/blog-content/main/cyber-hackathon-trolling-2016/glico_content.jpg)

![お菓子](https://raw.githubusercontent.com/noraworld/blog-content/main/cyber-hackathon-trolling-2016/snack.jpg)

![レッドブル](https://raw.githubusercontent.com/noraworld/blog-content/main/cyber-hackathon-trolling-2016/red_bull.jpg)

### さいごに
**繰り返しになりますが、この記事には追加記事（下のリンク先）があります。情報の訂正や誤解を生んでしまった発言の弁解と反省等について書かれています。ネット上で意見を述べる場合は必ずそちらの記事も読んだ上でお願いします。**

[サイバー犯罪被害防止ハッカソン炎上記事の後日談](https://noraworld.blog/cyber-hackathon-trolling-2016-sequel/)
