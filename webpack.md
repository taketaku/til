## 資料
- [公式](https://webpack.js.org/)
- [Wiki](https://en.wikipedia.org/wiki/Webpack)
- [what is webpack · webpack/docs Wiki · GitHub](https://github.com/webpack/docs/wiki/what-is-webpack)

## 概要
Wiki(原文)
```
Webpack is an open-source JavaScript module bundler. Webpack takes modules with dependencies and generates static assets representing those modules.[2] It takes the dependencies and generates a dependency graph allowing web developers to use a modular approach for their web application development purposes. The bundler can be used from the command line, or can be configured using a config file which is named webpack.config.js.[3]

Node.js is required for installing webpack. Another important aspect about webpack is that it is highly extensible by the use of loaders. Loaders allow developers to write custom tasks that they want to perform when bundling files together.

Webpack provides code on demand using the moniker code splitting. The Technical Committee 39 for ECMAScript is working on standardization of a function that loads additional code: proposal-dynamic-import
```
Wiki(訳)
```
WebpackはオープンソースのJavaScriptモジュールバンドラです。 Webpackは依存関係のあるモジュールを取り出し、それらのモジュールを表す静的資産を生成します。[2] それは依存関係を取り、依存関係グラフを生成し、Web開発者がWebアプリケーションの開発目的にモジュラーアプローチを使用できるようにします。 バンドラは、コマンドラインから使用することも、webpack.config.jsという名前の設定ファイルを使用して設定することもできます。[3]

webpackのインストールにはNode.jsが必要です。 Webpackに関するもう1つの重要な側面は、ローダーを使用することによって高度に拡張可能であることです。 ローダーを使用すると、開発者はファイルをバンドルするときに実行するカスタムタスクを記述できます。

Webpackは、モニカコード分割を使用してオンデマンドでコードを提供します。 ECMAScriptの技術委員会39は、追加のコードをロードする関数の標準化に取り組んでいます：proposal-dynamic-import
```
Webpackは
- Javascriptによるオープンソースのmodule bundler
- 依存関係にあるmoduleを取り出し、性的なassetsを生成する
- コマンドラインから使用できる
- webpack.config.js（設定ファイル）を利用して設定することができる
- インストールにはNode.jsが必要
- Loaderを使うことで高度に拡張できる
- Loaderを使用することで、ファイルをbundleするときに実行するカスタムタスクを記述できる

## Webpack3 から 4への変更点

- Node4のサポートがなくなった [- Node.js versions](https://nodejs.org/ja/download/releases/)
- cliが別パッケージ(webpack-cli)に移行した
- Mode optionの追加(production, development, none)
```
webpack --mode production
```
すべての種類の最適化を行ったバンドルファイルが生成される。
watch modeは起動しない

有効化される機能
- performance
    - hints: warning
- optimization
    - flagIncludedChunks
    - occurrenceOrde
    - sideEffects
    - usedExports
    - concatenateModules
    - noEmitOnErrors
    - minimize

```
webpack --mode development
```

有効化される機能
- performance
    - hints: warning
optimization
    - flagIncludedChunks
    - occurrenceOrde
    - sideEffects
    - usedExports
    - concatenateModules
    - noEmitOnErrors
    - minimize

```
webpack --mode none
```
すべての設定無効