---
title: "nmap cheat nmapチート"
date: "2022-05-01"
draft: false
categories:
  - "Tech"
tags:
  - "CEH"
  - "Network"
  - "nmap"

---


# nmapとは

ポートスキャンツールです。ペネトレーション作業の基本ツールです。



- -T5 insane 最速でスキャンを実行

  https://nmap.org/man/ja/man-performance.html

- -T4 Aggresive スキャン処理の遅延は10msec以内

- -F 簡易スキャン　nmap-servicesに記載されたポートのみをスキャン

  https://nmap.org/book/nmap-services.html

- -r ポートをランダムにしない


## Christmass Scan

- -sX Christmass Scan

  - FIN/PHS/URGのフラグを設定
  - Control Flag がOn/Off/On/Off/On/OffのためXmasと呼ばれる
  - **RSTを返さない場合、openと判定する**
  - windowsでは一律RSTを返すため、Windows判定に利用される

 https://nmap.org/man/ja/man-port-scanning-techniques.html


 {{< youtube ws0MeqfuA58 >}}


## Normal Scans

- sT connect Scan

  - Most visible and easily detected by IDS　IDSによって容易に検知される

- -sS Syn Scan or Stealth Scan

  - SYNスキャン、ハーフスキャン
  - 接続を完了しないため、ログに残らないケースが多い

| Option | Flags | Windows Open | Windows Closed | Linux Open | Linux Closed|
| --- | --- | --- | --- | --- | ---|
| -sS | Syn | Syn-Ack | Rst-Ack | Syn-Ack | Rst-Ack|
| -sT | Syn | Syn-Ack | Rst-Ack | Syn-Ack | Rst-Ack|


## -S Spoof source address ソースIP偽装

ソースIPを偽装してスキャンを実行する。


```
namp -S 192.168.10.1
```

## -D Decoy Scan デコイスキャン・おとりスキャン
https://linux.die.net/man/1/nmap

おとりスキャンを実行する。引数に複数のおとり用IPアドレスを指定。

```
namp -D decoy1[,decoy2]...
```

リモートホストには、おとりとして指定したホストもターゲットネットワークをスキャンしているように見せる。
そのため、IDSは固有のIPアドレスから5～10回のポートスキャンを報告するが、どのIPが実際にスキャンしていて、
どれが無実のおとりであるかの判定を困難にする。

## -O OS Detection

- O OS判定

## Input and Output

- -oX XML形式でのファイル出力

## Maimon scan マイモンスキャン

マイモンスキャンは、発見者であるウリエル・マイモンにちなんで名づけられた。
ウリエル・マイモンは、Phrack Magazineの49号(1996年11月)でこの技法を説明した。

このテクニックは、プローブがFIN/ACKであることを除けば、NULL、FIN、Xmasスキャンと全く同じである。

RFC793（TCP）によれば、このようなプローブに対しては、ポートが開いていようと閉じていようと、RSTパケットを生成することになっている。
しかし、ウリエルは、多くのBSD由来のシステムが、ポートが開いている場合は単にパケットをドロップしていることに気づいた。
これによりBSD由来のシステムの特定が可能となる。

https://nmap.org/book/scan-methods-maimon-scan.html


## Ping Sweep

アドレス指定範囲に対してpingを実行 

- -sn ping指定
- -PE Echo Request

```shell
nmap -sn -PE x.x.x.x/yy
```


---

## nmap学習動画

{{< youtube 4t4kBkMsDbQ >}}
