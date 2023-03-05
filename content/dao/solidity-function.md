---
title: "Solidity文法　関数"
date: "2022-10-15"
draft: false
categories:
  - "DAO"
tags:
  - "Solidity"
  - "Function"
thumbnail: "/images/blockchain.jpeg"
---


# Solidity Function  関数

基本的な関数の例は以下の通りです。

## 足し算
```solidity
function add(uint a, uint b) public pure returns (uint){
  return a + b;
}
```
## メッセージ
```solidity
function add(uint a, uint b) public pure returns (uint){
  return a + b;
}
```

# Solidity Visibility Modifiers 関数可視性修飾子　

- private : 該当関数のコントラクトだけが利用可能
- internal : 該当のコントラクトと継承するコントラクトが利用可能
- external : トランザクション、または、外部コントラクトによってのみ利用される関数
- public : 内部・外部どこからも呼び出しが可能（制約なし）

# ステートパーミッション修飾子　pure view

関数にpure/viewのどちらかを付けない場合はガス代が発生すると意識します。

- pure : 変数の参照のみ。ガス代不要
- view : 演算などを行い結果を返す。ブロックチェーンに変更を行わず、ガス代不要
