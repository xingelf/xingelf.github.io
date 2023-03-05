---
title: "Solidity 環境構築"
date: "2022-09-03"
draft: true
categories:
  - "Tech"
tags:
  - "Solidity"
  - "DApps"
---


# node.jsのインストール

## nvmによるインストール（複数バージョン管理できるため推奨）

https://github.com/nvm-sh/nvm

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```
.bashrcの最後に以下が追加されます
```
tail .bashrc
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```
sourceで.bashrcを読み込みます
```
source .bashrc
```

バージョンリストを取得

```
nvm list-remote

....
v16.17.0   (Latest LTS: Gallium)
 v17.0.0
 v17.0.1
 v17.1.0
 v17.2.0
 v17.3.0
 v17.3.1
 v17.4.0
 v17.5.0
 v17.6.0
 v17.7.0
 v17.7.1
 v17.7.2
 v17.8.0
 v17.9.0
 v17.9.1
 v18.0.0
 v18.1.0
 v18.2.0
 v18.3.0
 v18.4.0
 v18.5.0
 v18.6.0
 v18.7.0
 v18.8.0

```

ここではv16をインストールします。
```
nvm install v16.17.0
```
list コマンドで確認

```
$ nvm list
->     v16.17.0
default -> v16.17.0
iojs -> N/A (default)
unstable -> N/A (default)
node -> stable (-> v16.17.0) (default)
stable -> 16.17 (-> v16.17.0) (default)
lts/* -> lts/gallium (-> v16.17.0)
lts/argon -> v4.9.1 (-> N/A)
lts/boron -> v6.17.1 (-> N/A)
lts/carbon -> v8.17.0 (-> N/A)
lts/dubnium -> v10.24.1 (-> N/A)
lts/erbium -> v12.22.12 (-> N/A)
lts/fermium -> v14.20.0 (-> N/A)
lts/gallium -> v16.17.0
```



## aptによる通常のインストール

nodejsに加えてnpmもインストールします。
npmの場合、最新版がインストールされないケースもあるようです。

現在のバージョンを確認
```
$ sudo apt show nodejs
Package: nodejs
Version: 10.19.0~dfsg-3ubuntu1
Priority: extra
Section: universe/web
Origin: Ubuntu
```
aptによりインストール
```
sudo apt install nodejs

nodejs -v
```

npmのインストール

aptによりインストール

```
sudo apt install npm

npm -v
```

# Truffle プロジェクトの作成

プロジェクトのディレクトリを作成

```
mkdir helloworld
cd helloworld
```

truffleをインストール。メモリが少ないとOOMでエラーとなります。
1GB程度割り当ててください。

```
npm init
npm install truffle --save
npm WARN deprecated har-validator@5.1.5: this library is no longer supported
npm WARN deprecated mkdirp-promise@5.0.1: This package is broken and no longer maintained. 'mkdirp' itself supports promises now, please switch to that.
npm WARN deprecated multibase@0.6.1: This module has been superseded by the multiformats module
npm WARN deprecated node-pre-gyp@0.11.0: Please upgrade to @mapbox/node-pre-gyp: the non-scoped node-pre-gyp package is deprecated and only the @mapbox scoped package will recieve updates in the future
npm WARN deprecated request@2.88.2: request has been deprecated, see https://github.com/request/request/issues/3142
npm WARN deprecated multicodec@0.5.7: This module has been superseded by the multiformats module
npm WARN deprecated multicodec@1.0.4: This module has been superseded by the multiformats module
npm WARN deprecated uuid@3.4.0: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
npm WARN deprecated uuid@3.3.2: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
npm WARN deprecated uuid@3.2.1: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
npm WARN deprecated uuid@2.0.1: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
npm WARN deprecated uuid@3.2.1: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
npm WARN deprecated multibase@0.7.0: This module has been superseded by the multiformats module
npm WARN deprecated cids@0.7.5: This module has been superseded by the multiformats module

added 547 packages, and audited 579 packages in 55s

91 packages are looking for funding
  run `npm fund` for details

11 moderate severity vulnerabilities

To address all issues, run:
  npm audit fix

Run `npm audit` for details.
```

truffleプロジェクトを作成

```
$(npm bin)/truffle init

Starting init...
================

> Copying project files to /home/botuser/dapp/helloworld

Init successful, sweet!

Try our scaffold commands to get started:
  $ truffle create contract YourContractName # scaffold a contract
  $ truffle create test YourTestName         # scaffold a test

http://trufflesuite.com/docs

```

```
$ tree -L 1 .
.
├── contracts
├── migrations
├── node_modules
├── package-lock.json
├── package.json
├── test
└── truffle-config.js

4 directories, 3 files
```
# コンパイル


```
$(npm bin)/truffle compile

Compiling your contracts...
===========================
> Compiling ./contracts/Hello.sol solc-bin. Attempt #1
✓ Downloading compiler. Attempt #1.
CompileError: ParserError: Source file requires different compiler version (current compiler is 0.8.16+commit.07a7930e.Emscripten.clang) - note that nightly builds are considered to be strictly less than the released version
--> project:/contracts/Hello.sol:1:1:
 |
1 | pragma solidity ^0.5.0;
 | ^^^^^^^^^^^^^^^^^^^^^^^


Error: Truffle is currently using solc 0.8.16, but one or more of your contracts specify "pragma solidity ^0.5.0".
Please update your truffle config or pragma statement(s).
(See https://trufflesuite.com/docs/truffle/reference/configuration#compiler-configuration for information on
configuring Truffle to use a specific solc compiler version.)

Compilation failed. See above.
   at /home/botuser/dapp/helloworld/node_modules/truffle/build/webpack:/packages/compile-solidity/dist/run.js:95:1
   at Generator.next (<anonymous>)
   at fulfilled (/home/botuser/dapp/helloworld/node_modules/truffle/build/webpack:/packages/compile-solidity/dist/run.js:28:43)
Truffle v5.5.28 (core: 5.5.28)
Node v16.17.0
```

```
$(npm bin)/truffle compile

Compiling your contracts...
===========================
> Compiling ./contracts/Hello.sol
> Compilation warnings encountered:

   Warning: SPDX license identifier not provided in source file. Before publishing, consider adding a comment containing "SPDX-License-Identifier: <SPDX-License>" to each source file. Use "SPDX-License-Identifier: UNLICENSED" for non-open-source code. Please see https://spdx.org for more information.
--> project:/contracts/Hello.sol

,Warning: Visibility for constructor is ignored. If you want the contract to be non-deployable, making it "abstract" is sufficient.
--> project:/contracts/Hello.sol:5:3:
 |
5 |   constructor(string memory initMessage) public {
 |   ^ (Relevant source part starts here and spans across multiple lines).


> Artifacts written to /home/botuser/dapp/helloworld/build/contracts
> Compiled successfully using:
  - solc: 0.8.16+commit.07a7930e.Emscripten.clang

```
