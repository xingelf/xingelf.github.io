---
title: ""
date: "2000-01-01"
draft: true
categories:
tags:
---


install時のエラー


error: command 'x86_64-linux-gnu-gcc' failed with exit status 4

----------------------------------------
Failed building wheel for cvxpy

メモリ不足と想定　500MB→１GBへ



RuntimeError: CMake must be installed to build qdldl

----------------------------------------
Failed building wheel for qdldl


### cmakeのインストール

azurebot03@Bot03:~/trendBot$ cmake --version

Command 'cmake' not found, but can be installed with:

sudo snap install cmake  # version 3.20.2, or
sudo apt  install cmake

See 'snap info cmake' for additional versions.

azurebot03@Bot03:~/trendBot$ sudo apt install cmake
