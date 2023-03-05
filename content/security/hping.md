---
title: "hping/hping3使い方"
date: "2022-12-10"
draft: false
categories:
  - "Security"
tags:
  - "tool"
  - "network"

---

hping/hping3は、ネットワークホストに様々な種類のパケットを送信し、その応答を分析することができるコマンドラインユーティリティです。

ネットワークスキャン、ファイアウォールテスト、ネットワークテストなど、さまざまなタスクに使用することができます。


## hping3 コマンドサンプル 1

- eth0 インターフェース
- 10パケット
- 2.2.2.2で送信元を偽装
- TTLを100

```shell
hping3 -I eth0 -c 10 -a 2.2.2.2 -t 100 [targetIP]
```

## hpingコマンドサンプル 2

- TCP port 80
- SYN Packet

```shell
hping3 -S -p 80 [targetIP]
```


{{< youtube H5UsvAUoas8 >}}