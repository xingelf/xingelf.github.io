---
title: "Solidity文法　mapping マッピング"
date: "2022-09-30"
draft: false
categories:
  - "DAO"
tags:
  - "Solidity"
  - "Mapping"
thumbnail: "/images/blockchain.jpeg"

---


mappingはkey, valueの対応を定義するもので、ハッシュテーブル、辞書型のようなものです。
典型的な利用法があり、ブロックチェーン上のウォレットアドレスにある
残高をマップするケースでほぼ必ず利用されます。

```solidity
mapping(_KeyType => _ValueType) //定義

mapping(address => uint) public valances; //具体例
```

## mappingで出来ること

- キーの型はなんでもOK
- アドレスから残高の参照

## mappingでは出来ないこと

- ループ処理による取り出し
- valueからkeyの参照
