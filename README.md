# gulp_sass_pug_es6_flocss-template

htmlとcssおよび開発環境は、gulpを利用。jsはparcelを利用しています。

## Usage

### インストール
` npm install ` or `yarn`

### コマンド

コマンドはnpm scripts（npm run all）を利用。

- 開発用コマンド `npm run dev`
  - `_dev`に出力
- 出力用コマンド `npm run build`
  - `_dist`に出力
- 削除用コマンド `npm run clean`
  - `_dev`と`_dist`のファイルをすべて削除

- 開発は_srcディレクトリの中で行います。

### ディレクトリ構成

- `_dist` **変更不可** リリース用出力ファイル
  - git管理対象
- `_dev` **変更不可** 開発用確認出力ファイル
- `_src` 開発用ファイル
  - git管理対象

### FLOU
- scss ディレクトリはFLOCSSをベースにしたFLOUで構成しています。
  - foundation
  - layout
  - object
  - utility
  - [FLOUについて](https://webnaut.jp/technology/20170407-2421/)
  - [FLOCSSについて](https://github.com/hiloki/flocss)

- Foundation
  - リセットCSS、NormarizeCSSなどの、すべてのベースとなるCSS
  - npmで追加したパッケージのCSSも読み込む
  - `sass/foundation/`に記述
- Layout
  - パーツの配置や、ラッパーとしての幅や高さなどを決定するクラス
  - 接頭辞として`l-`をつける
  - `sass/layout/`に記述
- Object
  - ページをまたいで使われる各種パーツを定義するクラス
  - そのパーツ内で常に同様の振る舞いをするものに関してのみスタイルを定義
  - jsでclassを追加する場合は、`is-xx`という形で統一する
  - `sass/object/`に記述
- Utility
  - 調整用のクラス
  - margin、padding、font-size、colorなどを付与するのに使用
  - 他種類のパーツ間の空き調整や、パーツとして認められないような、自由な振る舞いをする要素に対してはこちらのクラスを使用
  - 接頭辞として`u-`をつける
  - `sass/utility/`に記述

## できること
- gulpを用いたタスクランナー機能
  - ブラウザー自動更新
    - browser-sync
    - browsersync-ssi
  - pugを用いたHTML作成
    - gulp-pug
  - sass
    - gulp-sass
    - gulp-sourcemaps
    - gulp-autoprefixer
    - gulp-group-css-media-queries
    - gulp-sass-glob
- parcelを用いたes6開発

## 依存アプリケーション等
- gulp
- sass
- pug
- parcel
- flocss

## Link

### BEM
- https://docs.emmet.io/filters/bem/
### Pug
- https://necosystem.hirokihomma.com/archives/121/