---
title: "VIM メモ"
date: 2021-02-20T00:00:00+08:00
draft: true
categories:
  - "Tech"
tags:
  - "vim"
featured_image: "/images/programing.jpeg"

---

vim editorの備忘メモ

https://www.vim.org/


# vim特化の学習サイト vimate
基礎はこちらのサイトで学習できます。

https://vimate.jp/


# vim基本操作

## ファイル操作

| 操作        | コマンド |
| ----       | ------- |
| ファイルを開く| :e |
| 上書き保存 　| :w |
| 終了 　　　　| :q |
| 上書きして終了 | :q! |


## モードの切り替え

|操作| コマンド|
|----|----|
|インサート| i |
|行の先頭でインサート| I |
|行末でインサート | A|
|次の行からインサート| o |
|ノーマルモードへ戻る| Ctrl + [ or Esc|

Escキーの配置は物理キーボードの仕様に依存するため、
ノーマルモードへ戻る際はEscapeキーではなく
Ctrl+[
で戻る癖をつけると良いです。

## カーソル移動

| 操作        | コマンド |
| ----       | ------- |
| 下にスクロール|  Ctrl+f |
| 上のスクロール| Ctrl+b|
| 1行目に移動| gg|
| 最終行に移動| G |

## 行の連結
連結したい行にてJ (Shift+j)


# vim応用

## 指定範囲のカット・ペースト

1. 開始行にカーソル移動
2. ms
3. 範囲最終行にカーソル移動
4. d's
5. p

## 一括インデント

1. Shift + v
2. シフトしたい行を洗濯
3. Shift + >

## 選択した行以降全ての行にインデントを挿入

1. Shift + v
2. shift + g
3. >>

## 確認しながら置換pする

```
:%s/置換前/置換後/gc
```


## プラグイン


### Vundleプラグインの導入
https://github.com/VundleVim/

```Shell
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```

vimを起動して
```
:PluginInstall
```

## Python向けvim環境

GUI環境では、PycharmなどのIDEを使えばいいですが、CUI環境で手軽にコーディングしたい場合は、vimが便利です。
vimにJEDIを導入してPython開発を効率化します。

### JEDI-VIMの導入

```Shell
git clone --recursive https://github.com/davidhalter/jedi-vim.git ~/.vim/bundle/jedi-vim
```

```
Plugin 'davidhalter/jedi-vim'
```


### [Vim as IDE 第1回] NeoBundleを利用してvimプラグインを一元管理する

https://qiita.com/kazu0620/items/819679ef006d973c6c22
