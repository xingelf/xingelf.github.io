---
title: "IAM Identity and Access Management"
date: "2021-07-02"
draft: true
categories:
  - "tech"
tags:
  - "IAM"
  - "Security"
---

# IAMアクセス管理

アクセス管理におけるポイントを学習します


## アクセス制御MAC/DAC/RBACについて

アクセス制御は主にMAC/DAC/RBACの３種類を理解しておく必要があります。 それぞれの特徴について以下の動画で基本が理解できます。

### DAC 任意アクセス制御

情報のオーナーが　他者に対して　自由に権限の付与が可能


{{< youtube UNRnSaXajC4 >}}


### MAC 強制的アクセス制御

管理者が　強制的にアクセス制御を設定する方法。以下はカルテに対するアクセス権限の例です

{{< youtube mNN-fEboRAA >}}


### RBAC 役割ベースのアクセス制御

Helpdesk担当やBackup運用者など、それぞれの役割に基づいて必要なコマンド実行やデータの参照を許可するモデルです。

{{< youtube C4NP8Eon3cA >}}
