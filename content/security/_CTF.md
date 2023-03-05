---
title: "Capture the Flag"
date: "2021-06-02"
draft: true
categories:
  - "tech"
tags:
  - "CTF"
  - "python"
---
---
title: "Capture the Flag"
date: "2021-06-02"
draft: true
categories:
  - "tech"
tags:
  - "CTF"
  - "python"
---


# CTF基礎

## 暗号解読

### 換字式暗号
文字の変換テーブルベースの暗号です。



## zipパスワード解読

### pkcrack
暗号化されたzipファイルのうち平文が分かるものからzipファイルの解読を行います。
パスワード自体が分かるわけではありません。
指定するパラメータが分かりにくいので注意です。
-C 暗号化されたzipファイルを指定
-P 平文が分かるものをzip化したものを指定
-c zipの中の平文が分かるファイルを指定
-p 平文が分かるファイル自体を指定
-d アウトプットファイルを指定（パスワード無しzip）

zipinfoで得た平文が分かるファイル名と手元にある平文のファイル名を同じ名前にしておくと混乱が無いです。

```
zipinfo password.zip

zip plain.jpg

pkcrack -C password.zip -P plain.zip -p plain.jpg -c plain.jpg -d ./cracked.zip
```


# CTF基礎

## 暗号解読

### 換字式暗号
文字の変換テーブルベースの暗号です。

{{< gist eigohack 433504139ea3dfee05dea630d782a3fc >}}



# zipパスワード解読

# pkcrack

暗号化されたzipファイルのうち平文が分かるものからzipファイルの解読を行います。
パスワード自体が分かるわけではありません。
指定するパラメータが分かりにくいので注意です。
-C 暗号化されたzipファイルを指定
-P 平文が分かるものをzip化したものを指定
-c zipの中の平文が分かるファイルを指定
-p 平文が分かるファイル自体を指定
-d アウトプットファイルを指定（パスワード無しzip）

zipinfoで得た平文が分かるファイル名と手元にある平文のファイル名を同じ名前にしておくと混乱が無いです。


## Instal Pkcrack on kali

tar xzvf
cd test
sudo make
cd ../src/pkcrack

```
zipinfo password.zip

zip plain.jpg

pkcrack -C password.zip -P plain.zip -p plain.jpg -c plain.jpg -d ./cracked.zip
```
