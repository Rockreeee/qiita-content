---
title: ターミナル上での 全角・ひらがな↔半角 変換コマンドを自作してみた！
tags:
  - '初心者'
  - 'zsh'
  - 'terminal'
  - 'dotfiles'
  - 'Mac'
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
こんな事よくありませんか？

![スクリーンショット 2024-10-30 11.08.40.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/3907333/bbd6bd67-f615-f933-691d-be8ddc7eafc2.png)  
と入力したいのに  
![スクリーンショット 2024-10-30 11.09.02.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/3907333/ca809199-9486-1a4d-75f5-efcf8f50c479.png)  
になってしまった！！

ここで、`Ctrl + X`を入力すると  
↓↓↓↓↓↓↓↓↓↓↓↓↓↓  
![スクリーンショット 2024-10-30 11.08.40.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/3907333/bbd6bd67-f615-f933-691d-be8ddc7eafc2.png)  
↑↑↑↑↑↑↑↑↑↑↑↑↑↑  
**自動で変換**される！！！ ＼(^o^)／

ものを作成しました。

# 🚀 やり方

必要なツール:

**nkf (Network Kanji Filter)**  
- nkfは、全角文字を半角文字に変換するために使用されます。  
- これは日本語の文字エンコード変換ツールで、Zshから全角→半角の変換に活用されています。

インストールコマンド例:
```zsh
brew install nkf
```

以下を`.zshrc`へ書き、読み込ませれば動作します。

```zsh
# 全角文字を半角文字に変換する関数
function zsh_convert_to_halfwidth() {
    # 入力された全角文字を半角文字に変換する
    local input="$BUFFER"
    local converted=$(echo "$input" | nkf -Z)
    
    # 変換結果を表示
    BUFFER="$converted"
    
    # カーソル位置を末尾に移動
    CURSOR=$#BUFFER
    zle -R
}

# ひらがなを対応する半角英字に変換する関数
function zsh_convert_hiragana_to_english() {
    local input="$BUFFER"

    # ひらがな -> 半角英字の変換テーブル
    typeset -A hira_to_eng=(

        [しゃ]=sya [しゅ]=syu [しょ]=syo
        [ちゃ]=cha [ちゅ]=chu [ちょ]=cho
        [じゃ]=ja [じゅ]=ju [じょ]=jo

        [あ]=a [い]=i [う]=u [え]=e [お]=o
        [か]=ka [き]=ki [く]=ku [け]=ke [こ]=ko
        [が]=ga [ぎ]=gi [ぐ]=gu [げ]=ge [ご]=go
        [さ]=sa [し]=si [す]=su [せ]=se [そ]=so
        [ざ]=za [じ]=zi [ず]=zu [ぜ]=ze [ぞ]=zo
        [た]=ta [ち]=ti [つ]=tu [て]=te [と]=to
        [だ]=da [ぢ]=di [づ]=du [で]=de [ど]=do
        [な]=na [に]=ni [ぬ]=nu [ね]=ne [の]=no
        [は]=ha [ひ]=hi [ふ]=fu [へ]=he [ほ]=ho
        [ば]=ba [び]=bi [ぶ]=bu [べ]=be [ぼ]=bo
        [ぱ]=pa [ぴ]=pi [ぷ]=pu [ぺ]=pe [ぽ]=po
        [ま]=ma [み]=mi [む]=mu [め]=me [も]=mo
        [や]=ya [ゆ]=yu [よ]=yo
        [ら]=ra [り]=ri [る]=ru [れ]=re [ろ]=ro
        [わ]=wa [を]=wo [ん]=n

    )

    # ひらがなを英字に変換
    local converted="$input"

    # 複数文字の変換を優先
    for key in ${(k)hira_to_eng}; do
        # 入力文字列に変換対象が含まれていれば置換
        converted=${converted//$key/${hira_to_eng[$key]}}
    done

    # 変換結果を表示
    BUFFER="$converted"
    CURSOR=$#BUFFER
    zle -R
}

# 全角スペースを半角スペースに変換する関数
function zsh_convert_fullwidth_space_to_halfwidth() {
    local input="$BUFFER"

    # 全角スペースを半角スペースに変換
    local converted="${input//　/ }"  # 全角スペースは「　」、半角スペースは「 」

    # 変換結果を表示
    BUFFER="$converted"

    # カーソル位置を末尾に移動
    CURSOR=$#BUFFER
    zle -R
}

# 各変換関数をまとめて呼び出すための関数
function zsh_convert_all() {
    zsh_convert_to_halfwidth
    zsh_convert_hiragana_to_english
    zsh_convert_fullwidth_space_to_halfwidth
}
zle -N zsh_convert_all

# ctrl + x にキーバインド
bindkey '^X' zsh_convert_all
```

:::note warn
ひらがな -> 半角英字の変換テーブル`hira_to_eng`は編集することをおすすめします。(入力の癖があると思うので。。)
:::


# 📝 まとめ
これを使うと、`全角・ひらがな↔半角変換`を一度に行い、入力をスマートに整えます！  
ぜひ使ってみてください！👋