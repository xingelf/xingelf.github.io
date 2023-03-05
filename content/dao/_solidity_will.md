---
title: "Solidity 遺産相続コントラクト"
date: "2022-09-11"
draft: true
categories:
  - "DAO"
tags:
  - "Solidity"
  - "Smart Contoract"
---


遺産相続を行うシンプルなスマートコントラクトの実装例です。



全体は以下の通りです。

```solidity
pragma solidity ^0.8.5;

contract Will {
    address owner;
    uint fortune;
    bool deceased; // 存命か否かをboolで定義　存命：false、逝去：true

    constructor() payable public {
        owner = msg.sender; // msg.sendをオーナーに設定
        fortune = msg.value; //msg.valueとして遺産額を指定  
    }

    // ownerは必ずmsg.senderであることをmodifierで定義
    modifier onlyOwner {
        require(msg.sender == owner);
        _;
    }

    // 被相続人が亡くなっていることをmodifierで定義
    modifier mustBeDeceased {
        require(deceased == true);
        _;
    }    

    // 相続人のウォレットを配列で定義
    address payable[] familyWallets;

    // 遺産額をウォレットアドレスからのマッピングで定義
    mapping(address => uint) inheritance;

    // 相続遺産支払いをforループで相続人のウォレットへ転送
    function payout() private mustBeDeceased {
        for(uint i=0; i<familyWallets.length; i++) {
            familyWallets[i].transfer(inheritance[familyWallets[i]]);
            // 相続人にアドレスへ遺産を転送
        }
    }

    // 亡くなったら支払い関数を呼び出し
    function hasDeceased() public onlyOwner {
        deceased = true;
        payout();
    }
}
```
