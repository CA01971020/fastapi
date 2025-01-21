# 構成

```
/
├─ api
│  └─ main.py
├─ .gitignore
└─ README.md
```

## main.py

```py
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello, FastAPI!"}

```

# FastAPI 仮想環境での実行方法

## 仮想環境作成

```
python -m venv env
```

## 仮想環境有効化

```
.\env\Scripts\activate
```

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
