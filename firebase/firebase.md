# firebase

- [wiki](https://en.wikipedia.org/wiki/Firebase)
- [公式](https://firebase.google.com/products/?hl=ja)

## wikiより

> - Firebase, Incが2011年に開発し、2014年にGoogleが買収した
> mobile と Web application のdevelopping platform

## Services

3つの分類
> - Development
> - Stability
> - Grow business

### Development

- Firebase Cloud Messaging

> - 無料
> - Android、iOS、ウェブなどのプラットフォーム間でメッセージを送信する
> - メッセージは、端末、特定のトピックやユーザー, セグメントに送信できる


- Firebase Auth

> - クライアント側コードのみを使用してユーザーを認証できるサービス
> - Facebook、GitHub、Twitter、Googleのソーシャルログインプロバイダをサポート
> Firebaseに格納されているEメールとパスワードのログインでユーザ認証を有効にできるユーザ管理システムも含まれる
> 独自のインターフェースを作成可能
> オープンソースの完全にカスタマイズ可能な UI を利用可能

- Realtime Database

> - リアルタイムのデータベースとバックエンドのサービス
> - クラウドでホスティングされる NoSQL データベース
> - リアルタイムにデータを保存し、ユーザーと端末の間で同期する
> - Firebaseのクラウドに格納するためのAPIを提供する
> - データの更新は接続された端末間で数ミリ秒で同期される
> - アプリがオフラインでも利用できる
> - クライアントライブラリは、Android、iOS、JavaScript、Java、Objective-C、Swift、Node.jsで利用できる
> - JavaScriptフレームワークAngular、React.js、Ember.jsでもREST APIとbindingを介してアクセス可能。
> - REST APIは、Server-Sent Eventsプロトコルを使用
> ```
> これは、サーバーからプッシュ通知を受信するためのHTTP接続を作成するためのAPIです。
> ```
> - サーバー側で実施されるセキュリティルールを使用してデータを保護することができる

- Cloud Storage

> - ネットワークの品質にかかわらず、Firebaseアプリの安全なファイルアップロードとダウンロードを提供する
> - 開発者は、これを使用して、画像、オーディオ、ビデオ、またはその他のユーザ生成コンテンツを格納することができる
> - Firebase StorageはGoogle Cloud Storageによってバックアップされています。

- Firebase Hosting

> - 静的なウェブのホスティングを簡素化する
> - 2014年5月13日に開始された静的で動的なWebホスティングサービス
> - ウェブ資産をアップロードすると、自動的にGoogleのグローバルCDNにプッシュされ、無料の SSL 証明書が付与されるため、ユーザーがどこにいても、安全で信頼性が高く、遅延の少ないサービスを提供できます。
> CSS、HTML、JavaScriptなどの静的ファイルのホスティング
> クラウド機能による動的Node.jsサポート
> このサービスは、HTTP Secure（HTTPS）およびSecure Sockets Layer（SSL）を介してコンテンツ配信ネットワーク（CDN）を介してファイルを配信します
> CDNバッファFirebase Hostingを提供するCDN Fastlyと提携しています。
> 開発者はFirebaseをリアルタイムデータベースとして使用していましたが、コンテンツをホストする場所が必要でした。

- ML Kit

> - MLキットは、Google I / O 2018のベータ版で2018年5月8日に開始された開発者向けのモバイルマシン学習システムです。
> - ML Kit APIは、文字認識、顔の検出、バーコードのスキャン、画像のラベル付け、ランドマークの認識など、さまざまな機能を備えています。
> - 現在のところ、iOSまたはAndroid開発者向け
