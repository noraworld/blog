---
layout: post
title: "ネットワークリスト"
author: noraworld
description: "自分との心理的距離を同心円で可視化するネットワークリスト。"
date: 2026-06-20
tags:
  - notes
  - wellbeing
---

本文をここに書く。

<div id="network"></div>

<script src="https://d3js.org/d3.v7.min.js"></script>
<script>
  const data = {
    center: "私",
    nodes: [
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

      // 必要なら個別指定も可
      // { name: "母", distance: 2, angle: -30 }
    ]
  };

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
