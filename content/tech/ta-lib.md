---
title: "ta-libのインストール"
date: "2020-05-01"
draft: false
categories:
  - "Tech"
tags:
  - "Finance"
  - "Python"

featured_image: "/images/stock.webp"

---

# ta-lib

Ta-Libはテクニカル分析ライブラリです。
テクニカル教の信者にとってはインストール必須のツールになります。

https://ta-lib.org/

## MacOS/OSX ta-libのインストール

OSXにインストールする場合はbrewを使うと簡単です。

```
brew install ta-lib 
pip3 install TA-Lib
```

## Azure ta-libのインストール

メモリは1G以上で実行しないとエラーになりました。
ta-libをインストールする際のみ1G以上に変更しましょう。

```
wget http://prdownloads.sourceforge.net/ta-lib/ta-lib-0.4.0-src.tar.gz
tar -zxvf ta-lib-0.4.0-src.tar.gz
cd ta-lib
./configure --prefix=/usr
make
sudo make install
cd ../
rm -rf ta-lib-0.4.0-src.tar.gz
rm -rf ta-lib
pip3 install TA-Lib
```


## 参考動画

{{< youtube QGkf2-caXmc >}}
