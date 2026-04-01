# トラブル対応ログ (troubleshooting_log.md)

開発中に発生したエラーとその解決策、再発防止策を累積します。

---

## 2026-04-01: Git 非互換エラー（Rejected）
### 現象
新しいリポジトリ（`fujita-shu-diary`）に対し、手元のデータを初めて Push しようとした際に `! [rejected] main -> main (fetch first)` というエラーで拒否された。

### 原因
GitHub 側でリポジトリ作成時に `README.md` を自動生成したため、GitHub 上に「ローカル（手元）には存在しない歴史（コミット）」が先にできてしまったため。

### 解決策
手元のデータ（85件の日記）を正解として上書きするため、以下のコマンドで強制 Push を行った。
```bash
git push -u origin main --force
```

### 再発防止
新しいリポジトリ作成時は、README などの初期ファイルを GitHub 上で作らず、「空のリポジトリ」として作成してから手元のデータを Push するのがスムーズである。

---

## 2026-04-01: Cloudflare Pages でリポジトリが見つからない
### 現象
Cloudflare Pages の新規プロジェクト作成画面で、新しく作った GitHub リポジトリ（`fujita-shu-diary`）が一覧に表示されない。

### 原因
GitHub 側で Cloudflare Pages アプリに対して、個別のリポジトリへのアクセス許可を与えていないため。

### 解決策
1. Cloudflare の画面にある「GitHub のリポジトリアクセスを構成する」リンクをクリック。
2. GitHub の設定画面で `fujita-shu-diary` を選択し、アクセスを許可して保存した。

### 再発防止
新しいリポジトリを追加した際は、常に GitHub のアプリ設定を確認し、Cloudflare への権限委譲が必要であることを意識する。
