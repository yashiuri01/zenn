---
title: "ZennとGitHubを連携してローカルからZennに投稿する"
emoji: 🚀
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Zenn", "GitHub",]
published: true
---

## ZennとGitHubの連携

1. Zenn用のリポジトリをGitHubで作成する
2. [ZennのGitHub連携](https://zenn.dev/dashboard/deploys)から作成したリポジトリをGitHub連携する


## npmのインストール(Optional)
Zenn CLIをインストールするためにはnpmが必要。
- npmが導入されていない場合
  - 下記の手順を実施
- npmが購入されている場合
  - この項目はスキップ

```shell
# Homebrewからnodebrewをインストール
$ brew install nodebrew
$ nodebrew setup

# PATHを登録
$ echo 'export PATH=$HOME/.nodebrew/current/bin:$PATH' >> ~/.zshrc
$ source ~/.zshrc

# インストールバージョンを確認
$ nodebrew ls-remote
# 最新版をインストール
$ nodebrew install latest
# バージョン確認
$ nodebrew list
# バージョン指定
$ nodebrew use <version>
# 設定確認
node -v
npm -v
```

## Zenn CLIのインストール

```shell
$ npm -v

$ cd <GitHub Repository Path>
$ npm init --yes
$ npm install zenn-cli
$ npm install zenn-cli@latest
$ npx zenn init
```


## 初めての記事をZenn CLIから投稿する

1. テンプレートファイルを作成する。
```shell
$ npx zenn new:article --slug zenn-<Github User Name>-`date +%Y%m%d`
```

2. 中身を編集する。以下は必ず編集しないと公開設定とならない。
```yml
- published: false
+ published: true
```

3. 記事のプレビューをする。
```shell
$ npx zenn preview
```
ブラウザで http://localhost:8000 にアクセスする。


4. GitHubのリポジトリに記事をpushする。

5. Well Done!


## 参考
https://zenn.dev/zenn/articles/connect-to-github  
https://zenn.dev/zenn/articles/install-zenn-cli  
https://zenn.dev/zenn/articles/zenn-cli-guide  
