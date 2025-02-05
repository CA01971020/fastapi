# 目次
* [前提](#前提)
    * [ディレクトリ構成](#ディレクトリ構成)
* [FastAPIインストール](#FastAPIインストール)
* [main.py](#main.py)
* [FastAPI仮想環境での実行方法](#FastAPI仮想環境での実行方法)
    *  [仮想環境作成](#仮想環境作成)
    *  [仮想環境有効化](#仮想環境有効化)
    *  [仮想環境有効化](#仮想環境有効化)
    *  [パッケージインストール](#パッケージインストール)
    *  [アプリケーション実行](#アプリケーション実行)
    *  [仮想環境無効化](#仮想環境無効化)
* [実行結果の確認](#実行結果の確認)
* [securityError](#securityError)
* [詳細](#詳細はZennの記事に記載)

# 前提

- Python 実行環境

## ディレクトリ構成

```
/
├─ api
│  └─ main.py
├─ env
├─ .gitignore
└─ README.md
```

# FastAPIインストール

```shell
pip install fastapi[all]
```

# main.py

```py
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello, FastAPI!"}

```

# FastAPI仮想環境での実行方法

## 仮想環境作成

```
python -m venv env
```

## 仮想環境有効化

```
.\env\Scripts\activate
```

- [セキュリティーポリシーのエラーが発生した場合](#securityError)

## パッケージインストール

```
pip install fastapi uvicorn
```

## アプリケーション実行

```
uvicorn api.main:app --reload
```

## 仮想環境無効化

```
deactivate
```

# 実行結果の確認

default  
http://127.0.0.1:8000

docs  
http://127.0.0.1:8000/docs

redoc  
http://127.0.0.1:8000/redoc

---

# securityError

### 現在のポリシー確認方法

```powershell
Get-ExecutionPolicy
```

### 現在のユーザのセキュリティーポリシーを RemoteSigned に変更

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### セキュリティーポリシーの一覧とスコープ一覧

```powershell
Get-ExecutionPolicy -List
```

# 詳細は Zenn の記事に記載

[FastAPI 入門 「Hello FastAPI!」 まで。](https://zenn.dev/aputech/articles/bad52ee80f2cc2)
