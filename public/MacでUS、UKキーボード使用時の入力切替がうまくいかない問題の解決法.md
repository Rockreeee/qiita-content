---
title: MacでUS、UKキーボード使用時の入力切替がうまくいかない問題の解決法
tags:
  - Mac
  - USキーボード
  - UKキーボード
private: false
updated_at: '2024-10-13T16:30:02+09:00'
id: 7a651ee62c16e297540a
organization_url_name: null
slide: false
ignorePublish: false
---
# 👍️ いいねのお願い
同じ悩みを抱えていた人がいたら、👍️やコメントお願いします。(自分だけだったのかが知りたい。)  

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
![原因](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/3907333/1be37a25-3f71-9fde-b031-8aa4248b85d0.png)


この機能をオフにすることで入力切替がスムーズに行くようになりました。

もしこの機能を再度オンにしたい場合はこちらのコマンドをターミナルで入力してください。
```zsh
defaults write -g ApplePressAndHoldEnabled -bool true
```

# まとめ
この現象で悩んでいる人の救いになればと思います！ 
