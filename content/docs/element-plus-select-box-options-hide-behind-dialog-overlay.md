---
title: "Element PlusのSelect Box OptionsがモーダルダイアログのOverlayの後ろに隠れる"
date: 2022-08-17T23:48:24Z
draft: false
sidebar: false
toc: false
categories:
  - "development"
tags:
  - "element-plus"
  - "vue3"
---

モーダルダイアログ内に設置したセレクトボックスのオプションがモーダルの下に隠れる。

class="el-overlay"のz-indexの値より小さな値がclass="el-popper"のz－印出xに設定されるための現象。

el-selectの属性に:teleported="false"を設定して解決。