---
title: "Git tips"
date: 2021-01-09T16:19:14+09:00
draft: false
sidebar: false
categories:
  - "開発環境"
tags:
  - "git"
---

## originを変更

```
git remote set-url origin 変更先のurl
```

## リモートブランチ一覧

```
git branch -r
```

## 特定のリモートブランチをclone

```
git clone origin/リモートブランチ名:ローカルブランチ名
```