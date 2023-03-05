---
title: "Solidity文法　型"
date: "2022-09-03"
draft: false
categories:
  - "DAO"
tags:
  - "Solidity"
  - "Type"
thumbnail: "/images/blockchain.jpeg"
---


# データ型

Solidityは強く型付けが必要な言語です。

https://solidity-ja.readthedocs.io/ja/latest/types.html


## 整数

```solidity
int b = -10; // 符号あり、正負の整数
uint a = 5; // unsinged int 符号なし、正の整数
```

## ブール、ブーリアン

```solidity
bool bt = true; // 真
bool bf = false; // 偽
```

## 文字列

```solidity
string hw = "Hello World";
```

## バイト型 bytesN

```solidity
bytes32 eth = "ETH";
```


## アドレス型

Walletのアドレス(20バイト)を示す型

```solidity
address adr = 0x06012c8cf97BEaD5deAe237070F9587f8E7A266d
```
