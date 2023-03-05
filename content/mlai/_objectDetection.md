---
title: "物体検出 - Object Detection"
date: "2021-08-20"
draft: true
categories:
  - "Python"
tags:
  - "python"
  - "Data Science"
  - "E資格"
---


---

# 物体検出 - Object Detection

物体認識凄さがわかるTEDトーク

{{< youtube Cgxsv1riJhI >}}


## R-CNN (Regional CNN)

一連の流れは以下の通りです。

1. オブジェクト候補領域RoI(Region of Interest)を選択的探索(Selective Search)で特定
2. 特定したRoIをリサイズしてCNNへ入力
3. SVMによって画像カテゴリを識別
4. Bounding Boxの回帰

R-CNNの課題
- 候補領域ごとにCNNを行う必要がある
- 候補領域の計算量が膨大

https://arxiv.org/abs/1311.2524

##　Fast R-CNN

R-CNNに対しての差分は以下の通り。

- 画像全体を始めに複数回畳み込みを行い特徴マップを作成
- 特徴マップから候補保領域に該当する部分を特定

https://arxiv.org/abs/1504.08083v1

## Faster R-CNN

領域提案ネットワーク(Region Proposal Network)により候補領域を予測

https://arxiv.org/abs/1506.01497


{{< youtube v5bFVbQvFRk >}}


---

## YOLO You Only Look Once

画像をグリッドに分割して、グリッドの領域毎に物体のクラスとBounding Boxの回帰を計算する手法です。

課題
- グリッドないで識別できるクラスは1つのため、大量の物体がある画像の認識が不可




## SSD Single Shot Detector
