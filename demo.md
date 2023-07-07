# デモ内容

## 準備

http://localhost:3000/ を開く

## プロジェクト削除

「管理」クリック

「プロジェクト」クリック

削除クリック

→403になる．

## ユーザーを削除

「管理」クリック

「ユーザー」クリック

削除クリック

→403になる．

## Issue削除

「プロジェクト」クリック

「rtnds-2023-07-03-1」クリック

「チケット」クリック

Issueの行で右クリック

→「チケットを削除」が非活性化されている．

## Issue削除をAPIで

```console
curl --silent \
  --dump-header - \
  --header 'Content-Type: application/json' \
  --header 'X-Redmine-API-Key: f1dcd7245a6bb18d36df3a1d2bebde9f1fc99280 \
  --request DELETE \
  http://localhost:3000/issues/2.json'
```

## 一時的な削除有効化

「管理」クリック

「一時的な削除有効化」クリック

「ユーザー」と「Expire after」

「作成」クリック

## rails console

```ruby
issue = Issue.first!
issue.destroy!
```
