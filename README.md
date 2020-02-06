# 【課題】Vue.jsとTypeScriptで実装するTodoリスト

### **※開発はこのリポジトリを自分のGitHubにForkしてから開発を進めてください**。

## 目標
ProgateのHTML、JavaScript、CSSを一通り学んだ後に、JavaScriptのフレームワークを用いて

- Create（生成）
- Read（読み取り)
- Update（更新）
- Delete（削除）

**CRUD機能**を実装し、実務に近い開発スキルを身につける。
また、GitHub issuesを使用して、実装イメージを組み立ててから実装できるようになる。

## アプリの要件
- inputフォームと追加ボタンでより新しいTodoを追加できる
- 追加したTodoを1つ選んで削除できる
- Todoをリストで複数表示できる（配列でTodoを追加し、それを表示します）
- 追加したTodoを1つ選んで内容を更新できる

**※デザインは自由にしてOKです。**

##  使用技術
- Vue.js ※Vuexは使用せずに実装をしてください。
- TypeScript
- SCSS

 GitHubを使用してコードを共有頂きます。同時にGitHubの使い方を学ぶため、GitHub issuesにissueを立てた上で実装していただきます。質問もissueを経由して行っていただきます。

 機能ごとにbranchを切り、Pull Requestを使ってmaster branchにマージをします。

 その際、レビューを行いますので私のOKが出たらマージをしてください。

 その他GitHubの作法に関してはこちらをご覧ください。（随時質問してください！）


## 開発環境
- 動作確認環境はMac OSです
- Windowsの方でも問題なく開発に入れるかと思います。(もしうまく行かないことがありましたらSlackに直接ご連絡ください。)
- Node.js(12.4.1は確認済み)がインストールされた環境が必要です。
### Macの場合
  - ターミナル(コマンドプロンプト)を開きます。
  - nodebrewというNode.jsのバージョン管理ツールを使い、インストールします。
  - Macにbrewをインストール `$ brew install nodebrew`
  - `$ nodebrew --version` バージョンが確認できればOKです。
  - 設定ファイルを作成。`$ vi ~/.bash_profile`
  - 右記を追記。 `$ export PATH=$HOME/.nodebrew/current/bin:$PATH`
  - `$ source ~/.bash_profile` で設定を読み込ませます。
  - `$ nodebrew install-binary 12.4.1` 安定版をダウンロードします。
  - `$ nodebrew use 12.4.1` ダウンロードした安定版を使用します。
  - `$ node -v` ここでバージョン`12.4.1`が確認できればOKです。

### Windowsの場合
以下の記事に沿って環境を整えてください。
https://qiita.com/Futo23/items/0825aa96088c5ff0906b

## GitHubの使い方
### GitHubってなに？
ソフトウェア開発のプラットフォームソフトウェア開発のプラットフォームです。<br>
コードのバージョン管理システムにはGitを使用しています。
実務では必ず使用します！使いこなせるようになりましょう！

### 課題ではどのように使うの？
#### ①自分のGitHubアカウントにForkをする。
右上のForkボタンを押すと自分のアカウントにForkができます。

<img width="1046" alt="Screen Shot 2020-02-07 at 00 45 24" src="https://user-images.githubusercontent.com/13050604/73959819-4197d380-494d-11ea-8cd0-5c6657603ae6.png">

### ②ローカル環境にcloneする。
cloneする際は**Use SSH**が選択されていることを確認してください。

<img width="414" alt="Screen Shot 2020-02-07 at 02 01 28" src="https://user-images.githubusercontent.com/13050604/73960223-d26eaf00-494d-11ea-8eb8-17774cd4019d.png">

ここからはターミナル(コマンドプロンプト)を使用します。
URLをコピーし、開発用のディレクトリ(ここは任意の場所ですが仮に`study`とします)を作ります。(例: `$ mkdir study`)
ディレクトリを移動したらcloneします。 `$ git clone コピーしたURL`

### パッケージマネージャを使って開発に必要なパッケージをインストールする。
パッケージマネージャには`npm`と`yarn`がありますが。今回は`yarn`を使用します。


ローカル環境にcloneできたら、`$ cd vue-sample-todo-app`でディレクトリを移動し、`$ yarn install`で開発に必要なパッケージをインストールします。この際、`$ yarn`と省略も可能です。

実際に`$ yarn serve`でローカルサーバを起動し、ブラウザで`localhost:8080`にアクセスし

<img width="443" alt="Screen Shot 2020-02-07 at 01 52 13" src="https://user-images.githubusercontent.com/13050604/73959758-2c22a980-494d-11ea-955b-5aeecb30d23a.png">

画像のような画面が表示されれば開発環境の構築は終了です。

## その他
 分からない用語やVue.jsの作法はググることで解決を目指しましょう！
（なるべく公式ドキュメント。Vue.jsは日本語で書かれているのでオススメ）

 15分調べて分からない場合は、質問大歓迎です！

## リンク集
 - Vue.js 公式ドキュメント https://jp.vuejs.org/v2/guide/index.html
 - GitHubの使い方 https://qiita.com/nnahito/items/565f8755e70c51532459
 - レポジトリ https://github.com/watsuyo/vue-sample-todo-app


## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### Compiles and minifies for production
```
yarn run build
```

### Run your tests
```
yarn run test
```

### Lints and fixes files
```
yarn run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
