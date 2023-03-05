---
title: "Azure IaaS備忘メモ"
date: "2021-06-20"
draft: true
categories:
  - "tech"
tags:
  - "Azure"
  - "Linux"
---

# Azure IaaS

Azure IaaSを利用してUbuntu Linuxを作成したときのメモです。
接続元はOSX/Macとなります。


## SSH環境の作成

https://docs.microsoft.com/ja-jp/azure/virtual-machines/linux/create-ssh-keys-detailed

```
ssh-keygen -t rsa -b 4096 -C "azureuser@vm01"
/.ssh/id_rsa.pub</pre>
```
作成されたキーファイルid_rsa.pubをAzure Portalに登録

## vim環境

Vundleプラグインを導入

https://github.com/VundleVim/Vundle.vim

```
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
 vim:VundleInstall
```
## python環境構築

pipをインストールする前にをaptのアップデートを実行
```
sudo apt-get update
```

### pip3のインストール

```
sudo apt install python3-pip
```

### pandasのインストール

```
pip3 install pasdas
```

### タイムゾーン設定

- 東京の場合
```
sudo ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime
```

- シンガポールの場合
```
sudo ln -sf /usr/share/zoneinfo/Asia/Singapore /etc/localtime
```

---

# OSX Azure CLIの導入

## Azure CLI導入方法

OSXへAzure CLIを導入します

https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-macos?view=azure-cli-latest">https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-macos?view=azure-cli-latest

## Homebrewのインストール
<a href="https://brew.sh">Homebrew</a>をインストールします。


```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)
```

## Azure CLIのインストール

```
brew update
brew install azure-cli
```

## Azureへのログイン

```
az login

```

ブラウザが起動するのでログインを行います。

## CLIマニュアル
あとは<a href="https://docs.microsoft.com/en-us/cli/azure/?view=azure-cli-latest">DOCS</a>を読むだけです。
