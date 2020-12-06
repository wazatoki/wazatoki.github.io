---
title: "windows10 + python embeded + visual studio code 環境作成"
date: 2020-11-29T16:41:07+09:00
draft: false
categories:
  - "開発環境"
tags:
  - "python"
  - "visual studio code"
  - "ソフトウエア運用"
---

配布用にpython embededを利用することを想定して開発環境を作成した際、調べたことの記録です。

## ダウンロード

下記のサイトよりダウンロードして適当なフォルダに展開します。

https://www.python.org/downloads/windows/

## pipのインストール

下記のサイトよりget-pip.pyをダウンロードして展開したフォルダにコピーします。

https://bootstrap.pypa.io/

展開したフォルダ内にあるpython**._pthを編集してコメントアウトを外します。 **はバージョン番号。

3.9だったらファイル名はpython39._pth

```

#import site → import site

```
展開したフォルダ内にあるpython.exeを使って下記を実行します。

```

.\python.exe get-pip.py

```
## visual studio codeの設定

以下のフォルダ構成を想定しています。

```
+-project_folder
|
+-python*.*.*-embed-win32
|
+-src
  |
  +-.env
  |
  +-main.py
|
+-pylintrc
|
+-projectname.code-workspace

```

File → Save Workspace Asと選択してフォルダにprojectname.code-workspaceを作成します。

projectname.code-workspaceの内容を下記の内容に修正します。

```

{
	"folders": [
		{
			"path": "."
		}
	],
	"settings": {
		"files.eol": "\n",
		"terminal.integrated.env.windows": {
			"PATH": "{プロジェクトフォルダまでのpath}\\python-*.*.*-embed-win32;{プロジェクトフォルダまでのpath}\\python-*.*.*-embed-win32\\Scripts"
		},
		"python.pythonPath": "{プロジェクトフォルダまでのpath}\\python-*.*.*-embed-win32\\python.exe"
	}
}


```
srcフォルダ内に.envファイルを作成して下記の内容を記載します。

```

PYTHON_PATH=../python-*.*.*-embed-win32

```

プロジェクトフォルダ直下にpylintrcファイルを作成して下記の内容を記載します。

```

init-hook="./src"

```

以上となります。
