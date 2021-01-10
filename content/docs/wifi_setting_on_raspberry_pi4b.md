---
title: "Raspberry Pi 4B のWifi設定"
date: 2021-01-10T17:21:45+09:00
draft: false
sidebar: false
toc: true
categories:
  - "運用"
tags:
  - "raspberry pi"
---

## wifi 設定

/etc/wpa_supplicant/wpa_supplicant.confにESSIDとwpaキーを設定する。

```
network={
        ssid="oooo"  # ESSID
        psk="xxxxxxxxx" # 暗号化キー
        group=CCMP
        key_mgmt=WPA-PSK　# 暗号化キーの管理方式
        priority=2 # 複数のnetworkブロックが定義されている場合の優先順位（大きいほど優先度が高い）
}

network={
        ssid="ooxxoo"
        scan_ssid=1    #ステルスSSIDの場合はこれを追記
        psk="xxxxxooooo"
        group=CCMP
        key_mgmt=WPA-PSK
        priority=1
}

```

WPA/WPA2は暗号化の規格のこと。

PSKは認証方式。事前に設定した暗号鍵を使う。

TKIP/CCIPは暗号化方式で、AESはCCIPに用いられる暗号化アルゴリズム。


[「WPA2-AES」と「WPA2-PSK（AES）」の違い](https://wa3.i-3-i.info/diff284security.html)

## IPアドレスの固定化

/etc/dhcpcd.confに設定を記述する。

```

interface wlan0
ssid XXXoo1
static ip_address=192.168.1.10/24
static routers=192.168.1.254
statis domain_name_server=1.1.1.1

```
