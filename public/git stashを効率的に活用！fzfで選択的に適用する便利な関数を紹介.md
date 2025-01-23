---
title: git stashを効率的に活用！fzfで選択的に適用する便利な関数を紹介
tags:
  - Zsh
  - Mac
  - Terminal
  - 初心者
  - dotfiles
private: false
updated_at: ''
id: null
organization_url_name: null
slide: false
ignorePublish: false
---

# 👍️ いいねのお願い
励みになるので、いいねをお願いします。 

# ✍️ はじめに
Gitを使って開発を進めていると、git stashを使って一時的に変更を退避させる場面が頻繁にあります。  
しかし、git stash listで一覧を確認した後、特定のstashを適用するには手動で名前を指定する必要があり、少し手間に感じることも。  
そんな煩わしさを解消するために、fzfを活用して、git stashのリストから選択して適用する便利な関数をご紹介します。

## こんな事ありませんか？
`git stash`しすぎて毎回どの番号かわからない。。 

`git stash list`するとこんな感じ

![スクリーンショット 2025-01-23 16.50.26.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/3907333/cdb39a55-d469-cabe-1be8-d4a7e99a89c0.png)

毎回`git stash list`してから、`git stash apply stash@{2}`する必要がある。。。

この動作をまとめられたらな。。。

# ✅ 実際の動作イメージ
`gsla`とターミナルで打ち込む

![スクリーンショット 2025-01-23 16.53.21.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/3907333/ca2ce1a0-13d8-57b5-0126-1c6c91c3d844.png)

ここで好きなものを選択すれば、選択したものが自動で`git stash apply`される＼(^o^)／


# 🚀 やり方
以下を`.zshrc`へ追加
### git stashリストをfzfでインタラクティブに選択し、選択したstashを適用するシェル関数
```zsh
# git stashしたリストの中から選択し、applyする関数
function git_stash_list_apply() {
    # stash list を取得して選択
    local selected_stash=$(git stash list | fzf --height=15 --prompt="Select a stash to apply: ")

    # 選択されなかった場合は終了
    if [[ -z "$selected_stash" ]]; then
        echo "No stash selected. Aborting."
        return 1
    fi

    # 選択された stash 名を抽出 (例: 'stash@{0}')
    local stash_name=$(echo "$selected_stash" | sed -E 's/^(stash@\{[0-9]+\}):.*/\1/')

    # stash apply を実行
    git stash apply "$stash_name"
}
```

### 簡単に呼び出せるようにaliasを設定
```zsh
alias gsla='git_stash_list_apply'
```

# 📝 まとめ
これを使うと、stashの番号が何だっけ問題が簡単に解決できます！
ぜひ使ってみてください！👋