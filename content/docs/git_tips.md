---
title: "Git tips"
date: 2021-10-10T10:07:00+09:00
draft: false
sidebar: false
categories:
  - "インフラ"
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

## サブモジュールを合わせてclone

```
git clone --recursive クローンしたいリポジトリ

```

## サブモジュールのcloneを忘れたとき（サブモジュールの更新）

```
git submodule update --init --recursive

```
