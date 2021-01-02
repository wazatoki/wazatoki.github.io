---
title: "hugo開発サーバーへlocalhost外からのアクセス"
date: 2021-01-02T21:45:53+09:00
draft: false
categories:
  - "blog"
tags:
  - "hugo"
---

hugo server -Dで開発サーバーを起動するとlocalhost外からアクセスできない。

```

$>hugo server --baseURL="192.168.0.1" --bind="192.168.0.1" --port=8080

```
で起動するとhttp://192.168.0.1:8080でアクセスできる。

