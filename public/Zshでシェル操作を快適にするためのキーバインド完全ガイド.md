---
title: Zshでシェル操作を快適にするためのキーバインド完全ガイド
tags:
  - Zsh
  - Mac
  - Terminal
private: false
updated_at: '2024-10-27T21:54:47+09:00'
id: 716df96425d91b91a438
organization_url_name: null
slide: false
ignorePublish: false
---
# 👍️ いいねのお願い
いつでも見返せるようにいいねをお願いします🙇

# ✍️ はじめに
Zshは、強力でカスタマイズ可能なシェルで、多くのデフォルトのキーバインドが用意されています。ここでは、Zshのデフォルトキーバインドの**すべて**を一覧にして紹介します。

# 🖥️ コマンドで確認
以下のコマンドで出力できます。
```zsh
bindkey
```
出力結果
```zsh
"^@" set-mark-command
"^A" beginning-of-line
"^B" backward-char
"^D" delete-char-or-list
"^E" end-of-line
"^F" forward-char
"^G" send-break
"^H" backward-delete-char
"^I" expand-or-complete
"^J" accept-line
"^K" kill-line
"^L" clear-screen
"^M" accept-line
"^N" down-line-or-history
"^O" accept-line-and-down-history
"^P" up-line-or-history
"^Q" push-line
"^R" history-incremental-search-backward
"^S" history-incremental-search-forward
"^T" transpose-chars
"^U" kill-whole-line
"^V" quoted-insert
"^W" backward-kill-word
"^X^B" vi-match-bracket
"^X^F" vi-find-next-char
"^X^J" vi-join
"^X^K" kill-buffer
"^X^N" infer-next-history
"^X^O" overwrite-mode
"^X^U" undo
"^X^V" vi-cmd-mode
"^X^X" exchange-point-and-mark
"^X*" expand-word
"^X=" what-cursor-position
"^XG" list-expand
"^Xg" list-expand
"^Xr" history-incremental-search-backward
"^Xs" history-incremental-search-forward
"^Xu" undo
"^Y" yank
"^[^D" list-choices
"^[^G" send-break
"^[^H" backward-kill-word
"^[^I" self-insert-unmeta
"^[^J" self-insert-unmeta
"^[^L" clear-screen
"^[^M" self-insert-unmeta
"^[^_" copy-prev-word
"^[ " expand-history
"^[!" expand-history
"^[\"" quote-region
"^[\$" spell-word
"^['" quote-line
"^[-" neg-argument
"^[." insert-last-word
"^[0" digit-argument
"^[1" digit-argument
"^[2" digit-argument
"^[3" digit-argument
"^[4" digit-argument
"^[5" digit-argument
"^[6" digit-argument
"^[7" digit-argument
"^[8" digit-argument
"^[9" digit-argument
"^[<" beginning-of-buffer-or-history
"^[>" end-of-buffer-or-history
"^[?" which-command
"^[A" accept-and-hold
"^[B" backward-word
"^[C" capitalize-word
"^[D" kill-word
"^[F" forward-word
"^[G" get-line
"^[H" run-help
"^[L" down-case-word
"^[N" history-search-forward
"^[OA" up-line-or-search
"^[OB" down-line-or-search
"^[OC" forward-char
"^[OD" backward-char
"^[OF" end-of-line
"^[OH" beginning-of-line
"^[P" history-search-backward
"^[Q" push-line
"^[S" spell-word
"^[T" transpose-words
"^[U" up-case-word
"^[W" copy-region-as-kill
"^[[200~" bracketed-paste
"^[[3~" delete-char
"^[[A" up-line-or-history
"^[[B" down-line-or-history
"^[[C" forward-char
"^[[D" backward-char
"^[_" insert-last-word
"^[a" accept-and-hold
"^[b" backward-word
"^[c" capitalize-word
"^[d" kill-word
"^[f" forward-word
"^[g" get-line
"^[h" run-help
"^[l" down-case-word
"^[n" history-search-forward
"^[p" history-search-backward
"^[q" push-line
"^[s" spell-word
"^[t" transpose-words
"^[u" up-case-word
"^[w" copy-region-as-kill
"^[x" execute-named-cmd
"^[y" yank-pop
"^[z" execute-last-named-cmd
"^[|" vi-goto-column
"^[^?" backward-kill-word
"^_" undo
"!"-"~" self-insert
"^?" backward-delete-char
"\M-^@"-"\M-^?" self-insert
```

# 📋 Zsh デフォルトキーバインド一覧
| キーコンビネーション       | 操作 | 関数名 |
|-------------|-----------|----------|
| `Ctrl + @` | 現在のカーソル位置にマークを設定 |	set-mark-command |
| `Ctrl + A` | 行の先頭に移動 |	beginning-of-line |
| `Ctrl + B` | カーソルを1文字左に移動 |	backward-char |
| `Ctrl + D` | カーソル位置の文字を削除、またはリスト表示 |	delete-char-or-list |
| `Ctrl + E` | 行の末尾に移動 |	end-of-line |
| `Ctrl + F` | カーソルを1文字右に移動 |	forward-char |
| `Ctrl + G` | プロセスに中断信号を送信 |	send-break |
| `Ctrl + H` | カーソル左の文字を削除 |	backward-delete-char |
| `Ctrl + I` | コマンドの補完や拡張を行う |	expand-or-complete |
| `Ctrl + J` | 現在の行を実行（Enterと同等） |	accept-line |
| `Ctrl + K` | カーソルから行末まで削除 |	kill-line |
| `Ctrl + L` | 画面をクリア |	clear-screen |
| `Ctrl + M` | 現在の行を実行（Enterと同等） |	accept-line |
| `Ctrl + N` | 次の行やコマンド履歴に移動 |	down-line-or-history |
| `Ctrl + O` | 現在の行を実行して次の履歴コマンドを表示 |	accept-line-and-down-history |
| `Ctrl + P` | 前の行やコマンド履歴に移動 |	up-line-or-history |
| `Ctrl + Q` | 現在の入力行を保存して新しい行を開始 |	push-line |
| `Ctrl + R` | コマンド履歴を逆方向に検索 |	history-incremental-search-backward |
| `Ctrl + S` | コマンド履歴を前方向に検索 |	history-incremental-search-forward |
| `Ctrl + T` | 2文字を入れ替える |	transpose-chars |
| `Ctrl + U` | 行全体を削除 |	kill-whole-line |
| `Ctrl + V` | 特殊文字をエスケープして入力 |	quoted-insert |
| `Ctrl + W` | カーソル前の単語を削除 |	backward-kill-word |
| `Ctrl + X, Ctrl + B` | VIモードで括弧のペアに移動 |	vi-match-bracket |
| `Ctrl + X, Ctrl + F` | VIモードで次の指定文字を検索 |	vi-find-next-char |
| `Ctrl + X, Ctrl + J` | VIモードで行を結合 |	vi-join |
| `Ctrl + X, Ctrl + K` | バッファを削除 |	kill-buffer |
| `Ctrl + X, Ctrl + N` | 次の履歴コマンドを推測 |	infer-next-history |
| `Ctrl + X, Ctrl + O` | オーバーライトモードの切り替え |	overwrite-mode |
| `Ctrl + X, Ctrl + U` | 直前の操作を取り消す |	undo |
| `Ctrl + X, Ctrl + V` | VIコマンドモードに切り替え |	vi-cmd-mode |
| `Ctrl + X, Ctrl + X` | カーソル位置とマーク位置を入れ替え |	exchange-point-and-mark |
| `Ctrl + X *` | ワードを展開 |	expand-word |
| `Ctrl + X =` | カーソル位置を表示 |	what-cursor-position |
| `Ctrl + X G` | 展開候補をリスト表示 |	list-expand |
| `Ctrl + X g` | 展開候補をリスト表示 |	list-expand |
| `Ctrl + X r` | コマンド履歴を逆方向に検索 |	history-incremental-search-backward |
| `Ctrl + X s` | コマンド履歴を前方向に検索 |	history-incremental-search-forward |
| `Ctrl + X u` | 直前の操作を取り消す |	undo |
| `Ctrl + Y` | 直前に削除したテキストを貼り付け |	yank |

# 📝 まとめ

Zshのデフォルトキーバインドを活用することで、シェル操作が効率的になります。これらのキーバインドを覚えて、日々の作業を快適に進めましょう。自分に合ったカスタマイズを行うことで、さらに快適なシェル環境を構築できます。

# 💡 補足
Zshのキーバインドは、~/.zshrcファイル内で設定できます。
