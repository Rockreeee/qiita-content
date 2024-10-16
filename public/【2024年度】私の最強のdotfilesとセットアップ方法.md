---
title: 【2024年度】私の最強のdotfilesとセットアップ方法
tags:
  - 'Dotfiles'
  - 'Zsh'
  - 'ShellScript'
  - 'VSCode'
  - 'Mac'
  - 'Linux'
private: false
updated_at: ''
id: null
organization_url_name: null
slide: false
ignorePublish: true
---
# 👍️ いいねのお願い
いつでも見返せるようにいいねをお願いします🙇

# はじめに
この記事では、私がどのようにしてdotfilesを整理し、セットアップを自動化しているかを紹介します。  
以下のファイルをダウンロードして使用してもよいですし、参考にして自身で構築してもよいです。👍️  

**【2024年度】私の最強のdotfilesのダウンロードは[こちら](https://github.com/Rockreeee/dotfiles)**  

このファイルを使えば以下の環境の構築が簡単にできます。

```
構築される環境:
•	homebrew
•	oh-my-zsh(powerlevel10k)
•	dotfiles(.zshrc, .zshenv, .gitconfig...)
•	macOS
•	VSCode
```


# dotfilesとは
dotfilesとは、主にLinuxやmacOSなどのUnix系のオペレーティングシステムで使われる設定ファイルのことを指します。これらのファイルは通常、.（ドット）で始まる名前を持ち、ホームディレクトリに隠しファイルとして存在します。たとえば、.zshrc、.vimrc、.gitconfigなどが典型的な例です。

dotfilesの役割は次の通りです：

1. 設定の管理

	•	各アプリケーションやシェル（ZshやBashなど）のカスタム設定を保存するために使われます。例えば、.zshrcはZshの設定ファイルであり、シェルの動作、エイリアス、環境変数の定義などを行います。

2. 環境の移行

	•	dotfilesを一箇所にまとめ、GitHubなどのバージョン管理システムに保存しておくことで、他のマシンでも同じ環境を簡単に再現することができます。

```
Dotfilesに含まれる代表的なファイル

• .zshrc: Zshシェルの設定ファイル
• .vimrc: Vimエディタの設定ファイル
• .gitconfig: Gitのグローバル設定ファイル
• .bash_profile: Bashシェルの設定ファイル（macOSでよく使われる）
• .tmux.conf: tmuxターミナルマルチプレクサの設定ファイル
```

これらのファイルは、自分の作業効率を上げるためにカスタマイズされることが多く、プログラマーや開発者にとっては非常に重要な役割を果たします。

# 【2024年度】私の最強のdotfilesの構成
```zsh
~/dotfiles/
├── config/
│   ├── vscode/   
│   │   ├── extensions          # vscodeの拡張機能一覧
│   │   ├── keybindings.json    # vscodeのキーバインド
│   │   └── settings.json       # vscodeの設定ファイル
│   └── zsh/   
│       ├── alias.zsh           # エイリアスの定義
│       ├── bindkey.zsh         # キーバインドの定義
│       ├── completion.zsh      # キーバインドの定義
│       ├── env.zsh             # 環境変数の設定
│       ├── functions.zsh       # 関数の定義
│       └── oh-my-zsh.zsh       # oh-my-zshの設定
├── setup-scripts/
│   ├── install-brew-package.sh # homebrewのインストールなど
│   ├── install-oh-my-zsh.sh    # oh-my-zshのインストール
│   ├── setup-git.sh            # gitのセットアップ
│   ├── setup-MacOS.sh          # mac設定のセットアップ
│   ├── setup-vscode.sh         # vscodeのセットアップ
│   └── setup-zsh.sh            # zshのセットアップ
├── .gitconfig                  # Gitの設定ファイル
├── .gitconfig-personal         # 個人のGitの設定ファイル
├── .gitconfig-work             # 会社のGitの設定ファイル
├── .gitconfig                  # Gitの設定ファイル
├── .zshenv                     # 全シェルで適用される設定
└── .zshrc                      # インタラクティブシェル用の設定
```
:::note warn
警告
.gitconfig-personalと.gitconfig-workはご自身で追加してください。内容は以下を参考にしてください。
:::
- **.gitconfig-personal**: 個人のGitの設定ファイル
```zsh
[user]
	name = gitアカウントの名前【個人】
	email = gitアカウントのメアド【個人】
```

- **.gitconfig-work**: 会社のGitの設定ファイル
```zsh
[user]
	name = gitアカウントの名前【会社】
	email = gitアカウントのメアド【会社】
```

# セットアップ方法
【2024年度】私の最強のdotfilesでは**各機能個別にセットアップを行います。**  
:::note alert
より強い警告
各ファイルの中身を理解した上で実行してください。実行は自己責任でお願いします。
:::

## zsh環境のセットアップ
### homebrewパッケージをインストール
```zsh
# 実行権限付与
chmod +x ~/dotfiles/setup-scripts/install-brew-packages.sh
# 実行
~/dotfiles/setup-scripts/install-brew-packages.sh
```
dotfilesの環境構築のために必要なパッケージをhomebrewを用いてインストールします。

### oh-my-zshをインストール
```zsh
# 実行権限付与
chmod +x ~/dotfiles/setup-scripts/install-oh-my-zsh.sh
# 実行
~/dotfiles/setup-scripts/install-oh-my-zsh.sh
```
Oh My Zshは、Zshシェルのカスタマイズを簡単に行えるフレームワークで、豊富なプラグインやテーマを使ってシェルを便利にできるツールです。

### power10kインストール
```zsh
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```
Powerlevel10kは、Zsh用の高速でカスタマイズ可能なテーマで、情報を見やすく表示しつつ、シェルのパフォーマンスを向上させる人気のテーマです。

### ｚｓｈ環境のセットアップ
```zsh
# 実行権限付与
chmod +x ~/dotfiles/setup-scripts/setup-zsh.sh
# 実行
~/dotfiles/setup-scripts/setup-zsh.sh
```

## git環境のセットアップ
```zsh
# 実行権限付与
chmod +x ~/dotfiles/setup-scripts/setup-git.sh
# 実行
~/dotfiles/setup-scripts/setup-git.sh
```


## Mac環境のセットアップ
```zsh
# 実行権限付与
chmod +x ~/dotfiles/setup-scripts/setup-MacOS.sh
# 実行
~/dotfiles/setup-scripts/setup-MacOS.sh
```

## VSCode環境のセットアップ
```zsh
# 実行権限付与
chmod +x ~/dotfiles/setup-scripts/setup-vscode.sh
# 実行
~/dotfiles/setup-scripts/setup-vscode.sh
```

# 各ファイルの解説
## zsh編
zshのセットアップに関係するファイルは以下です。
```zsh
~/dotfiles/
├── config/
│   └── zsh/   
│       ├── alias.zsh           
│       ├── bindkey.zsh         
│       ├── completion.zsh      
│       ├── env.zsh             
│       ├── functions.zsh       
│       └── oh-my-zsh.zsh       
├── setup-scripts/
│   ├── install-brew-package.sh 
│   ├── install-oh-my-zsh.sh    
│   └── setup-zsh.sh            
├── .zshenv                     
└── .zshrc                      
```

- **alias.zsh**: このファイルには、シェルでのコマンドの短縮形（エイリアス）が定義されている。例えば、alias ll='ls -la' のように書くことで、ll と入力するだけで ls -la を実行できるようになる。

- **bindkey.zsh**: このファイルには、Zshのキーバインド設定が含まれている。キーバインドを設定することで、特定のキー入力に特定のアクションを割り当てることができる。

- **completion.zsh**: このファイルでは、コマンドの補完設定を行う。Zshの補完機能をカスタマイズすることで、コマンドやファイル名の自動補完の動作を変更したり、特定のコマンドに対する補完の方法を指定したりできる。

- **env.zsh**: このファイルには、環境変数の設定が含まれている。環境変数は、システム全体やユーザーのセッションに影響を与える設定で、アプリケーションやスクリプトに渡される情報を定義する。

- **functions.zsh**: このファイルには、カスタム関数の定義が含まれている。関数を使用することで、特定のタスクを実行するための一連のコマンドをまとめ、再利用可能にすることができる。例えば、特定の作業を自動化するスクリプトを関数として定義し、コマンドラインで簡単に呼び出すことができます。

- **oh-my-zsh.zsh**: このファイルでは、Oh My Zshのプラグインやテーマの管理、Oh My Zshの初期設定を行ったりします。

- **install-brew-package.sh**: homebrewのインストールなど

- **install-oh-my-zsh.sh**: oh-my-zshのインストール

- **setup-zsh.sh**: Zshの設定ファイルをシンボリックリンクとして作成し、既存のファイルがあればバックアップする

- **.zshenv**: 全シェルで適用される設定

- **.zshrc**: config/zsh/ の中を読み込むファイル

## git編
gitのセットアップに関係するファイルは以下です。
```zsh
~/dotfiles/
├── setup-scripts/
│   └── setup-git.sh            
├── .gitconfig                  
├── .gitconfig-personal         
└── .gitconfig-work             
```

- **setup-git.sh**: gitの設定ファイルをシンボリックリンクとして作成し、既存のファイルがあればバックアップする。

- **.gitconfig**: Gitの設定ファイル

- **.gitconfig-personal**: 個人のGitの設定ファイル【ご自身で追加】

- **.gitconfig-work**: 会社のGitの設定ファイル

## VSCode編
VSCodeのセットアップに関係するファイルは以下です。
```zsh
~/dotfiles/
├── config/
│   └── vscode/   
│       ├── extensions          
│       ├── keybindings.json    
│       └── settings.json       
└── setup-scripts/
    └── setup-vscode.sh         
```

- **extensions**: インストールする拡張機能一覧

- **keybindings.json**: vscodeのキーバインド

- **settings.json**: vscodeの設定ファイル

- **setup-vscode.sh**: VSCodeの設定をdotfilesから自動的にセットアップするためのシェルスクリプト。具体的には、VSCodeの設定ファイルのシンボリックリンクを作成し、必要な拡張機能をインストール。

## Mac編
Macのセットアップに関係するファイルは以下です。
```zsh
~/dotfiles/
└── setup-scripts/
    └── setup-MacOS.sh          
```

**setup-vscode.sh**: macOSの設定を変更するためのZshスクリプト。具体的には、トラックパッドやDockに関する設定を行っている。


# まとめ

この記事では、私がどのようにしてDotfilesを構成し、セットアップを効率化しているかを紹介しました。これにより、どんな環境でも素早く自分の作業環境を再現できるようになりました。皆さんもぜひ、自分用にカスタマイズしてみてください！

# 最後に
私のdotfilesもまだまだ伸びしろがあると思います！  
ぜひおすすめの設定などがあれば<span style="color:green;">コメント</span>で教えて下さい🙇