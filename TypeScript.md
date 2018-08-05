# TypeScript

- [wiki](https://ja.wikipedia.org/wiki/TypeScript)
- [公式](https://www.typescriptlang.org/)
- [ドットインストール](https://dotinstall.com/lessons/basic_typescript)

## 概要

-　マイクロソフトによって開発された
- オープンソースのプログラミング言語
- javascriptに省略可能な性的型付けとクラスベースオブジェクト指向を加えた上位互換
- クライアントサイド、サーバーサイドで実行されるJavaScriptアプリケーションの開発で利用できる
- 大規模なアプリケーションのために設計されている
- 上位互換のため、すべての既存のJavaScriptプログラムはすべて有効なTypeScriptプログラムとなる
-  型定義ファイルをサポートしており、既存のJavaScriptライブラリに型情報を付与して利用できる
```
その型定義ファイル内で定義された値を、他のプログラムがあたかも静的に型付けされたTypeScriptエンティティであるかのように利用することができるようになる
```
- JavaScriptへのトランスコンパイラでもある

## 特徴
TypeScriptは、
- ES5を拡張したもの
- ES6由来の機能を有している
```
- クラス
- アロー関数式（ラムダ式）
- オプション引数、デフォルト引数
- let, const
- テンプレート文字列 : 文字列内への変数埋め込み
- モジュール[26]
- for/of
- 分割代入
- Symbol
```
- ES7由来の機能を有している
```
- デコレーター
- Async/Await
```
- 独自の実装を有している
```
型注釈（変数、引数、戻り値などの型宣言）とコンパイル時の型チェック
型推論、型ガード - if文の instanceof などを利用した型推論
インタフェース
列挙型
Mixin
ジェネリック
名前空間
タプル型
和型（英語版）, 交差型（英語版）
型エイリアス
```

## JavaScriptとの互換性
- TypeScriptプログラムはJavaScriptを境目なしに利用できる
- デフォルト設定の場合、コンパイラはECMAScript 3を出力
- オプションによりECMAScript 3から最新のECMAScriptまでの間で出力対象を選択することができる
- 既存のJavaScriptコードを使うことができる
- JavaScriptからTypeScriptで作られたコードを呼ぶこともできる

TypeScript はECMAScript 2015の厳密なスーパーセットであり、ECMAScript 2015はECMAScript 5(一般的にJavaScriptと呼ばれているもの)のスーパーセットである[27]。従って、JavaScriptプログラムは有効なTypeScriptプログラムでもあるので、TypeScriptプログラムはJavaScriptを境目なしに利用できる。

デフォルト設定の場合、コンパイラはECMAScript 3を出力するが、オプションによりECMAScript 3から最新のECMAScriptまでの間で出力対象を選択することができる。

TypeScriptでは、既存のJavaScriptコードを使うことができる。つまり、人気のあるJavaScriptライブラリを取り入れることができ、他のJavaScriptからTypeScriptで作られたコードを呼ぶこともできる[28]。これらの外部ライブラリに対する型宣言は、DefinitelyTyped（後述）に収録されていればnpmを用いて簡単にインストールすることができる[

## 型アノテーション

```
function add(left: number, right: number): number {
	return left + right;
}
```
TypeScriptは
- コンパイル時における型検査を可能にするために、型アノーテーションによる静的型付けの仕組みを提供している
- この仕組みの利用は任意(動的型付けを使うこともできる)
- プリミティブ型のためのアノーテーションはnumber、boolean、stringである。弱い型付けあるいは動的型付けにする場合は、any型を用いる
- 既にJavaScriptにコンパイルされた型を使うTypeScriptスクリプトから型情報を利用できるようにするために、型アノーテーションは別個の「宣言ファイル」に外出しすることが出来る

型が与えられていない場合、TypeScriptコンパイラは型を推論するために型推論を使う。例えば、上のコードにおけるadd メソッドは、もし戻り値型が何も与えられていなかったとしても、number型を返すと推論される。これは引数leftとrightが number型であること、および「二つのnumber型を加算した結果は常にnumber型である」というコンパイラ側の知識に基づいている。しかし、明示的に戻り値型を指定しておけば、コンパイラがその正しさを検証してくれる

宣言の不足により型推論が不可能な場合、動的なany型がデフォルトで使われる。any型の値に対する操作は、JavaScriptと同様の操作をサポートしているので、any型に対する操作については最低限の静的型検査が行われるだけである

## 型宣言ファイル
TypeScriptをコンパイルするとき、「型宣言ファイル」を生成するオプションがある
型宣言ファイルは、
- ファイル拡張子は .d.ts
- コンパイルされてできたJavaScript内のコンポーネントへのインタフェースの役割を果たす
- コンパイラは、型宣言ファイルの作成過程で、関数やメソッドのコードの中身はすべて除去し、出力される型のシグネチャだけを残す
```
declare module arithmetics {
    add(left: number, right: number): number;
    subtract(left: number, right: number): number;
    multiply(left: number, right: number): number;
    divide(left: number, right: number): number;
}
```
- 出力されたJavaScriptライブラリまたはモジュールの仮想的なTypeScript型が記述してあり、第三者がTypeScriptを書くとき、この型宣言ファイルを読み込んで使うことが出来る
- 既存のJavaScriptライブラリのための型宣言ファイルは、手書きで書くこともできる


