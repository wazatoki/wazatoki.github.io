---
title: "docker execでcd"
date: 2022-08-20T18:55:00+09:00
lastmod: 2022-08-20T18:55:00+09:00
draft: false
sidebar: false
categories:
  - "インフラ"
tags:
  - "docker"
---

## docker execでディレクトリを移動したのちに何かの処理を行いたい場合

```
docker exec [コンテナ名] /bin/sh -c "cd foo/bar && npm run build"
```
