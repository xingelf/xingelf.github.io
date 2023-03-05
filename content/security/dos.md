---
title: "DoS/DDoS攻撃"
date: 2022-12-01
draft: false
categories:
  - "Cyber Security"
tags:
  - "DOS"
  - "CEH"
thumbnail: "/images/cyber-security.png"
---


# DDoS攻撃とは
https://en.wikipedia.org/wiki/Denial-of-service_attack


分散型サービス妨害（DDoS）攻撃とは、
インターネット上の大量のトラフィックでターゲットやその周辺のインフラへ高負荷を与えるることで、
ターゲットのサーバー、サービス、ネットワークの正常なトラフィックを妨害しようとする悪意のある試み。

DDoS攻撃は、攻撃トラフィックの発生源として、危険にさらされた複数のコンピューターシステムを利用することで効果を発揮する。

悪用されるマシンは、PC端末、IoTデバイスなどのインターネット上のリソースである。



## DDoSの種類

### L4 フラッド

SYN Flood, ACK Flood, UDP Floodなど。  
サーバリソース枯渇を目的としたDDoS攻撃

### L7 フラッド

HTTP GET/POST Flood、Slow HTTP DoS攻撃など

Webサーバの処理能力を超えたリクエストを送り、サービスを停止する。


### Amplification

DNS Amplification,NTP Amplificationなど

送信元IPをターゲットのIPに偽装し、世界中のDNS/NTPサーバに対して、
DNS/NTPのUDP通信を送ることで、その応答パケットをターゲットIPへ大量送信する。




## Slow HTTP DoS Attack

- Slow HTTP DoS Attack に対する注意喚起について
 https://www.npa.go.jp/cyberpolice/detect/pdf/20151216.pdf


- Slowloris攻撃（スローロリス）

帯域ではなく処理中セッションを増加させることでリソース不足を引き起こす攻撃。

https://www.cloudflare.com/ja-jp/learning/ddos/ddos-attack-tools/slowloris/

### RUDY R-U-Dead-Yet?

- Slow HTTP DoS Attackの一種
- POSTを利用するためSlow HTTP Post Attackと呼ばれる
- 小さいPOSTメソッドを間隔を空けて送信することでサーバ側のTCPセッションを占有
- POSTを受け付けるWebサイトでのみ利用可能


{{< youtube k1o9Ya8qxlU >}}

### LOIC HOIC ネットワーク負荷生成ツール

LOIC(Low Orbit ION cannon)とHOIC(High Orbit ION canon)はネットワーク負荷
生成ツールのためDDoS攻撃にも利用が可能なツール。

- オープンソース
- LOIC https://sourceforge.net/projects/loic/
- HOIC https://sourceforge.net/projects/hoic/


### Smurf攻撃

ブロードキャストアドレス宛にICMPパケットを送信することで、ネットワーク帯域を消費させる攻撃。
ネットワーク機器において、ブロードキャストアドレスに対してパケット転送しない設定することにより防御可能。


### Fraggle攻撃

Smurf攻撃の変種。ブロードキャストアドレス宛にUDPパケットを送信する攻撃。