---
title: "Tex/LaTexメモ"
date: "2021-07-22"
draft: false
categories:
  - "Tech"
tags:
  - "Hugo"
  - "Tex"
  - "Markdown"
---


# Markdown Tex形式で数式を書く

## partialsの設定
paritial templateの機能を使います。

https://gohugo.io/templates/partials/

\layouts配下にpartialsフォルダを作成します

\layouts\partials

配下に2つのファイルを配置します。

- mathjax.html
```html
<script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
<script type="text/x-mathjax-config">
 MathJax.Hub.Config({
 tex2jax: {
 inlineMath: [['$', '$'] ],
 displayMath: [ ['$$','$$'], ["\\[","\\]"] ]
 }
 });
</script>
```
- footer.html

```html
<footer>
  {{ partial "mathjax.html" . }}
</footer>
```

## 数式の例
tex表記を$で囲むだけです。


- 2次方程式解の公式

$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$

```tex
$ x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} $
```


- ベイズの定理

$ P(X=x| Y=y) = \frac{P(Y=y|X=x)P(X=x)}{P(Y=y)} $

```tex
$ P(X=x| Y=y) = \frac{P(Y=y|X=x)P(X=x)}{P(Y=y)} $
```


- ブラック・ショールズ方程式

$
rC = \frac{\partial C}{\partial t}
       + \frac{1}{2}\sigma^2S^2_t\frac{\partial^2 C}{\partial S_t^2}
       + rS_t\frac{\partial C}{\partial S_t}
$

```tex
$
rC = \frac{\partial C}{\partial t}
       + \frac{1}{2}\sigma^2S^2_t\frac{\partial^2 C}{\partial S_t^2}
       + rS_t\frac{\partial C}{\partial S_t}
$
```
