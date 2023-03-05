---
title: Hugo備忘メモ
date: 2021-08-20
draft: true
sidebar: false
categories:
  - "Tech"
tags:
  - "Hugo"
  - "MarkDown"
---


# Install Hugo

homebrewでインストールするのが定番ですが、セキュリティなどを考慮して
tarボールでインストールします。

https://gohugo.io/getting-started/installing/

1. ファイルの展開

$HOME配下にbinを作成し、そこに配置します。

```
make dir ~/bin
tar -xvzf ~/Downloads/hugo_X.Y_osx-64bit.tgz
./hugo version
mv hugo ~/bin
```

2. パスの設定

export PATH="$HOME/bin:$PATH"




# GitHub x Hugo

GitHubでHugoを使う方法です

## 新たにサイトを作成

以下のコマンドによりドメイン名のディレクトリが作成されます。

```
hugo new site new-site.com

Congratulations! Your new Hugo site is created in xxxx

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.

```

### gitを初期化

```
git init
Initialized empty Git repository in xxx/.git/
```

```
echo "# earth" >> README.md

git add README.md
git commit -m "first commit"
git remote add origin git@github.com:account_name/git_rep.git
```


- サブアカウントの場合
```

git remote set-url origin git@github.com.sub:account_name/git_rep.git

git config remote.origin.url
git@github.com:aitil/earth.git
```

config.tomlファイルにpublishDir = "docs"の1行を追加する


テーマの導入
```
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

ローカルで確認
```
hugo server
```



### 記事の作成

```
hugo new posts/test.md
```
### github側にてpublicレポジトリ作成




## ドラフトを確認する

draft Trueにしたものをローカルで確認する方法です。

```
$ hugo server --watch --buildDrafts
```

## Wordpress to Hugo


## テーマの変更

config.tomlでテーマを変更します。次に、docsを削除してから、サイト再作成を行います。
独自ドメインの場合はCNAMEを維持してgit pushします。

1. config.tomlでテーマを変更

```
#theme = "ananke"
theme = "hugo-clarity"
```

2. docsを削除して、サイト再作成
```
cp -p ./docs ./docs-old
hugo
cp -p ./docs-old/CNAME ./docs
```

3.

```
git add.
git branch -m master main
git origin main
git push

```

---
