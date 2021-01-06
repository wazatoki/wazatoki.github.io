---
title: "NTPを使ったRaspberry Piの時刻合わせ"
date: 2021-01-06T18:53:00+09:00
draft: false
sidebar: false
toc: false
categories:
  - "運用"
tags:
  - "raspberry pi"
  - "ntp"
---

Raspberry Pi 4 model Bを使って確認しました。

というかsystemd-timesyncdを使っているなら大体同じ。

設定ファイル/etc/systemd/timesyncd.confを修正します。

```
cd /etc/systemd
sudo cp -p timesyncd.conf timesyncd.conf.org
sudo vi timesyncd.conf
```

以下の内容を[Time]の下に追記する。

```
NTP=ntp.jst.mfeed.ad.jp ntp.nict.jp time.google.com
```

NTP=の後にNTPサーバのホスト名かIPを書く。複数ある時は空白でで区切る。

（参考）[systemd-timesyncd](https://wiki.archlinux.jp/index.php/Systemd-timesyncd)

FallbackNTPについてはこのような記事を投稿している人がいた。

[timesyncdのFallbackNTPは「予備サーバー」ではない](https://qiita.com/sskki/items/6a73fade9bf4d8f93d93)

知らなかっったです。



