# Firebase Authentication

- [ドキュメント](https://firebase.google.com/docs/auth/?hl=ja)

## 概要
ほとんどのアプリでは、ユーザー ID を識別する必要があります。
アプリでユーザー ID を識別することにより、
> - ユーザーデータをクラウドに安全に保存したり
> - ユーザーのすべての端末で、カスタマイズされた同じ体験を提供したりできる

Firebase Authentication は、
> - バックエンドサービス、SDK、ユーザー認証に使用できるUIライブラリが利用できる
> - パスワード、電話番号、一般的なフェデレーション, IDプロバイダ（Google、Facebook、Twitter）などを使用した認証を行うことができる
> - 他のFirebaseサービスと緊密に統合されている
> - OAuth 2.0 や OpenID Connect などの業界標準を使用しているため、カスタムバックエンドと簡単に統合できる

## 主な機能

2つの使用方法がある
- FirebaseUI - 完全なドロップイン認証ソリューション
- Firebase Authentication SDK - 複数のログイン方法を手動でアプリに統合する

### FirebaseUI Auth

> - オープンソース
> - 完全なログイン システムをアプリに追加する推奨される方法
> - 備わっているドロップイン認証ソリューションは、メールアドレスとパスワード、電話番号を使用したり、Google ログインや Facebook ログインなどの一般的なフェデレーション ID プロバイダを使用してユーザーをログインさせるための UI フローを処理する
> - FirebaseUI Auth コンポーネントには、モバイル端末やウェブサイトで、アプリのログインや登録のコンバージョンを最大限に高めるために使用できる、おすすめの方法が導入されています
> - セキュリティの侵害や処理でのミスが起こりやすいエッジケースにも対応している
> - FirebaseUIは、アプリの他の部分の表示スタイルに合うように簡単にカスタマイズできる

### Firebase SDK Authentication

メールとパスワードに基づく認証
> - メールアドレスとパスワードを使用してユーザーを認証する
> - メールアドレスとパスワードを使用してログインするユーザーを作成して管理するための方法が用意されてる。
> - パスワードの再設定メールを送信することもできる

フェデレーション ID プロバイダとの統合
> - フェデレーションIDプロバイダと統合することで、ユーザーを認証する
> - ユーザーが Google、Facebook、Twitter、GitHubアカウントを使用してログインできる方法が用意されてる

電話番号認証
> - スマートフォンに SMS メッセージを送信してユーザーを認証する

カスタム認証システムとの統合
> - アプリの既存のログイン システムをFirebase Authentication SDK に接続して、Firebase Realtime DatabaseなどのFirebaseサービスにアクセスできるようにする

匿名認証
> - 一時的な匿名アカウントを作成することで、ユーザーにログインを要求することなく認証できる
> - ユーザーが後から登録することにした場合は、匿名アカウントを通常のアカウントにアップグレードして、ユーザーが前回終了したところから操作を続行できるようにすることができる


### 仕組み
アプリへのユーザーのログインを行うには、
> 1. ユーザーから認証情報を取得する
> ```
> ユーザーのメールアドレスとパスワードや、フェデレーション ID プロバイダの OAuth トークンなど
> ```
> 2. 取得した認証情報を Firebase Authentication SDK に渡す
> 3. Googleのバックエンドサービスによって認証情報が検証され、クライアントに応答が返される
> 4. ログインが成功すると、ユーザーの基本的なプロフィール情報にアクセスしたり、他の Firebase サービスに保存されているデータへのユーザーのアクセスを制御したりできます。
