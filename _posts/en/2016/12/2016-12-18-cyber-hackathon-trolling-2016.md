---
layout: post
title: Overview of the Cybercrime Victim Prevention Hackathon and Summary of the Major Controversy
date: '2016-12-18 16:39:24'
tags:
- university-life
- event
- development
published: true
---

**About this article: I have posted an additional article concerning this post. If you intend to express your opinion or write comments about this article on Twitter or elsewhere, please ensure you read the additional article before doing so.**

[Follow-up on the Cybercrime Victim Prevention Hackathon Controversy Article](https://noraworld.blog/cyber-hackathon-trolling-2016-sequel/)

From December 17th (Saturday) to 18th, my organization RCC hosted a "Cybercrime Victim Prevention Hackathon." As an RCC member, I participated under the team name "Overwhelming Absence of Human Rights." I'll introduce how we managed to live up to that name later.

This hackathon was a collaboration between RCC and the Kyoto Prefectural Police.

### What kind of hackathon was it?
Recently, cybercrime seems to be never-ending (for example, phishing scams and ransomware), so the idea was to devise technical countermeasures to reduce victims of cybercrime.

Each team was composed of a group they formed by themselves, plus about two high school students. Assigning tasks effectively to the high school students also seemed to be an important objective.

Each team presented their final creation, and the Kyoto Prefectural Police and faculty members judged them. The team with the highest score would receive **a prize of 100,000 yen**. Apparently, teams besides the first place also received prize money.

* 1st: 100,000 yen
* 2nd: 30,000 yen
* 3rd: 10,000 yen
* Participation prize: 1,000 yen worth of book cards

Our team talked about going for either a yakiniku dinner or a hot pot meal if we win.

### What we created
Our team developed an authentication system using an authentication server and tokens, eliminating the need for passwords.

I won't go into specifics here, but the idea is to authenticate through a mediation service rather than storing important information like passwords on the web service. This helps reduce the risk of sensitive information being leaked by the service.

Furthermore, by using a unique application ID (a sufficiently secure string not easily guessed) associated with each device (smartphone) instead of passwords, it prevents the risks of users setting simple passwords subject to brute-force attacks or reusing passwords expanding the damage.

However, since the authentication server manages the sensitive information for multiple web services, it must have solid security mechanisms, and there's the disadvantage of all services being compromised if that sensitive information ever leaks. Despite this, we believe it is an ideal system to minimize cybercrime damage today.

There were about ten teams participating in this hackathon. While about three teams, including ours, developed systems or tools for technical cybercrime prevention, the rest developed educational video content for cybercrime awareness or game apps simulating fraud to learn about it interactively.

### Major Controversy
To directly get to the point, there was **a significant controversy on Twitter** surrounding this hackathon.

Instead of me explaining it through text, you should look at these tweets to understand the situation better.

#### Code-free selling mystery series

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">某ハッカソン，終了と同時に委細告げず成果物徴収(無報酬)しにきて爆笑</p>&mdash; うつろき (@hile_net) <a href="https://twitter.com/hile_net/status/810401462668828672">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">いくらクソコードといえどもソースコードは著作物なので、それを何の目的に使うかも知らずに渡すほど人権は落ちぶれちゃいない</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810404823707201536">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">だいたい警察がハッカソンのコードを回収してどうすんだ？</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810405045904678913">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">ゲームが受賞するのは向こうの選考点によるから別にいいんだけど製作したコードを無償で徴収されるのはさすがに人権が消えてませんかね？</p>&mdash; tattaka (@tattaka_sun) <a href="https://twitter.com/tattaka_sun/status/810419781236969472">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

No, no, what are they going to do with source code collected by people with no technical understanding? Even as "bad code," code is intellectual property, and you can't just hand it over for free! No sense of information literacy at all!!

#### Observers from outside series

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">某、炎上してんの</p>&mdash; かるみす (@roma9_sgsm) <a href="https://twitter.com/roma9_sgsm/status/810405397076975616">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">こんな面白いもの見れたならサイバー犯罪防止ハッカソン見に行きたかったわ</p>&mdash; きょうとき (@egz6gldm21) <a href="https://twitter.com/egz6gldm21/status/810411390280179712">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">某ハッカソン結局燃えたのか</p>&mdash; tattaka (@tattaka_sun) <a href="https://twitter.com/tattaka_sun/status/810414253022658560">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

The controversy was widespread enough to reach those who were not even participating.

#### Personal series

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">あの警察の押し付け間嫌い。</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810406881332051969">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">2回も弁当を無理やり食わされた</p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810406993689124864">2016年12月18日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

It was a hassle dealing with police officers who were insistent on forcing us to eat boxed lunches. Even when I said I couldn't eat...

#### Mysterious evaluation criteria series

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

...

As already mentioned, police who don't understand technology evaluated the projects, and there were only 2-3 professors. Of course, it's impossible to evaluate technical things fairly when the evaluators mostly lack technical knowledge.

Thus, ideas for actual security-driven cybercrime prevention were undervalued compared to a game app for training people not to fall for scams, leading to inevitable controversy.

...

#### Flames avoidance series

...

The ambiguous usage of "prevention" — whether it meant technical prevention or scam prevention — is suggested to be a root cause of the controversy. Clarifying this beforehand might have avoided some of the backlash.

Incidentally, Kitsune mentioned that multiple awards like technical division awards or idea awards might be ideal. I agree with this. Separating game app ideas and technical ideas could have led to a more widely accepted evaluation.

...

Above all, remember that the operation (RCC) had nothing to do with the evaluation; therefore, should not bear any blame for the incident. Please don't misunderstand this due to the association with the RCC name.

...

### Discontent Points
Apart from the controversy, here are some personal points of dissatisfaction:

* Meals were just boxed lunches, boxed lunches, rice balls, boxed lunches
* Held at Kinugasa despite most participants being from science (BKC)
* No food allowed in the development space
* Presentation time is only 5 minutes (forced to stop if exceeded)

It's still something to have meals provided, but having 3 out of 4 meals as boxed lunches and 1 meal as rice balls seems inadequate... Also, they're cold and greasy, making them hard to finish. Even saying "I can't eat now," police still forced them on us...

Also, why hold it at Kinugasa when the ideathon was at BKC a month ago? From what I've heard, the BKC accommodation was already reserved by a project group. But at least there should have been arrangements to hold the hackathon at BKC where most were from.

No food allowed in the development space, so we had to go out to the hallway to drink. Snacks weren't allowed either. Understanding the desire to keep things clean, hackathons are intensive development periods, so it's tough when eating and drinking are restricted.

On top of that, only 5 minutes to present results developed over two days. Presenting the system's entirety isn't feasible in such a short window, leading to incomplete presentations. It's not like an LT; at least 10 minutes would have been appreciated.

Under such bare minimum conditions, development continued. Necessities like toothbrushes, towels, etc., were not provided (had to be brought), and the shower room lacked shampoo or body soap, meaning you couldn't wash up unless brought. Why not host at BKC...?

It was virtually impossible to bring shampoo or body soap from home, leaving the option of just a shower. But I didn't enter the shower anyway, having lost human rights this time...

The lodging room was too small for four people. With beds and desks side by side, it was barely wide enough for two people to squeeze through.

With curfew at 10 PM, we headed to the convenience store before it to buy snacks, but it took nearly 10 minutes on foot due to the isolated location. There were a lot of things to point out...

...

### Closing Thoughts
This was my first hackathon experience, which wasn't enjoyable. I prefer environments where I can code freely at my pace rather than under obligation.

Moreover, as a team project, communication and synergy are crucial, but with exhaustion setting in, internal harmony frayed, leaving little joy in development. I didn’t join this event to put myself in an uncomfortable coding situation willingly.

Having witnessed the dark side of hackathons, I'm not eager to participate again soon. Honestly, this hackathon brought no enjoyment or real gains for me, except witnessing the massive controversy and joining the flame battle with others.

Regardless, thanks to the organizers and participants.

Time to get home, take a bath, and sleep...

### Bonus (Twitter)
In addition to the controversy, various tweets were made, so here's a curated selection:

<blockquote class="twitter-tweet" data-lang="ja"><p lang="ja" dir="ltr">開発楽しいなあ！！(闇) <a href="https://twitter.com/hashtag/%E3%82%B5%E3%82%A4%E3%83%90%E3%83%BC%E3%83%8F%E3%83%83%E3%82%AB%E3%82%BD%E3%83%B3?src=hash">#サイバーハッカソン</a> <a href="https://t.co/DAfgoB5etS">pic.twitter.com/DAfgoB5etS</a></p>&mdash; のら (@noraworld_jp) <a href="https://twitter.com/noraworld_jp/status/810036736453509120">2016年12月17日</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

...

The RCC people had access to bitbucket for viewing the code. Though it involves rough code written under hackathon pressure, so don't use it as a reference... I handled the web service processing.

...

### Bonus (Loot)
Left with much more snacks than I originally brought, an inverse of a typical outing.

![Glico](https://raw.githubusercontent.com/noraworld/blog-content/main/cyber-hackathon-trolling-2016/glico_box.jpg)

![Glico](https://raw.githubusercontent.com/noraworld/blog-content/main/cyber-hackathon-trolling-2016/glico_content.jpg)

![Snacks](https://raw.githubusercontent.com/noraworld/blog-content/main/cyber-hackathon-trolling-2016/snack.jpg)

![Red Bull](https://raw.githubusercontent.com/noraworld/blog-content/main/cyber-hackathon-trolling-2016/red_bull.jpg)

### Lastly
**Again, there is an additional article related to this post (link below), addressing corrections and reflections on certain remarks misinterpreted in the original post. Ensure to read the additional article before expressing any opinions online.**

[Follow-up on the Cybercrime Victim Prevention Hackathon Controversy Article](https://noraworld.blog/cyber-hackathon-trolling-2016-sequel/)
