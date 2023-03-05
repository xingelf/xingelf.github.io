---
title: ""
date: "2000-01-01"
draft: true
categories:
tags:
---

最適化手法


## RMSProp RootMeanSquere

$ h_t = \alpha h_{t-1} + (1-\alpha)(\nabla E)^2$

AdaGradを改良したアルゴリズム。
過去の勾配の平均ではなく、指数移動平均を採用
