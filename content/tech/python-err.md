---
title: "Errors in Python"
date: "2023-01-03"
draft: false
categories:
  - "Python"
tags:
  - "Python"
---


## Invalid comparison between dtype=datetime64[ns, America/New_York] and datetime64

#### Error

Yahoo Financeにおいて、時刻の比較を行った際に発生したエラー。


#### 対処 

AmericaのTZが付与されているのでUTCローカライズします。

```Python
    start = np.datetime64(datetime.date.today() - datetime.timedelta(days=freq))
    df = df[ start < df.index ]
```

```Python
    start = np.datetime64(datetime.date.today() - datetime.timedelta(days=freq))
    df.index = df.index.tz_localize(None) 
    df = df[ start < df.index ]
```


## Could not import the lzma module

#### Error

UserWarning: Could not import the lzma module. Your installed Python is incomplete

pandas 1.0系以降でpandasをimportすると以下のエラーが発生する

Attempting to use lzma compression will result in a RuntimeError.

 warnings.warn(msg)

#### 対処

xzをbrewでインストール

```shell
brew install xz
pyenv uninstall 3.7.3
pyenv install 3.7.3
pyenv global 3.7.3
pip install pandas
```
