---
title: "画像認識 - Visual Recognition"
date: "2000-01-01"
draft: true
categories:
  - "tech"
tags:
  - "E資格"
---



---

# 画像認識・画像分類

## VGG

2014年に提案されたモデル。フィルタサイズ3x3の畳み込み層を複数重ねる。

## GoogLeNet

2014年に提案されたモデル。フィルタサイズの異なる畳み込み層を並列に配置する
**インセプションモジュール** を導入。
これにより複数のスケールの特徴を抽出する。Network in Networkを採用。

Global Average Poolingを採用。Global Average Poolingでは、
各チャネルの画素平均値を算出し、各チャネルの平均値を要素とするベクトルに変換。


{{< youtube p-SflGf3m2Y >}}


## ResNet - Residual Network

2015年に提案されたモデル。恒等写像を介して特徴マップ同士を足し合わせる。スキップ接続。

$ H(x) = F(x) + x$

畳み込み層にその層の入力を足し合わせる


https://arxiv.org/pdf/1512.03385.pdf

{{< youtube WslQrSO94qE >}}


## DenseNet

畳み込み層の後に層の前の入力のすべてを足し合わせる。


# 物体検出

## YOLO

## SSD
