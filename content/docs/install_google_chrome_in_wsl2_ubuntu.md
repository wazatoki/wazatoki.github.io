---
title: "Install_google_chrome_in_wsl2_ubuntu"
date: 2021-01-09T16:19:14+09:00
draft: false
sidebar: false
categories:
  - "開発環境"
tags:
  - "wsl2"
  - "ubuntu"
  - "google chrome"
  - "angular"
---

## google chromeのインストール

```
sudo apt-get update
sudo apt-get install libappindicator1 libappindicator3-1 fonts-liberation
curl -O https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
# ここで依存関係のエラーが出るので依存をfixする
sudo apt --fix-broken install

# もう一度インストール
sudo dpkg -i google-chrome-stable_current_amd64.deb
```

## angularでユニットテストを行う時の設定

karuma.conf.js
```

browsers: ['Chrome'],
customLaunchers: {
    ChromeHeadlessCI: {
    base: 'ChromeHeadless',
    flags: ['--no-sandbox']
    }
},

```

## テストを実行するときは

```
npx ng test --browsers=ChromeHeadlessCI

```