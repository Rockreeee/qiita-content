---
title: Zshでシェル操作を快適にするためのキーバインド完全ガイド
tags:
  - Zsh
  - Mac
  - Terminal
private: false
updated_at: ''
id: 716df96425d91b91a438
organization_url_name: null
slide: false
ignorePublish: false
---
# 👍️ いいねのお願い
いつでも見返せるようにいいねをお願いします🙇

# はじめに
Zshは、強力でカスタマイズ可能なシェルで、多くのデフォルトのキーバインドが用意されています。ここでは、Zshのデフォルトキーバインドの**すべて**を一覧にして紹介します。

# コマンドで確認
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
"^X^E" edit-command-line
"^X^F" vi-find-next-char
"^X^J" vi-join
"^X^K" kill-buffer
"^X^N" infer-next-history
"^X^O" overwrite-mode
"^X^R" _read_comp
"^X^U" undo
"^X^V" vi-cmd-mode
"^X^X" exchange-point-and-mark
"^X*" expand-word
"^X=" what-cursor-position
"^X?" _complete_debug
"^XC" _correct_filename
"^XG" list-expand
"^Xa" _expand_alias
"^Xc" _correct_word
"^Xd" _list_expansions
"^Xe" _expand_word
"^Xg" list-expand
"^Xh" _complete_help
"^Xm" _most_recent_file
"^Xn" _next_tags
"^Xr" history-incremental-search-backward
"^Xs" history-incremental-search-forward
"^Xt" _complete_tag
"^Xu" undo
"^X~" _bash_list-choices
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
"^[," _history-complete-newer
"^[-" neg-argument
"^[." insert-last-word
"^[/" _history-complete-older
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
"^[OA" up-line-or-beginning-search
"^[OB" down-line-or-beginning-search
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
"^[[1;5C" forward-word
"^[[1;5D" backward-word
"^[[200~" bracketed-paste
"^[[3;5~" kill-word
"^[[3~" delete-char
"^[[5~" up-line-or-history
"^[[6~" down-line-or-history
"^[[A" up-line-or-beginning-search
"^[[B" down-line-or-beginning-search
"^[[C" forward-char
"^[[D" backward-char
"^[[Z" reverse-menu-complete
"^[_" insert-last-word
"^[a" accept-and-hold
"^[b" backward-word
"^[c" capitalize-word
"^[d" kill-word
"^[f" forward-word
"^[g" get-line
"^[h" run-help
"^[l" "ls^J"
"^[m" copy-prev-shell-word
"^[n" history-search-forward
"^[p" history-search-backward
"^[q" push-line
"^[s" spell-word
"^[t" transpose-words
"^[u" up-case-word
"^[w" kill-region
"^[x" execute-named-cmd
"^[y" yank-pop
"^[z" execute-last-named-cmd
"^[|" vi-goto-column
"^[~" _bash_complete-word
"^[^?" backward-kill-word
"^_" undo
" " magic-space
"!"-"~" self-insert
"^?" backward-delete-char
"\M-^@"-"\M-^?" self-insert
```

# Zsh デフォルトキーバインド一覧
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
| `Ctrl + X, Ctrl + E` | エディタでコマンドを編集 |	edit-command-line |
| `Ctrl + X, Ctrl + F` | VIモードで次の指定文字を検索 |	vi-find-next-char |
| `Ctrl + X, Ctrl + J` | VIモードで行を結合 |	vi-join |
| `Ctrl + X, Ctrl + K` | バッファを削除 |	kill-buffer |
| `Ctrl + X, Ctrl + N` | 次の履歴コマンドを推測 |	infer-next-history |
| `Ctrl + X, Ctrl + O` | オーバーライトモードの切り替え |	overwrite-mode |
| `Ctrl + X, Ctrl + R` | 補完機能を実行 |	_read_comp |
| `Ctrl + X, Ctrl + U` | 直前の操作を取り消す |	undo |
| `Ctrl + X, Ctrl + V` | VIコマンドモードに切り替え |	vi-cmd-mode |
| `Ctrl + X, Ctrl + X` | カーソル位置とマーク位置を入れ替え |	exchange-point-and-mark |
| `Ctrl + X *` | ワードを展開 |	expand-word |
| `Ctrl + X =` | カーソル位置を表示 |	what-cursor-position |
| `Ctrl + X ?` | デバッグ用補完コマンドを実行 |	_complete_debug |
| `Ctrl + X C` | ファイル名を補正 |	_correct_filename |
| `Ctrl + X G` | 展開候補をリスト表示 |	list-expand |
| `Ctrl + X a` | エイリアスを展開 |	_expand_alias |
| `Ctrl + X c` | 単語を補正 |	_correct_word |
| `Ctrl + X d` | 展開候補をリスト表示 |	_list_expansions |
| `Ctrl + X e` | 単語を展開 |	_expand_word |
| `Ctrl + X g` | 展開候補をリスト表示 |	list-expand |
| `Ctrl + X h` | 補完ヘルプを表示 |	_complete_help |
| `Ctrl + X m` | 最も最近のファイルを表示 |	_most_recent_file |
| `Ctrl + X n` | 次のタグを表示 |	_next_tags |
| `Ctrl + X r` | コマンド履歴を逆方向に検索 |	history-incremental-search-backward |
| `Ctrl + X s` | コマンド履歴を前方向に検索 |	history-incremental-search-forward |
| `Ctrl + X t` | タグを補完 |	_complete_tag |
| `Ctrl + X u` | 直前の操作を取り消す |	undo |
| `Ctrl + X ~` | Bashスタイルの補完をリスト表示 |	_bash_list-choices |
| `Ctrl + Y` | 直前に削除したテキストを貼り付け |	yank |
| `Esc + Ctrl + D` | 展開候補をリスト表示 |	list-choices |
| `Esc + Ctrl + G` | プロセスに中断信号を送信 |	send-break |
| `Esc + Ctrl + H` | カーソル前の単語を削除 |	backward-kill-word |
| `Esc + Ctrl + I` |Metaキーと一緒に挿入 | self-insert-unmeta |
| `Esc + Ctrl + J` |Metaキーと一緒に挿入 | self-insert-unmeta |
| `Esc + Ctrl + L` |画面をクリア | clear-screen |
| `Esc + Ctrl + M` |Metaキーと一緒に挿入 | self-insert-unmeta |
| `Esc + Ctrl + _` |前の単語をコピー | copy-prev-word |
| `Esc + Space` | コマンド履歴を展開 | expand-history |
| `Esc + !` | コマンド履歴を展開 | expand-history |
| `Esc + "` | リージョンをクォート | quote-region |
| `Esc + $` | 単語のスペルを確認 | spell-word |
| `Esc + '` | 現在の行をクォート | quote-line |
| `Esc + ,` | 最新の履歴を補完 | _history-complete-newer |
| `Esc + -` | 負の引数を指定 | neg-argument |
| `Esc + .` | 最後に使用した単語を挿入 | insert-last-word |
| `Esc + /` | 古い履歴を補完 | _history-complete-older |
| `Esc + 0` | 引数を0に設定 | digit-argument |
| `Esc + 1` | 引数を1に設定 | digit-argument |
| `Esc + 2` | 引数を2に設定 | digit-argument |
| `Esc + 3` | 引数を3に設定 | digit-argument |
| `Esc + 4` | 引数を4に設定 | digit-argument |
| `Esc + 5` | 引数を5に設定 | digit-argument |
| `Esc + 6` | 引数を6に設定 | digit-argument |
| `Esc + 7` | 引数を7に設定 | digit-argument |
| `Esc + 8` | 引数を8に設定 | digit-argument |
| `Esc + 9` | 引数を9に設定 | digit-argument |
| `Esc + <` | 履歴の先頭に移動 | beginning-of-buffer-or-history |
| `Esc + >` | 履歴の末尾に移動 | end-of-buffer-or-history |
| `Esc + ?` | 現在のコマンドを表示 | which-command |
| `Esc + A` | コマンドを保持して実行 | accept-and-hold |
| `Esc + B` | 単語単位でカーソルを左に移動 | backward-word |
| `Esc + C` | 単語をキャピタライズ | capitalize-word |
| `Esc + D` | カーソル位置から単語を削除 | kill-word |
| `Esc + F` | 単語単位でカーソルを右に移動 | forward-word |
| `Esc + G` | 現在の行を取得 | get-line |
| `Esc + H` | ヘルプを表示 | run-help |
| `Esc + L` | 単語を小文字に変換 | down-case-word |
| `Esc + N` | 履歴を前方検索 | history-search-forward |
| `Esc + OA` | 行を上に移動または履歴を検索 | up-line-or-beginning-search |
| `Esc + OB` | 行を下に移動または履歴を検索 | down-line-or-beginning-search |
| `Esc + OC` | カーソルを右に移動 | forward-char |
| `Esc + OD` | カーソルを左に移動 | backward-char |
| `Esc + OF` | 行の末尾に移動 | end-of-line |
| `Esc + OH` | 行の先頭に移動 | beginning-of-line |
| `Esc + P` | 履歴を後方検索 | history-search-backward |
| `Esc + Q` | 現在の行を保存して新しい行を開始 | push-line |
| `Esc + S` | 単語のスペルを確認 | spell-word |
| `Esc + T` | 単語を入れ替え | transpose-words |
| `Esc + U` | 単語を大文字に変換 | up-case-word |
| `Esc + W` | リージョンをコピー | copy-region-as-kill |
| `Esc + [1;5C` | 単語単位でカーソルを右に移動 | forward-word |
| `Esc + [1;5D`	| 単語単位でカーソルを左に移動 | backward-word |
| `Esc + [200~`	| ブラケットペーストモードを開始 | bracketed-paste |
| `Esc + [3;5~`	| 単語を削除 | kill-word |
| `Esc + [3~` | 文字を削除 | delete-char |
| `Esc + [5~`	| 履歴を上に移動 | up-line-or-history |
| `Esc + [6~`	| 履歴を下に移動 | down-line-or-history |
| `Esc + [A` | 行を上に移動または履歴を検索 | up-line-or-beginning-search |
| `Esc + [B` | 行を下に移動または履歴を検索 |down-line-or-beginning-search
| `Esc + [C` |カーソルを右に移動 | forward-char |
| `Esc + [D` | カーソルを左に移動 | backward-char |
| `Esc + [Z` | メニュー補完を逆順に実行 | reverse-menu-complete |
| `Esc + _` |	 最後に挿入した単語を再挿入 | insert-last-word |
| `Esc + a` |	コマンドを保持して実行 | accept-and-hold |
| `Esc + b` |	単語単位でカーソルを左に移動 | backward-word |
| `Esc + c` |	単語をキャピタライズ | capitalize-word |
| `Esc + d` |	カーソル位置から単語を削除 | kill-word |
| `Esc + f` |	単語単位でカーソルを右に移動 | forward-word |
| `Esc + g` |	現在の行を取得 | get-line |
| `Esc + h` |	ヘルプを表示 | run-help |
| `Esc + l` |	コマンドをクリアしlsコマンドを実行 | "ls^J"っっっっっっっっ |
| `Esc + m` |	前のシェルコマンドをコピー | copy-prev-shell-word |
| `Esc + n` |	履歴を前方検索 | history-search-forward |
| `Esc + p` |	履歴を後方検索 | history-search-backward |
| `Esc + q` |	現在の行を保存して新しい行を開始 | push-line |
| `Esc + s` |	単語のスペルを確認 | spell-word |
| `Esc + t` |	単語を入れ替え | transpose-words |
| `Esc + u` |	単語を大文字に変換 | up-case-word |
| `Esc + w` |	リージョンを削除 | kill-region |
| `Esc + x` |	名前付きコマンドを実行 | execute-named-cmd |
| `Esc + y` |	直前に削除したテキストを入れ替えて貼り付け | yank-pop |
| `Esc + z` |	最後に実行した名前付きコマンドを再実行 | execute-last-named-cmd |
| `Esc +	\|` | 指定の列に移動 | vi-goto-column | 
| `Esc + ~` | Bashスタイルの補完を実行 | _bash_complete-word |
| `Esc + Ctrl + ?` | カーソル前の単語を削除 | backward-kill-word |
| `Ctrl + _` | 直前の操作を取り消す | undo |
| `Space`	| 自動補完	| magic-space |
| `! ～ ~` | 文字を入力 (セルフインサート) |	self-insert |
| `Ctrl + ?` | カーソル前の文字を削除 | backward-delete-char |
| `Meta + Ctrl + @ ～ Meta + Ctrl + ?` | 文字を入力 (セルフインサート)	 |self-insert |

# まとめ

Zshのデフォルトキーバインドを活用することで、シェル操作が効率的になります。これらのキーバインドを覚えて、日々の作業を快適に進めましょう。自分に合ったカスタマイズを行うことで、さらに快適なシェル環境を構築できます。

# 補足
Zshのキーバインドは、~/.zshrcファイル内で設定できます。
