---
title: Pythonミニ関数 String/Object型の列にブール文字がある場合、ブール型に変換
date: 2022-10-01
draft: false
categories:
  - "ML/AI"
tags:
  - "Python"
  - "Kaggle"
thumbnail: "/images/code.jpeg"
---

真偽の情報がString/Object型の列にtやfとして与えられた場合、ブール型に変換

``` Python
def str_to_bool(s):
    if s=='t':
        return True
    else:
        return False
```

使い方

``` Python
col = "Availabiliy"
df[col] = df[col].apply(str_to_bool)
```
