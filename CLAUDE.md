# tournament-viewer 開発ルール

## 作業開始時

**必ず最初に GitHub の最新を取得する。**
複数環境で開発しているため、前回の作業が別マシンで行われている可能性がある。

```bash
git fetch origin && git status
git pull origin main   # ローカルが遅れていたらプル
```

## 変更前の確認

大きな変更（UI追加・構造変更など）は実装前にユーザーに方針を確認する（"やる前にきいて"）。

## デプロイ

`git push` 後、GitHub Actions の Pages デプロイが完了するまで見届ける。

```bash
gh run watch $(gh run list --limit 1 --json databaseId -q '.[0].databaseId') --exit-status
```
