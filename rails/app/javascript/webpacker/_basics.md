# Webpacker

## webpackとWebpackerは別もの？
結論言うと、別もの。

### webpackとは
- npmパッケージで、`webpack`コマンドと`webpack.config.js`の設定ファイルでJSのコンパイルや圧縮などを行う。

- 昨今のフロントエンド開発では、このwebpackを使ってJSファイルを一つに結合してリソース用のファイルを作成している。

### Webpackerとは
- webpackをRailsから利用するためのツール。
- Rails 5.1からはオプションで、Rails 6.0からはデフォルトに変更されている。

### 設定ファイル
webpackでは、`webpack.config.js`だが、Webpackerでは主に以下のファイル

- config/webpacker.yml
- config/webpack/development.js
- config/webpack/environment.js
- config/webpack/production.js
- config/webpack/test.js

## Webpackerによる自動ビルド
- 特に意識せずにJSのビルドが実行される。
  - もう少し詳しく言うと、`javascript_pack_tag`メソッド実行時に対象となるファイルの更新有無をチェックしている。

- そのためJS更新後の初回アクセス時に、HTML生成のタイミングでJSのビルドが実行されるので、ビルド待ちの時間が発生する。

## `$ bin/webpack-dev-server`で自動ビルドが良い
- `$ bin/webpack-dev-server`で自動ビルドすると、webpack管理下のファイルの更新を検知し、すぐにビルドしてくれる。

ビルド対象が多い時は、
- `$ bin/webpack-dev-server`で起動しておき
- 別途 `$ rails s`でRailsを起動しておくと、JSをあらかじめビルドしておく状態にできる。

### Webpacker::DevServerProxyミドルウェアのおかげ
- Webpacker管理下のパス(/packs)配下にアクセスした場合、webpack-dev-server の起動確認をする
- 起動していたら、webpack-dev-server へ委譲する
- 起動していない場合、`public/packs`配下のファイルを返す
