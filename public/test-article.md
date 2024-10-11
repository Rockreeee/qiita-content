---
title: test-article
tags:
  - 'test'
private: false
updated_at: ''
id: null
organization_url_name: null
slide: false
ignorePublish: false
---
# テスト記事: Qiitaへの自動投稿テスト

この記事は、GitHub Actionsを使ってQiitaに自動投稿されるテスト記事です。

## 概要

- GitHubに`git push`した際に、この記事がQiitaに自動投稿されるかを確認します。
- この設定では、`main`ブランチにプッシュすることで、記事がQiitaに投稿されます。

## 設定手順

1. GitHubリポジトリに`qiita-cli`の設定を行い、GitHub Actionsを有効化します。
2. `.github/workflows`ディレクトリに、Qiitaに記事を投稿するワークフローファイルを作成します。
3. `git push`を実行して、GitHub Actionsが正しく動作するか確認します。

## 結果

- 記事が自動で投稿されれば、設定は成功です。
- QiitaのAPIトークン（`QIITA_TOKEN`）が正しく設定されていることを確認してください。

---

このテスト記事がうまく投稿されることを確認しましょう！