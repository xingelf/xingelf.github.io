---
title: "Pharming and Phising"
date: "2022-05-26"
draft: false
categories:
  - "Cyber Security"
tags:
  - "CEH"
  - "DNS"
  - "email"
thumbnail: "/images/cyber-security.png"
---

## Pharming　ファーミング

https://csrc.nist.gov/glossary/term/pharming

DNS（Domain Name System）などのインフラサービスを攻撃者が改ざんし、契約者を偽造した検証機/RPに誤誘導し、契約者に機密情報の漏洩や有害ソフトウェアのダウンロード、詐欺行為に加担させる攻撃。

ファーミングには、いくつかの異なる形態がある。

1. 電子メールで送信されたコードが、PC上のローカルホストファイルを変更するものです。ホスト・ファイルは、Uniform Resource Locator (URL)を、コンピューターがウェブサイトにアクセスするために使用するIPアドレスに変換します。ホスト・ファイルが侵害されたコンピューターは、ユーザーが正しいウェブ・アドレスを入力したり、影響を受けるブックマーク項目をクリックしたりしても、偽のサイトにアクセスしてしまう。

2. DNSポイズニング。サーバーのDNSテーブルが変更され、正規のウェブサイトにアクセスしているつもりのユーザーが、不正なウェブサイトに誘導される。この手法では、個々のPCのホスト・ファイルを改ざんする必要はありません。代わりに、数百万人のインターネットユーザーのURLリクエストを処理するDNSサーバーに問題が発生する。そして、被害者は、不一致を目に見える形で示すことなく、偽サイトにアクセスしてしまう。


## Phishing　フッシング

https://en.wikipedia.org/wiki/Phishing

An attacker sends e-mail with a URL which has malicious link similar to the popular actual websites.

メールアドレスに不正リンクなどをつけ、個別の利用者を不正アクセスへ誘導する手法



{{< youtube PAtUSoIRJhA >}}
