# Swagger
- [wiki](https://en.wikipedia.org/wiki/Swagger_(software))
- [公式](https://swagger.io/tools/open-source/)

> - オープンソースのソフトウェアフレームワーク
> - RESTfulなWebサービスの使用、デザイン、構築、文書化に役立つ
> - ほとんどのユーザーはSwagger UIツールでSwaggerを識別するが 
> - Swaggerツールセットには自動化されたドキュメント、コード生成、テストケース生成のサポートが含まれている
> - SmartBear Softwareがサポートしている

Swaggerの実体は、
- Swagger Spec
```
YAMLやJSON形式で定義されるドキュメント仕様
```

- Swagger Core
```
API実装コードからSwagger Specで記載された設計を自動生成
```
- Swagger Editor
```
Swagger Specの設計書を記載するためのエディタ
```
- Swagger UI
```
Swagger Specで記載された設計からドキュメントを自動生成
```
- Swagger Codegen
```
Swagger Specで記載された設計からAPIのスタブを自動生成
```

## それは何で問題意識はなにか、それをどう解決しているか
Swaggerは、
- API設計のツール群で
- APIのフォーマットも標準化する

問題意識は、
- APIの仕様書と実際との乖離の問題
- 管理メンテンナンス及び開発のコストの問題

それをどう解決しているか、
Swagger Specを書くことで、
- 自動でAPI仕様ドキュメントを生成
- 記載された設計からAPIのスタブを自動生成