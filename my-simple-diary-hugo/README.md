# my-simple-diary (Hugo版)

このリポジトリは、既存の手動HTML日記を **Hugo + Markdown** に移行したものです。

- 記事は `content/diary/YYYY-MM-DD.md` に1日1ファイルで保存します。
- トップページ `/` は **全文をすべて時系列（新しい順）** で表示します。
- 個別ページは `/diary/YYYY-MM-DD/` です。

## 1) ローカルで確認

Hugo をインストール後、プロジェクト直下で：

```bash
hugo server
```

表示: http://localhost:1313/

## 2) Cloudflare Pages でデプロイ

Cloudflare Pages の「Framework preset」で **Hugo** を選び、次を設定します。

- **Build command**: `hugo`
- **Build output directory**: `public`
- **Environment variables**: `HUGO_VERSION`（例: `0.146.6` など）

> 注: Markdown内の生HTML（既存記事のHTML）を表示するため、`hugo.toml` で `markup.goldmark.renderer.unsafe = true` を有効化しています。

## 3) 新しい日記を追加

`content/diary/2026-02-03.md` のようなファイルを追加して push すれば、トップと個別ページが同時に更新されます。

---

移行元データ範囲: 2025-11-30 〜 2026-02-02
生成件数: 59
