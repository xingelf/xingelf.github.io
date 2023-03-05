---
title: "dotfiles github管理"
date: "2021-07-01"
draft: true
categories:
  - "Tech"
tags:
  - "Github"
featured_image: "/images/english.webp"
thumbnail: "/images/english.webp"

---

# dotfiles on Github

OSX/LinuxなどUNIX環境において.vimrc .zshrc .bashrcなどをdotfilesと呼びます。これらをGithubにて管理します。

最近はIaaSサービスなどの充実により、VMを簡単に作成することが可能になりました。新しくVMを作成した際にも従来と同じViやシェル環境をgit cloneコマンド１発で実現することが可能になります。

## GitHubにリポジトリを作成

New Repositoryからdotfilesという名称で作成します。

## ローカル環境での作業

### 設定ファイルをdotfilesへ移動

```
mkdir dotfiles
mv .vimrc dotfiles
mv .zshrc dotfiles
mv .gitconfig dotfiles
```


### リンクの設定

ホームディレクトリのdotfilesがない状態ですので、dotfiles配下のファイルへシンボリックリンクを設定します。

```
ln -sf ~/dotfiles/.vimrc ~/.vimrc
ln -sf ~/dotfiles/.zshrc ~/.zshrc
ln -sf ~/dotfiles/.gitconfig ~/.gitconfig
```

この操作は新しいVMでも必要になるのでdotfiles配下にシェルスクリプトとして格納しておきます。


```
#!/bin/sh
##setup.sh
ln -sf ~/dotfiles/.vimrc ~/.vimrc
ln -sf ~/dotfiles/.zshrc ~/.zshrc
ln -sf ~/dotfiles/.gitconfig ~/.gitconfig
```

上記の場合、dotfileを追加する度に、個別の修正が必要になりますので、今後のdotfile追加対応として一般化しておきます。

```
#!/bin/sh
##setup.sh
DOT_DIRECTORY=~/dotfiles
for f in .??*
  do [ "$f" = ".git" ] ;
   continue
  ln -fnsv ${DOT_DIRECTORY}/$f ${HOME}/$f
done
```

### GitHubへPush

```

git init
git add .
git commit -m "Initial Creation"
git remote add origin git://github.com/git-username/dotfiles.git
git push origin master
```

これで先程作成したリポジトリにdotfilesが格納されました。


## 新しいVM構築時の設定同期

以下のコマンドで設定が同期されます
```
git clone https://github.com/your_name/dotfiles.git
sh setup.sh
```

## GitHub の使い方

GitHubの使い方についてはこちらがお勧めです。
