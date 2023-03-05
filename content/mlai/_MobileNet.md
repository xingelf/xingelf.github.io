---
title: "MobileNet"
date: "2021-04-17"
draft: true
categories:
  - "tech"
tags:
  - "E資格"
---

# MobileNetとは

スマホなどモバイル端末でもCNNが出来るように計算量を削減する仕組み。計算量削減は、計算パラメタを大幅削減することで実現する。

## 通常のCNNのパラメタ数

フィルタの縦横をf、入力チャネルをN、出力チャネルをMとした場合、
そのパラメタ数は

$ f^2NM $

## 深さ畳み込み　Depthwise Convolution

チャネル毎に独立のフィルタを用いて畳み込みを行う。
そのパラメタ数は

$ f^2N $


## Pointwise Covolution

フィルタサイズを1、つまりポイント・点として畳み込みを行う。
そのパラメタ数は

$ NM $



{{< youtube 5JAZiue-fzY >}}



## 原著論文

https://arxiv.org/pdf/1704.04861.pdf
