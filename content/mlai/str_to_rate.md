---
title: Pythonミニ関数 String/Object型の列にパーセントがある場合、数字に変換
date: 2022-10-29
draft: false
categories:
  - "ML/AI"
tags:
  - "Python"
  - "Kaggle"
thumbnail: "/images/code.jpeg"
---

割合の情報がString/Object型の列にパーセントとして与えられた、数字に変換

``` Python
def str_to_rate(s):
    if pd.isnull(s)==False:
        return float(s.replace('%',''))
    else:
        return s
```

使い方

``` Python
col = "ReplyRate"
df[col] = df[col].apply(str_to_rate)
```
