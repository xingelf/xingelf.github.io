---
title: ""
date: "2022-09-30"
draft: true
categories:
tags:
---






## im2colを理解する


## conv2dを理解する

https://qiita.com/kenichiro-yamato/items/60affeb7ca9f67c87a17

ざっくり言うと、下記のとおり。

元画像とカーネル（フィルタ）を比較して計算し、その計算（行列演算）結果を出力して並べていく処理のことを「畳み込み」という。
畳み込んだ出力結果を「特徴マップ」と呼ぶことがある。
畳み込みによって出力されたデータは、元画像のデータよりも小さくなる。
