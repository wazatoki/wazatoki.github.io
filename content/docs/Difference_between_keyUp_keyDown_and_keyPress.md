---
title: "keyupとkeydownとkeypressの違い"
date: 2022-08-18T09:07:24Z
draft: false
sidebar: false
toc: false
categories:
  - "development"
tags:
  - "javascript"
---

発火する順番は、keyDown → keyPress → keyUp

keydownとkeyupは、全てのキーに対応するが、keypressはシフトキーなど文字でない入力は反応しない。

keyPressは機能が削除される予定の為、非推奨。

[mdn web docs: Element: keypress イベント ](https://developer.mozilla.org/ja/docs/Web/API/Element/keypress_event)