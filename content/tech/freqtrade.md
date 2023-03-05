---
title: "Freqtradeのインストール"
date: "2020-04-01"
draft: false
categories:
  - "tech"
tags:
  - "Finance"
  - "Python"
featured_image: "/images/road.jpeg"
thumbnail: "/images/road.jpeg"

---


# freqtradeのインストール

https://github.com/freqtrade/freqtrade.git

## python venvのインストール

```
sudo apt-get install python3-venv

```
## git clone にてパッケージを取得

```
git clone https://github.com/freqtrade/freqtrade.git
cd freqtrade
git checkout develop
./setup.sh --install

```

ta-libのインストールで時間が掛かりますが、ひたすら待ちます。

1CPU/1GB MEMのAzure環境の場合、20分くらいで完了しました。
