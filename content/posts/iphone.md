---
title: "iPhone メモ "
date: "2022-10-08"
draft: false
categories:
  - "Tech"
tags:
  - "iPhone"
thumbnail: "/images/iphone.webp"
#toc: true

---


# ショートカット

## 位置情報のOFF/ONをホームボタンに配置

URLを開くのショートカットを作成してURLに以下を指定

prefs:root=Privacy&path=LOCATION

ホームボタンに配置すれば、OFF/ONが簡単になります。


# iPhoneでのKindle自動読み上げ

## AssistiveTouch/アシスティブタッチの有効化

 設定→アクセシビリティ→タッチ→AssistiveTouch→ON

## 画面の読み上げ

 Kindleアプリを開きAssistiveTouch◎から　画面の読み上げを選択

### iPhone読み上げ課題

 - 画像ページになると止まる - 日本語書籍は以外に挿し込み画像が多い。英語書籍の日本語訳は挿し込み画像が少なくスムーズ。
 - 流暢さ - 英語書籍は問題ないが、日本語書籍は若干読み上げに難あり
 - 動作 - 読み上げ開始されない場合があり動作が少し不安定

---


# 強制リセット

1. 音量をあげるボタン押下
2. 音量をあげるボタン押下
3. サイドボタン長押し
4. Appleロゴが表示されたらボタンを離す

https://support.apple.com/ja-jp/guide/iphone/iph8903c3ee6/ios


---

# 文字入力

## スペースキー長押しによるカーソル移動

スペースキー長押しにより、カーソル移動が可能となります


---

# iPhone機種変更

クイックスタートが最も簡単です。

## クイックスタート

### 事前準備

- Suicaを利用している場合、iCloudへWalletの同期を設定して、アプリを削除 -　新機種では新規インストール、登録アカウントで復旧

https://www.jreast.co.jp/appsuica/procedure/chg_model.html


- WiFiでMACアドレス制限している場合は一旦解除する - 後でprivateアドレスで許可リストに登録
- Apple Walletを利用している場合はカードを手元に準備　- 移行に3桁が必要なため
- VPNソフトが自動起動になっている場合はOFF - 移行後にVPNソフトが起動せず、その他アプリのインストールが始まらないため

### 移行作業

1. 新機種の電源ON
2. 旧機種と近づける
3. 新機種の画面をキャプチャ
4. WiFi接続
5. Apple Walletの移行（カード3桁の入力）
6. 旧機種のデータ転送開始　
　　使用データに依存すると思いますが、10〜15分程度でした。
7. 移行完了すると自動で再起動されます。

### 自動移行されるもの

以下のガジェットは自動的にペアリングされます

- Apple Watch
- Air Pods


### 移行後作業

1. WiFiをプライベードアドレスで接続し、MACアドレス制限を戻す
2. 不要な標準アプリのアンインストール
   - Numbers
   - Keynote
   - Pages
   - Clips
   - iMovie
   - GarageBand
　 - Apple Store

3. SIMの入れ替え

4. Microsoft Authenticatorの移行

   - リカバリ開始 Begin Recovery
   - Microsoftアカウントでログイン
   - 旧機種にログイン通知が着信するため許可　- 2桁の番号を選択など
   - 2FAを設定したアカウントについて旧機種と新機種で同じ番号が表示されていることを確認

5. Google Authenticatorの移行

   - 旧機種でGoogle Authenticatorを起動
   - 右上の・・・をタップしアカウントエクスポート/Export Accountsを選択
   - 旧機種側にQRコードが表示されるので、そのコードを新機種からスキャン
   - 旧機種側のアカウント削除、または、維持を選択。
   新旧の機種で同じ番号が表示されていれば旧機種側は削除して問題ありません。

6. Suica復元

   Walletアプリから復元します。Suica IDは変更になるようです。

   機種変更後、Expressで新幹線を利用した際、自動改札でエラーになりました。
   Expressアプリを利用されている方はアプリ側で連携するSuica IDを変更しておく必要があります。

7. Kindle/Audible

   コンテンツは再度ダウンロードが必要です。
   正しい動作か不明ですが、AppleWatchとのSync内容も解除・無効にされてしまいます。
　　少し面倒ですが、再度Syncをかけます。

---


# プライバシー保護

## DNS保護

DNS保護アプリをインストールしてプライバシー強化
<a href="https://itunes.apple.com/jp/app/1-1-1-1-faster-internet/id1423538627?mt=8">https://itunes.apple.com/jp/app/1-1-1-1-faster-internet/id1423538627?mt=8</a>


## VPNアプリ

VPNアプリをインストールして通信を全て暗号化するとともにアクセス元の匿名化を行います

<a href="https://www.expressvpn.com/jp/vpn-software/vpn-ios">https://www.expressvpn.com/jp/vpn-software/vpn-ios</a>


## Safari編

- 検索エンジンをDuckDuckGoに設定
- 定期的に履歴のクリア、ウェブサイトデータのクリアを実行
- ポップアップブロックの有効化
