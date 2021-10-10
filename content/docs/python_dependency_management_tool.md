---
title: "Python_dependency_management_tool"
date: 2021-10-10T01:53:33Z
draft: false
categories:
  - "development"
tags:
  - "python"
---

## pipenv

新規プロジェクトでPipfileを元にして最新のモジュールをインストールしたい場合。

```
pipenv install
```

特定のモジュールをインストールしたい場合

```
pipenv install モジュール名称
```

既存のプロジェクトでモジュールを最新化したい場合

```
pipenv update
```

新規プロジェクトでPipfile.lockを元にしてモジュールをインストールしたい場合。

```
pipenv sync
```

Pipfile.lockを最新化したい場合。

```
pipenv lock
```

Pipfile.lockをキャッシュをクリアして最新化したい場合。
キャッシュの不具合でpipenv syncやpipenv lockがうまくいかないとき。

```
pipenv lock --clear
```

requirements.txtの生成
```
pipenv lock --requirements > ./requirements.txt

or

pipenv lock -r > ./requirements.txt
```

## pip

requirements.txtを元にしてモジュールをインストールしたい場合。

```
pip install -r requirements.txt
```

requirements.txtの書き出し

```
pip freeze > ./requirements.txt
```