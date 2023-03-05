---
title: "Softmax関数"
date: "2021-07-31"
draft: false
categories:
  - "ML/AI"
tags:
  - "Machine Learning"
  - "Math"
thumbnail: "/images/math.webp"
---

# Softmax関数

Softmax関数は以下の式で定義される。

$ y_i = {softmax}(x_i) = \frac{e^{x_i}}{\sum_{k=1}e^{x_i}}$

$ i = 0,1,2,\dots n$

$y_i$をすべて足し算すると和が1になるため、それぞれの を確立と考えることができる。
分類問題における多クラス分類に利用される。

Sofmax関数は以下の性質をもつ

$ Softmax(x) = Softmax(x+c) $


# 参考動画



{{< youtube 5CwLT-IQB9E >}}


{{< youtube i5uPUiBSFbQ >}}
