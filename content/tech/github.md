---
title: "github 備忘・対処メモ"
date: "2021-06-06"
draft: false
categories:
  - "tech"
tags:
  - "github"
featured_image: "/images/github.webp"
thumbnail:  "/images/github.webp"
toc: true

---

## .gitignoreが効かない

キャッシュ削除による解決を試みます。
```shell
git rm -r --cached .
```

## git push がreject

ローカルが正/originであることを確認して、強制的にpushします。
```shell
git push -f origin master
```

## git pull error マージエラーが発生


```shell
error: Your local changes to the following files would be overwritten by merge:
test.py
Please commit your changes or stash them before you merge.
Aborting
```

### Solve it by overwriting 上書きして解決する場合

 pull元が正しい前提で上書きを行います。

```shell
git fetch origin master
git reset --hard origin/master
git pull origin/master
```


## sshで2つのgithubアカウントを管理

~/.ssh/configに2つのアカウントを記載 2つ目をサブに設定
```shell
Host github github.com
  HostName github.com
  IdentityFile ~/.ssh/rsa-git
  User git
Host github github.com.sub
  HostName github.com
  IdentityFile ~/.ssh/rsa-git-sub
  User git
```
remote URLを以下に設定

```shell
git remote add origin git@github.com.sub:user2/repository.git
```

.git/configに以下の様に設定されているかを確認
```shell
[remote "origin"]
	url = git@github.com.sub:user2/repositry.git
```

sshにて2つのアカウントが動作することを確認

```shell
ssh -T git@github.com
Enter passphrase for key '/Users/user/.ssh/rsa-git':
Hi user1! You've successfully authenticated, but GitHub does not provide shell access.

ssh -T git@github.com.sub
Enter passphrase for key '/Users/user/.ssh/rsa-git-sub':
Hi user2! You've successfully authenticated, but GitHub does not provide shell access.

```



## レポジトリ登録備忘メモ

### github側

1. private repository新規登録

注意点
- README.mdは作成しないこと　※Localで作成する
- defaultのブランチはmaster ではなくmainであること


2. 右上のCodeからsshのURLを確認

　　git@github.com:username/new-rep.git



### ローカル側

1. ソースを管理したいディレクトリ・フォルダに移動
2. git init
3. git remote add origin git@github.com:username/new-rep.git
4. git add .
5. git commit -m "update"
6. git push origin main
