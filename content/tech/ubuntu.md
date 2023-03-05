---
title: "Ubuntu on Azure メモ"
date: "2022-10-01"
draft: false
categories:
  - "Tech"
tags:
  - "Ubuntu"
  - "Linux"

---


# 定期メンテナンス

```
sudo apt update
sudo apt upgrade
```


## 定期メンテ時のエラー　11: Resource temporarily unavailable

sudo upgradeでリソース不足を検知した場合の対処です。

```
E: Could not get lock /var/lib/dpkg/lock – open (11: Resource temporarily unavailable)
E: Unable to lock the administration directory (/var/lib/dpkg/), is another process using it?
```

psコマンドでaptが存在することを確認します。存在する場合は、少しまって再度実行するか、再起動できる場合は再起動してしまうと早いです。

```
ps aux | grep -i apt
```


# 定期的なapt updateを停止

毎日AM6時と18時にaptが動作しリソース消費した結果OOM(Out-of-Memory)となる症状がありました（メモリは少なめ）。
以下がデフォルトとなっているため、自動起動を停止しました。

```
$ systemctl cat apt-daily.timer
# /lib/systemd/system/apt-daily.timer
[Unit]
Description=Daily apt download activities

[Timer]
OnCalendar=*-*-* 6,18:00
RandomizedDelaySec=12h
Persistent=true

[Install]
WantedBy=timers.target
```

```
$ systemctl cat apt-daily-upgrade.timer
# /lib/systemd/system/apt-daily-upgrade.timer
[Unit]
Description=Daily apt upgrade and clean activities
After=apt-daily.timer

[Timer]
OnCalendar=*-*-* 6:00
RandomizedDelaySec=60m
Persistent=true

[Install]
WantedBy=timers.target
```

apt.systemd.dailyで自動実行を無効化(AutoAptEnable)

```
sudo vi /usr/lib/apt/apt.systemd.daily
```

```
# check if the user really wants to do something
#AutoAptEnable=1  # default is yes
AutoAptEnable=0  # default is yes
eval $(apt-config shell AutoAptEnable APT::Periodic::Enable)
if [ $AutoAptEnable -eq 0 ]; then
    exit 0
fi
```
