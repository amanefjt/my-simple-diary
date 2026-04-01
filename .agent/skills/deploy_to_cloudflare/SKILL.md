---
name: deploy_to_cloudflare
description: サイトを Cloudflare Pages にデプロイし、公開・更新の状況を確認します。
---

# Cloudflare Pages へのデプロイ手順 (deploy_to_cloudflare)

このスキルは、サイトの変更を GitHub に反映し、Cloudflare Pages による自動デプロイを監視するために使用します。

## 実行手順

1.  **Git による更新**: 
    - 変更を加えたファイルを `git commit` し、リモートリポジトリ（GitHub）に `git push` します。
2.  **デプロイ状況の確認**: 
    - Cloudflare Pages の管理画面、あるいは GitHub の Actions タブでビルドが正常に開始されたかを確認します。
3.  **URL での検証**: 
    - デプロイ完了後、公開済みの URL にアクセスし、変更内容が正しく反映されているかを確認します。

## 注意事項
- **Secrets の不足**: ビルドエラー（例：`HUGO_VERSION` の未設定）が発生した場合は、速やかに原因を特定し、ユーザーに設定の追加を依頼します。
- **リポジトリの不一致**: リポジトリ名（例：`fujita-shu-diary`）が変更された場合、Cloudflare 側のソース設定も更新する必要があります。

## トラブルシューティング
- もし Push が拒否された場合は、`git fetch` や `git pull` を試みるか、必要に応じて人間に確認の上、強制的な解決を行います。
