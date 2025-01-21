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
uvicorn main:app --reload
```

## 仮想環境無効化

```
deactivate
```
