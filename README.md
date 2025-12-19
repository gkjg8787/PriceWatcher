# PriceWatcher

## 概要

[kakakuscraping-fastapi](https://github.com/gkjg8787/kakakuscraping-fastapi)を中心とした商品価格の監視環境を構築するためのものです。

## 使い方

1. git clone でこのリポジトリをダウンロードします。

2. .env ファイルを作成します。[external_search](https://github.com/gkjg8787/external_search)の gemini を使用するために必要です。APIKeyはGoogleAIStudioで作成できます(2025/12/19時点)。

```
mkdir search
echo "GEMINI_API_KEY=your_api_key" >> search/.env
```

3.  初回はスクリプトで起動して 各コンテナの settings.py を修正し、コンテナを作成します。

```bash
bash create_container.sh
```

4. 起動後、`localhost:8000`にアクセスして操作。または`search_gui`から検索して URL を登録。

## 前提条件

- Docker
- gemini api

## 注意

- `search_gui`から検索して`kakakuscraping`へ登録する際には search_gui → search2kakaku(search2kakakuへの登録) → kakakuscraping(search2kakakuから登録)という手順を踏む必要があります。
- `search_gui`で検索ラベルを作成した際にHTMLから情報を取得するプログラムをAIに作成してもらうため初回は時間がかかります。

## コンテナ

- 各コンテナの説明はそれぞれのリポジトリで。
- [kakakuscraping-fastapi](https://github.com/gkjg8787/kakakuscraping-fastapi)
- [search2kakaku](https://github.com/gkjg8787/search2kakaku)
- [search_gui](https://github.com/gkjg8787/external_search_gui)
- [external_search](https://github.com/gkjg8787/external_search)
- [nodriver_api](https://github.com/gkjg8787/nodriver_api)
