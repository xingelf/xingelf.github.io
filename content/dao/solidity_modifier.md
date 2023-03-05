---
title: "Solidity文法 modifier　使い方"
date: "2022-09-19"
draft: false
categories:
  - "DAO"
tags:
  - "Solidity"
thumbnail: "/images/blockchain.jpeg"

---

初見では少し理解できないmodifierについて、簡単に説明します。
modifierは関数修飾子でfunction文の後半に記載して、関数を実行する前に
定型処理（前提条件の判定など）を行うことができます。

よく定義されるのはonlyOwnerともので、Ownerアドレス保有者限定で実行できるような
制限を行います。

## modifier の使い方

以下は入金・預金を行うdeposit関数を作成しますが、関数を呼び出しした人に限定する処理です。

```solidity

modifier onlyOwner {
  require(msg.sender == owner, "Error");
  _; // functionの処理を続行するための処理
}


function deposit() public payable onlyOwner{
  balance[msg.sender] += msg.value;
}
```

以下のようにonlyOwnerを使わない方法もありますが、modifierを使うことで、
関数の制約を付けて可読性が上がります。

```solidity

function deposit() public payable　{
  require(msg.sender == owner, "Error");
  balance[msg.sender] += msg.value;
}
```
