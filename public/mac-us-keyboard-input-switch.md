---
title: MacでUS、UKキーボード使用時の入力切替がうまくいかない問題の解決法
tags:
  - Mac
  - USキーボード
  - UKキーボード
private: false
updated_at: ''
id: null
organization_url_name: null
slide: false
ignorePublish: false
---
# 👍️ いいねのお願い
いつでも見返せるように、いいねをお願いします🙇  
コメントもお待ちしております🙇

# はじめに
**JISキーボード以外**を使用しているユーザーはおそらく入力切替で**Ctrl+Space**を使っているかと思います。その場合、入力切替がなかなか切り替わらないことございませんか？

筆者自身がこの現象に会って半年以上苦しみましたが、ついに解決法を見つけたので共有いたします。（なぜこれについて書いた記事がみつからなかったのか。。）

# 結論
以下のコマンドをターミナルで入力し、Macを再起動してください。
```zsh
defaults write -g ApplePressAndHoldEnabled -bool false
```
ターミナルとは：https://jp.minitool.com/data-recovery/open-terminal-mac-command-prompt.html

:::note warn
警告
このコマンドを打つことで、原因に示す機能がオフになります。
:::

# 原因
原因は以下の機能のせいです。。。
![キーを長押しした時](../img/mac-us-keyboard-input-switch/226_1.png)

この機能をオフにすることで入力切替がスムーズに行くようになりました。

もしこの機能を再度オンにしたい場合はこちらのコマンドをターミナルで入力してください。
```zsh
defaults write -g ApplePressAndHoldEnabled -bool true
```

# まとめ
この現象で悩んでいる人の救いになればと思います！  
同じ悩みを抱えていた人がいたら、👍️やコメントお願いします。(自分だけだったのかが知りたい。)