---
title: "Pylint使用時のインポートエラー対策"
date: 2021-01-02T19:00:48+09:00
draft: false
sidebar: false
categories:
  - "開発環境"
tags:
  - "python"
  - "visual studio code"
---

visual studio codeのpythonプラグインでpylintを使用した時に表示されたimportエラーの対応記録。

## workspace.code-workspace に設定記載

```

"settings": {
    "python.linting.pylintPath": "{path to pylint}",
    "python.pipenvPath": "{path to pipenv}",
    "python.pythonPath": "{path to python}"
}

```

## pylintrcの設定

pylintrcの生成

```

$>pylint --generate-rcfile > pylintrc

```
生成したpylintrcを編集

```

init-hook='import sys; sys.path.append("path to project root dir")'

```