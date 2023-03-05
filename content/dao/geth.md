---
title: "geth　使い方"
date: "2022-09-18"
draft: true
categories:
  - "DAO"
tags:
  - "Ethereum"
  - "Geth"
---


# Gethとは

Ethereumクライアントです。

https://geth.ethereum.org/


# Gethのインストール

https://geth.ethereum.org/docs/install-and-build/installing-geth



## Ubuntuへのインストール

```
$ sudo add-apt-repository -y ppa:ethereum/ethereum
$ sudo apt-get update
$ sudo apt-get install ethereum
$ geth version
Geth
Version: 1.10.25-stable
Git Commit: 69568c554880b3567bace64f8848ff1be27d084d
Architecture: amd64
Go Version: go1.18.5
Operating System: linux

```

# Gethの文法

```
geth [global options] command [command options] [arguments...]
```
