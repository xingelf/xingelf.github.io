---
title: "Kali Linux Memo"
date: "2021-06-02"
draft: true
categories:
  - "tech"
tags:
  - "CTF"
  - "Kali Linux"
  - "CEH"

---

# Update

```
sudo apt update
sudo apt upgrade

```

# Install

## pkcrack

```
tar xvzf pkcrack
cd test
sudo make
cd ../src/
pkcrack
```

## fcrackzip zipパスワード解析

```
sudo apt install fcrackzip
```


## exiftool

sudo apt install exiftool



# Network

## 443通信しているアプリケーションと通信先を特定

```
sudo lsof -i:443
```


# Linux Fundamentals

## ファイル検索

findで検索する際は"permission denied(FD 2 STDERR)" をフィルタするため 2>/dev/nullを指定

find /etc -name passwd 2>/dev/null
