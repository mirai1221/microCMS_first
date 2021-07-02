## ディレクトリ構成について

公式(https://ja.nuxtjs.org/docs/2.x/get-started/directory-structure/)

### 公式の補足

- layouts(header や footer などグローバルなコンポーネント設置場所)
- dist(本番用のファイル設置場所)
- instance(middleWare 起動時のインスタンス)
- functions(恐らく middleWare のようなもの)

## package json command について

```js
  "scripts": {
    "dev": "nuxt",
    "generate": "nuxt generate --fail-on-error",
    "start": "nuxt start",
    "lint": "eslint --ext .js,.vue --ignore-path .gitignore .",
    "lintfix": "eslint --fix --ext .js,.vue --ignore-path .gitignore .",
    "functions:build": "netlify-lambda build functions",
    "functions:serve": "netlify-lambda serve functions"
  }
```

[公式サイト](https://ja.nuxtjs.org/docs/2.x/get-started/commands/)

nuxt configのtarget設定によって挙動が異なる。  
今回は `target: static`

- `nuxt dev` - 開発サーバーを起動します。
- `nuxt generate` -（必要に応じて）アプリケーションをビルドし、すべてのルートを HTML ファイルとして生成し、dist/ ディレクトリに静的にエクスポートします（静的ホスティングに使用されます）。
- `nuxt start` - 静的ホスティング（Netlify、Vercel、Surge など）と同じように dist/ ディレクトリを提供します。デプロイ前のテストに最適です。
- `functions:hoge` - netlify lambda を使用する時のコマンド。2種類は開発用と本番用

lintはlint関連のことで今回は使わないので省略。