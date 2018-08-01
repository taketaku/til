# Babel is a JavaScript compiler.
- [公式](https://babeljs.io/)
- [Wiki](https://en.wikipedia.org/wiki/Babel_(compiler))

wiki(原文)
```
Babel or Babel.js is a free and open-source JavaScript compiler and configurable transpiler used in web development. Babel allows software developers to write source code in a preferred programming language or markup language and have it translated by Babel into JavaScript, a language understood by modern web browsers.

Babel is popular tool for using the newest features of the JavaScript programming language.[3] As a transpiler, or source-to-source compiler, developers can program using new ECMAScript 6 (ES6) language features by using Babel to convert their source code into versions of JavaScript that evolving browsers are able to process.[4] The core version of Babel is downloaded 5 million times a month.[5]

Babel plugins are available to provide specific conversions used in web development. For example, developers working with React.js, can use Babel to convert JSX (JavaScript XML) markup into JavaScript using the Babel preset "react".
```

wiki(訳)
```
BabelまたはBabel.jsは、Web開発で使用される無料のオープンソースのJavaScriptコンパイラと設定可能なトランスヒーラーです。 Babelは、ソフトウェア開発者がソースコードを好みのプログラミング言語やマークアップ言語で記述し、BabelによってJavaScript（現代のWebブラウザで理解できる言語）に変換することを可能にします。

Babelは、JavaScriptプログラミング言語の最新機能を使用するための一般的なツールです。[3] Transilerやソースソースコンパイラとして、開発者はBabelを使用してソースコードをブラウザが処理できるJavaScriptのバージョンに変換することにより、新しいECMAScript 6（ES6）言語機能を使用してプログラムすることができます。バベルのコアバージョンは月に500万回ダウンロードされている[5]

Babelプラグインは、Web開発で使用される特定の変換を提供するために利用できます。たとえば、React.jsを使用している開発者は、Babelプリセット「react」を使用してBabelを使用してJSX（JavaScript XML）マークアップをJavaScriptに変換できます。
```
Babelは、
- Web開発で使用される無料のオープンソースのJavaScriptコンパイラ
- 好みのプログラミング言語やマークアップ言語で記述したものを、JavaScriptに変換することができる
- JavaScriptの最新機能を使用するための一般的なツール
```
開発者はBabelを使用してソースコードをプラウザが処理できるJavaScriptのバージョンに偏見することにより、新しいES６言語機能を使用してプログラムすることができる
```
Babelプラグインは、
- 特定の変換を提供するために利用できる
```
プリセット「react」を利用することでJAXマークアップをJavascriptに変換できる
```

## BabelとWebpack
[参考](https://ics.media/entry/16028)
```
トランスパイラとして一番有名なのが「Babel」というツールです。ただ、BabelにはECMAScript Modules（importやexport文のこと。以下、ES Modulesと記載）のJSファイルをまとめる機能が提供されていません。そのため、ES ModulesのJSファイルをまとめるモジュールバンドラー（例：webpack、Rollup等）をBabelと合わせて使うのが一般的です。
```
- Babelはトランスパイラ
- Webpackはモジュールバンドラー
- ２つを合わせて使うのが一般的

### 使い方例

- webpack + Babel + jQueryの構成
- webpack + Babel + Reactの構成
- webpack + Babel + Three.jsの構成
- webpack + Babel + Vue.jsの構成
- ECMAScript 2018仕様を使う方法

#### シンプルな方法

> npm install -D webpack webpack-cli babel-core babel-loader babel-preset-env

webpack.config.js
```
module.exports = {
  // モード値を production に設定すると最適化された状態で、
  // development に設定するとソースマップ有効でJSファイルが出力される
  mode: 'development',
 
  // メインとなるJavaScriptファイル（エントリーポイント）
  entry: './src/app.js',
 
  module: {
    rules: [
      {
        // 拡張子 .js の場合
        test: /\.js$/,
        use: [
          {
            // Babel を利用する
            loader: 'babel-loader',
            // Babel のオプションを指定する
            options: {
              presets: [
                // env を指定することで、ES2018 を ES5 に変換。
                // {modules: false}にしないと import 文が Babel によって
                // CommonJS に変換され、
                // webpack の Tree Shaking 機能が使えない
                ['env', {'modules': false}]
              ]
            }
          }
        ]
      }
    ]
  }
};

```

> ※プリセット「babel-preset-env」は「ECMAScript 5/6/7 compatibility tables」に基づきターゲットブラウザを指定できたりと様々な機能が提供されています。例えば、ターゲットブラウザがSafari 10だけでよければ、ES5まで落として変換する必要はなく、ES2015(ES6)をターゲットにすれば良いということになります。


npm run buildコマンドを入力すると、srcフォルダに配置したJSファイルがトランスパイルされ、distフォルダにmain.jsファイルが出力されます。

#### webpack + Babel + Reactの構成

> npm install -D webpack webpack-cli babel-core babel-loader babel-preset-env babel-preset-react

> npm install react react-dom

webpack.config.js
```
module.exports = {
  // モード値を production に設定すると最適化された状態で、
  // development に設定するとソースマップ有効でJSファイルが出力される
  mode: 'development',
 
  // メインとなるJavaScriptファイル（エントリーポイント）
  entry: './src/main.js',
  // ファイルの出力設定
  output: {
    //  出力ファイルのディレクトリ名
    path: `${__dirname}/dist`,
    // 出力ファイル名
    filename: 'main.js'
  },
  module: {
    rules: [
      {
        // 拡張子 .js の場合
        test: /\.js$/,
        use: [
          {
            // Babel を利用する
            loader: 'babel-loader',
            // Babel のオプションを指定する
            options: {
              presets: [
                // env を指定することで、ES2018 を ES5 に変換。
                // {modules: false}にしないと import 文が Babel によって CommonJS に変換され、
                // webpack の Tree Shaking 機能が使えない
                ['env', {'modules': false}],
                // React の JSX を解釈
                'react'
              ]
            }
          }
        ]
      }
    ]
  }
};

```

#### webpack + Babel + Vue.jsの構成

> vue-cliを使うのが最も簡単ですが、vue-cliはwebpack 3をベースにしているため、少し環境設定が古めです。この解説ではwebpack4とBabelとVue.jsを最小構成で作っていきます。

> npm i -D babel-core babel-loader babel-preset-env css-loader file-loader vue-loader vue-template-compiler webpack webpack-cli

> npm i vue

Webpack.config.js
```
const { VueLoaderPlugin } = require('vue-loader');
 
module.exports = {
  // モード値を production に設定すると最適化された状態で、
  // development に設定するとソースマップ有効でJSファイルが出力される
  mode: 'production',
 
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          'vue-style-loader',
          'css-loader'
        ],
      },
 
      {
        test: /\.vue$/,
        loader: 'vue-loader'
      },
      {
        test: /\.js$/,
        loader: 'babel-loader',
        // Babel のオプションを指定する
        options: {
          presets: [
            // env を指定することで、ES2018 を ES5 に変換。
            // {modules: false}にしないと import 文が Babel によって CommonJS に変換され、
            // webpack の Tree Shaking 機能が使えない
            ['env', {'modules': false}]
          ]
        }
      },
    ]
  },
  // import 文で .ts ファイルを解決するため
  resolve: {
    // Webpackで利用するときの設定
    alias: {
      'vue$': 'vue/dist/vue.esm.js'
    },
    extensions: ['*', '.js', '.vue', '.json']
  },
  plugins: [
    // Vueを読み込めるようにするため
    new VueLoaderPlugin(),
  ],
};

```

#### webpack+ECMAScript 2018

- Babelはアロー関数やクラス、letやconstといった新しい構文を下位バージョンに変換します
- PromiseやArray.includes()といった機能までは変換しません

```
Babel - 最新のEcmaScriptの構文wお下位のEcmaScriptに変換する。class, アロー関数,
        let/const, テンプレート構文
Babel-polyfil - 最新のEcmaScriptの構文をエミュレートするポリフィル。構文ではない機能的な仕様を使えるようにする。Promise, WeakMap, Array.prototype.includes, Array.from, Object.assign
```
エミュレータ・・・機械を真似る機械。る機械部品やソフトウェアを動作させるのに、オリジナルのシステムを用意するのが難しい場合に、オリジナルと全く同じ動作をするより簡便なシステムを用意することがある。この装置をエミュレータと言う。エミュレータの上で、動作させたいソフトウェアや機械部品をオリジナルと全く同じように機能させられる。機械装置やハードウェアだけでエミュレータを作成したり、ソフトだけで作成したり、あるいはその両方を同時に使う。

エミュレート・・・語源は英語の"emulate"（エミュレート：模倣する・真似をする）からきており、そのとおり異なるハードウェアやソフトウェア環境を模倣・物真似をさせる技術である。模倣対象のシステムを近似や推論でモデル化する場合をシミュレート（simulate）と言う。

ポリフィル・・・古いブラウザーに欠けている部分、新しいブラウザーでも足りない機能の穴を埋めることを、ポリフィル (polyfill) という風に呼ばれています

> npm install -D webpack webpack-cli babel-core babel-loader babel-preset-env babel-polyfill

```
module.exports = {
  // モード値を production に設定すると最適化された状態で、
  // development に設定するとソースマップ有効でJSファイルが出力される
  mode: 'production',
 
  // メインとなるJavaScriptファイル（エントリーポイント）
  entry: [
    'babel-polyfill', // Polyfillも含める
    './src/app.js',
  ],
  // ファイルの出力設定
  output: {
    // 出力ファイルのディレクトリ名
    path: `${__dirname}/dist`,
    // 出力ファイル名
    filename: 'main.js'
  },
 
  module: {
    rules: [
      {
        // 拡張子 .js の場合
        test: /\.js$/,
        use: [
          {
            // Babel を利用する
            loader: 'babel-loader',
            // Babel のオプションを指定する
            options: {
              presets: [
                // env を指定することで、ES2018 を ES5 に変換。
                // {modules: false}にしないと import 文が Babel によって CommonJS に変換され、
                // webpack の Tree Shaking 機能が使えない
                ['env', {'modules': false}]
              ]
            }
          }
        ]
      }
    ]
  }
};
```