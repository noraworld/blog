---
title: "ソーシャルサポートワーク"
description: "自分との心理的距離を同心円で可視化するネットワークリスト。"
# image: https://noraworld.github.io/box-venusaur/2026/06/20/6a5da0598c82f2ffbda420e0e733b5ed.png
image: https://noraworld.github.io/box-venusaur/2026/06/20/7cd388471af4d7725d64a42665329daf.png
date: 2026-06-20 17:00:00 +09:00
tags:
  - notes
  - wellbeing
references:
  # - TODO_REFERENCES
  - https://chatgpt.com/c/6a36264b-daf8-83ee-b83c-e1bb6f98f8a9
  # - https://chatgpt.com/share/12345678-90ab-cdef-0123-456789abcdef
note_disabled: true
translation: false
---

### ネットワークリスト
<div id="network"></div>

<script src="https://d3js.org/d3.v7.min.js"></script>
<script>
  // ============================================================
  // 編集するのは基本的にここだけ
  // ============================================================

  const data = {
    center: "私",
    nodes: [
      // ネットワークリストの書き方の例
      //   { name: "上司", distance: 4 },
      //
      // こだわりたい場合だけ angle の個別指定も可
      //   { name: "母", distance: 2, angle: -30 },
      //
      // コピペ用
      //   { name: "", distance:  },
      //   { name: "", distance: , angle:  },
      //
      // ルール
      //   * distance 順に並び替える必要はない
      //   * トレイリングカンマはつけておいたほうがいいかも

      { name: "友人C", distance: 1 },
      { name: "友人B", distance: 1 },
      { name: "兄", distance: 1 },

      { name: "恩師", distance: 2 },
      { name: "母", distance: 2 },
      { name: "ネット掲示板", distance: 2 },
      { name: "ランニングクラブ", distance: 2 },

      { name: "父", distance: 3 },
      { name: "行きつけの店の人", distance: 3 },
      { name: "営業部のAさん", distance: 3 },

      { name: "上司", distance: 4 },
      { name: "タイラー・ダーデン", distance: 4 },
      { name: "医者のDさん", distance: 4 },

      { name: "上司", distance: 5 },
      { name: "タイラー・ダーデン", distance: 5.3 },
      { name: "医者のDさん", distance: 5.7 },

      { name: "上司", distance: 6 },
      { name: "タイラー・ダーデン", distance: 6 },
      { name: "医者のDさん", distance: 6 },
    ]
  };

  // ============================================================
  // 以下は基本的に編集不要
  // ============================================================

  const width = 900;
  const height = 900;
  const cx = width / 2;
  const cy = height / 2 + 30;

  const centerRadius = 46;
  const firstRingGap = 65;
  const ringStep = 95;
  const goldenAngle = 137.507764;

  const maxDistance = Math.max(...data.nodes.map(d => d.distance));

  function radiusForDistance(distance) {
    if (distance === 1) {
      return centerRadius + firstRingGap;
    }

    return centerRadius + firstRingGap + ringStep * (distance - 1);
  }

  function toRad(deg) {
    return deg * Math.PI / 180;
  }

  function normalizeAngle(deg) {
    return ((deg % 360) + 360) % 360;
  }

  function estimateLabelWidth(text) {
    return text.length * 24;
  }

  function estimateLabelHeight() {
    return 30;
  }

  const nodes = data.nodes.map((node, index) => {
    const angle = node.angle ?? (-90 + index * goldenAngle + node.distance * 23);
    const radius = radiusForDistance(node.distance);
    const rad = toRad(angle);

    const x = cx + Math.cos(rad) * radius;
    const y = cy + Math.sin(rad) * radius;

    const normalized = normalizeAngle(angle);
    const isLeft = normalized > 90 && normalized < 270;

    const labelDistance = 38;

    return {
      ...node,
      angle,
      x,
      y,
      labelX: x + Math.cos(rad) * labelDistance,
      labelY: y + Math.sin(rad) * labelDistance,
      labelTargetX: x + Math.cos(rad) * labelDistance,
      labelTargetY: y + Math.sin(rad) * labelDistance,
      labelWidth: estimateLabelWidth(node.name),
      labelHeight: estimateLabelHeight(node.name),
      anchor: isLeft ? "end" : "start"
    };
  });

  const svg = d3.select("#network")
    .append("svg")
    .attr("viewBox", `0 0 ${width} ${height}`)
    .attr("role", "img")
    .attr("aria-label", "ネットワークサークル");

  for (let distance = 1; distance <= maxDistance; distance++) {
    svg.append("circle")
      .attr("class", "ring")
      .attr("cx", cx)
      .attr("cy", cy)
      .attr("r", radiusForDistance(distance));
  }

  svg.append("circle")
    .attr("class", "center")
    .attr("cx", cx)
    .attr("cy", cy)
    .attr("r", centerRadius);

  svg.append("text")
    .attr("class", "center-label")
    .attr("x", cx)
    .attr("y", cy)
    .text(data.center);

  const nodeGroup = svg.selectAll(".node")
    .data(nodes)
    .enter()
    .append("g")
    .attr("class", "node");

  nodeGroup.append("circle")
    .attr("class", "dot")
    .attr("r", 12)
    .attr("cx", d => d.x)
    .attr("cy", d => d.y);

  const leaderLines = nodeGroup.append("line")
    .attr("class", "leader-line")
    .attr("x1", d => d.x)
    .attr("y1", d => d.y);

  const labels = nodeGroup.append("text")
    .attr("class", "label")
    .attr("text-anchor", d => d.anchor)
    .text(d => d.name);

  const simulation = d3.forceSimulation(nodes)
    .force("x", d3.forceX(d => d.labelTargetX).strength(0.18))
    .force("y", d3.forceY(d => d.labelTargetY).strength(0.18))
    .force("collide", d3.forceCollide().radius(d => {
      return Math.max(d.labelWidth / 2, d.labelHeight) + 12;
    }).strength(1))
    .force("radial", d3.forceRadial(d => {
      return radiusForDistance(d.distance) + 45;
    }, cx, cy).strength(0.12))
    .stop();

  for (let i = 0; i < 500; i++) {
    simulation.tick();
  }

  labels
    .attr("x", d => d.x)
    .attr("y", d => d.y);

  leaderLines
    .attr("x2", d => d.x)
    .attr("y2", d => d.y);

  labels
    .attr("text-anchor", d => d.x < cx ? "end" : "start");

  const bbox = svg.node().getBBox();
  const padding = 50;

  svg.attr(
    "viewBox",
    `${bbox.x - padding} ${bbox.y - padding} ${bbox.width + padding * 2} ${bbox.height + padding * 2}`
  );
</script>

<style>
  #network svg {
    width: 100%;
    max-width: 900px;
    display: block;
    margin: auto;
    overflow: visible;
  }

  #network .ring {
    fill: none;
    stroke: #999;
    stroke-width: 1.5;
  }

  #network .dot,
  #network .center {
    fill: #1f1715;
  }

  #network .label {
    font-size: 24px;
    font-weight: 700;
    fill: #1f1715;
    paint-order: stroke;
    stroke: white;
    stroke-width: 5px;
    stroke-linejoin: round;
  }

  #network .leader-line {
    stroke: #aaa;
    stroke-width: 1.2;
    fill: none;
  }

  #network .center-label {
    font-size: 26px;
    font-weight: 700;
    fill: white;
    text-anchor: middle;
    dominant-baseline: central;
  }
</style>





### 目的
他者とのつながりの感覚を増やして、脳に安心感を与えるため。

### 影響
その影響力は想像より大きく、孤独感はタバコや運動不足よりも身体に悪いと報告されている。

### 手順
1. 自分の社会的ネットワークに存在する人を、思いつくだけリストアップする
    * なかなか思い浮かばない場合は、次の例を参考にする
        * **親しい人**: 親しい友人、家族、同僚など
        * **顔見知りの人**: たまに挨拶する隣人、いつものコンビニの店員、よくすれ違う人など
        * **あこがれの人**: 自分が理想とする人、尊敬する過去の偉人、好きな映画や本の架空のキャラクターなど
        * **助けになりそうな人**: 主治医、かつての恩師、法律相談所、ネットのコミュニティなど
2. それぞれの人物について「私はこの人にどれくらい親密さを感じるだろうか？」と考え、親しみを感じる人やキャラクターを **最低でも 15 人ほど** ネットワークリストのサークルに書き込む
    * 上記の `<script>` タグ内の `data.nodes[*]` に以下のキーを持ったプロパティを記入する（例: `{ name: "上司", distance: 4 }`）
        * `name`: 自分の社会的ネットワークに存在する人やキャラクターの名前または属性（例: `"上司"`）
        * `distance`: 該当する人やキャラクターとの親密度（例: `4`）
            * 親しみが大きい人ほど `distance` の値を小さくする（円の内側に配置する）
            * 一応、少数も使える（整数で円周上、少数で円と円の間に配置される）
    * 以下の「ネットワークリストサークルの例」の図を参考にする
3. 記入を終えたサークルを見ながら、次の質問について考えてみる
    * この中でどの人物ともっと時間を過ごしたいだろうか？
    * 親密な人と接触する時間を増やすために、何ができるだろうか？
    * いまの悩みや困りごとを相談できる人はいるだろうか？ もしいない場合は、専門の組織や機関、自助グループに相談はできないだろうか？
4. これからの人生で新たな人が現れたら、随時リストに加えていく

<details>
<summary>ネットワークリストサークルの例</summary>

![ネットワークリストサークルの例](https://noraworld.github.io/box-venusaur/2026/06/20/c3c6bf761d3e185275abf528ff48ff52.png)
</details>

### 用途
ネガティブな感情がわいたとき（特に孤独感に襲われたとき）に見返す。

### 効果
たいていの人は「私は社会の中で生きている」や「いざというときに頼れる人やキャラがいる」という事実にあらためて気づき、直後からストレス反応が低下する。

### 参考
* [無（最高の状態）](https://www.amazon.co.jp/dp/B099DDJSL9)（第 3 章 結界 ソーシャルサポートワーク）
