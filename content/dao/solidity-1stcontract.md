---
title: "Solidity 最も簡単なコントラクトの作成"
date: "2022-09-19"
draft: false
categories:
  - "DAO"
tags:
  - "Solidity"
  - "DApps"
thumbnail: "/images/blockchain.jpeg"

---


Solidity学習リソースでよく紹介されている最も簡単なコントラクトを
REMIXを利用して作成します。

コントラクトの動作としては数字をセット/setしてそれを表示/getするだけの単純なものです。

これを実行するだけでもGAS代が消費されることを確認します。

もちろん、ローカルEVM(テスト環境)で実行します。

# REMIXで最も簡単なコントラクトを作成

## 1. REMIXにアクセス

https://remix.ethereum.org/

Environmentには[Remix VM (London)]と設定されていることを確認します。


## 2. ソースファイルを作成

Firstcontract.solを作成

{{< figure src="/images/sol01.png" class="center" >}}

## 3. コントラクトをコード

実態の中身としては既に存在している1_Storage.solとほぼ同じです。。

値をsetするstore関数と値をgetするretrive関数を作成します。

{{< figure src="/images/sol02.png" class="center" >}}



```solidity
// SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.7.0 <0.9.0;

contract simpleStorage {

    uint256 number;

    function store(uint256 num) public {
        number = num;
    }

    function retrieve() public view returns (uint256){
        return number;
    }
}
```

## 4. コンパイル

autoコンパイルされていますが、一応コンパイル[Compile Firstcontract.sol]をクリックしましょう。

{{< figure src="/images/sol03.png" class="center" >}}


## 5. 実行

Deployをクリックします。storeに任意の数字を入力(set)し、retriveにてその数値を得る(get)ことを確認します。

{{< figure src="/images/sol04.png" class="center" >}}
