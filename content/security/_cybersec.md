---
title: "サイバーセキュリティ関連 - Cyber Security"
date: "2021-07-15"
draft: true
categories:
  - "Security"
tags:
  - "hacking"
  - "CTF"
  - "cyber"
  - "security"
---

サイバーセキュリティ関連気になったトピックの雑記メモです

---
## フレームワーク

### NIST Cyber Security Framework

#### NIST CSFポイント

従来のISO-27001が予防や防御を中心に対策を要求していましたが、NISTのCSFでは、以下の5つのフェーズで対策を要求しています。

|  |Phase　 |フェーズ　 |
| ---- | ---- | ---- |
|ID |IDENTIFY    |特定 |
|PT |PROTECTION  |防御 |
|DE |DETECTION   |検知 |
|RE |RESPONSE    |対応 |
|RC |RECOVER     |復旧 |


{{< youtube J9ToNuwmyF0 >}}


---

## 攻撃手法

### メール系攻撃

### メール会話誘導型攻撃

EMOTETなどで使われている手法です。通常のメール会話に類似した文面を使うことで、開封を誘導し、ウイルス感染を図ります。

https://www.hornetsecurity.com/en/security-information/email-conversation-thread-hijacking/

### PDoS Permanent Denial of Servive - Phlashing Attack

フラッシング攻撃。主にハードウェアを対象とした物理的に破壊を行う攻撃です。

https://www.datafoundry.com/blog/what-is-a-permanent-dos-pdos-attack


## 防御手法

### 多層防御 - Defence in depth

複数のセキュリティ防御策を講じることで、サイバー攻撃におけるレジリエンスを高めるアイデアです。
大規模な侵害に至る前、侵入フェーズの前段で検知することで被害拡大を抑止します。

{{< youtube OTGMi0ksjXY >}}



### ゼロトラスト

安全と定義したネットワークにおいても、何らかのリソースにアクセスする際は、
無条件で許可をせず、その都度認証・認可を行う考え方。
境界防御が既に有効ではなく、Assume Breach侵入を前提とした防御を考える際に
基本となるアイデアがゼロトラストです。

{{< youtube 1D5mg9an19o >}}


---

## 脆弱性管理

### CVSS/CVE

#### CVEとは

CVEとは脆弱性データベースです。

CVE概説　
https://www.ipa.go.jp/security/vuln/CVE.html


{{< youtube qfpnJyTl1To >}}



#### 脆弱性トレンドを知る

https://cvestalker.com/weekly.php


## セキュリティレベル評価・リスク評価

### ISO27001 ISMS

ルールベースです。
セキュリティ監査の定番ですが、全体的に形骸化しており、近年のサイバーセキュリティに対応ができているとは言えません。

### Risk IQ

ベンダーソリューションです。インターネットから実機ベースの評価を行う手法です。
https://www.macnica.net/riskiq/

### FFIEC-CAT

金融機関限定。
サイバー・セキュリティ管理の成熟度評価ガイドラインです。
https://www.ffiec.gov/pdf/cybersecurity/FFIEC_CAT_May_2017.pdf


### サイバーセキュリティ日々の出来事　Cyber Daily Monitoring

- Bleeping Computer
https://www.bleepingcomputer.com/

- Morning Start Security
https://morningstarsecurity.com/news


---

## セキュリティスキル向上

### Capture the Flag CTF

https://overthewire.org/wargames/


### ネットワークスキル

#### WiFiルータのデフォルトパスワードを調べる

https://www.routerpasswords.com/

### オープンソースインテリジェンス OSINT

#### IPアドレス

IPアドレスと場所を調べる際に利用します。
https://whatismyipaddress.com/

#### Shodan

インターネット上の情報をサービス、脆弱性の観点などで検索できます。

https://www.shodan.io/

#### Whois Lookup

ドメインに関する情報を簡単に調べることができます

https://whois.domaintools.com/


#### 情報探索 Footprinting

Footprintingと言います。
https://www.greycampus.com/opencampus/ethical-hacking/what-is-footprinting

---

## セキュリティモデル全般

日本語資料をとても少ないですが、IPAのこちらの資料が基礎から詳細まで含まれており内容が充実しています。


#### Bell-La Padula and Biba

Bell-La Padulaの特徴

- 機密性に特化したアクセス制御モデル
- マルチレベルセキュリティモデル
- 数学的モデル
- No Read Up, No Write Down


Bibaの特徴

- 完全性に特化したアクセス制御モデル
- 全性の低いデータが完全性の高いデータを破壊しないように制御
- No Write Up, No Read Down

### Clark-Wilsonの特徴

- 商用システム向け完全性ポリシーを定義
- 責務の分離 Separation of Duties(SOD)

---

## サイバー事案

### 2020年12月 Solarwinds/AD/ M365

こちらにMITRE ATT&CKベースでの攻撃のTTPsの解説があります。
https://us-cert.cisa.gov/sites/default/files/publications/SolarWinds_and_AD-M365_Compromise-Detecting_APT_Activity_from_Known_TTPs.pdf
