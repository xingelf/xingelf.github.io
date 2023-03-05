---
title: "リカレントニューラルネット - Recurrent Nueral Net RNN　"
date: "2021-08-16"
draft: false
categories:
  - "Tech"
tags:
  - "Neural Network"
  - "Deep Learning"
  - "E資格"
thumbnail: "/images/artificial-intelligence.png"
---


# RNNとは

時系列や文章・音声など系列データを扱うネットワークです。
前の時点のデータを入力とすることが特徴です。

{{< youtube yvqgQZIUAKg >}}

---

## RNNの数学的記述

入力: $x^t$

中間層の入力: $ u^t = w_{(in)}x^t + Wz^{t-1} + b $

中間層の出力: $ z^t = f(u^t) = f(w_{(in)}x^t + Wz^{t-1} + b) $

出力層の入力: $ v^t = w_{(out)}z^t + c $

出力層の出力: $ y^t = g(v^t) = g(w_{(out)}z^t + c) $

## Simple RNN


出力: $ y^t = h^t
= f^{\tanh}(x^t,h^{t-1})
= \tanh{(x^tW_{xh} + h^{t-1}W_{hh} +b)} $


## LSTM - Long Short Term Memory

RNNでは以下の課題がありました。

- 過去の情報を保持できない
- 勾配消失

LSTMではメモリ、ゲートと呼ばれる機能を導入し、この問題に対応。
ゲートは過去のメモリをどの程度利用するかを調整する。

- CEC Constant Error Carousel　メモリセル/記憶セル

- 入力ゲート
入力と1つ前の出力をどの程度反映するか調整

- 忘却ゲート
記憶セルの要素をどの程度残すかを調整。過去の情報が不要な場合は弱める機能をもつ→忘却。

- 出力ゲート
出力の値を調整


### LSTMの数学的記述


- 忘却ゲート(forget gate):

$ f^t =　f_f^{\sigma}(x^t,h^{t-1}) $

- 入力ゲート(input gate):

$ i^t =　f_f^{\sigma}(x^t,h^{t-1}) $

- 出力ゲート(output gate):

$ o^t =　f_o^{\sigma}(x^t,h^{t-1}) $

- 入力と隠れ状態の結合():

$ \tilde{c}^t =　f_{\tilde{c}}^{\tanh}(x^t,h^{t-1}) $

- 記憶セル(memory cell):

$ c^t =　f^t \otimes c^{t-1} + i^t \otimes  \tilde{c}^t $


- 出力(output):

$ y^t =　h^t = o^t \otimes c^t $



{{< youtube oxygME2UBFc >}}



## GRU Gated Recurrent Unit

メモリセルをなくして忘却ゲートと入力ゲートをあわせたモデル

以下2つのゲートで構成

- リセットゲート　過去の隠れ状態を調整するゲート

- 更新ゲート　過去の隠れ状態と仮の隠れ状態の割合を決めるゲート

### GRUの数学的記述


- 更新ゲート(update gate vector):hをどの程度更新するかを決める

$ z^t =　f_z^{\sigma}(x^t,h^{t-1}) $


- リセットゲート(reset gate vector):前までの情報をどれだけ弱めるか


$ r^t =　f_r^{\sigma}(x^t,h^{t-1}) $

- 仮の隠れ状態: GRUの隠れ状態を更新する

$ \tilde{h}^t =　f_h^{\tanh}(x^t, r^t \otimes h^{t-1}) $

- **時刻tの出力状態**:

$h^t =　(1-z^t) \otimes h^{t-1} + z^t \otimes \tilde{h}^t $

---

{{< youtube K8ktkhAEuLM >}}
