# NoSQL

- [Wiki](https://ja.wikipedia.org/wiki/NoSQL)

## wikiより

### 概要

> - NoSQL - Not only SQL。関係データベース管理システム (RDBMS) 以外のデータベース管理システムを指すおおまかな分類語

関係モデルではないデータストアの特徴として、
> - 固定されたスキーマに縛られない
> - 関係モデルの結合操作を利用しない
> - 水平スケーラビリティが確保しやすい事が多い
> - トランザクションを利用できないものが多い
> - 学術的な世界では、この種のデータベースのことを構造型ストレージ (structured storage) 

*水平スケール・・・本番環境に実際に接続されたサーバやコンピュータ機器の台数を増やすことで、情報システムやサービス全体としての処理性能（スケーラビリティ）を向上させることである。スケールアウトともいう。

*垂直スケール・・・サーバそのものを最新のマシンに入れ替えるなどしてスケーラビリティを向上させることは、スケールアップともいう。

NoSQL系データベース管理システムは、
> - データの格納および取得が高度に最適化されているものが多い
> - その最適化のために機能性を最小限にしているものもある
> - その最たる例が、「値」およびそれを取得するための「キー」だけを格納できるKey-Value型データベース
> - 関係データベースのような汎用性は欠くものの、 その制約された条件下ではRDBMSより高いパフォーマンスを持つ
> - そのためビッグデータ系ソリューションでしばしば活用される。

NoSQL系データベース管理システムが有用な場面は、
> - 関係モデルを必要としないデータを扱う時
> - 大量のデータを扱う時

用途は多様であり、
> - 数百万のkey-valueペアの格納
> - 数10個程度の連想配列の格納
> - 数百万の構造的データの格納

この構造は解析などに便利
> - 大規模なデータを統計的に解析
> - 増えつづける情報をリアルタイム解析

産業界での有名な実装として、
> - GoogleのBigTable
> - アマゾンのAmazon DynamoDB

オープンソースの実装も数多く存在している
> - MongoDB
> - Redis
> - Apache HBase
> - HyperTable
> - Apache Cassandraなどがある

### 歴史

> - NoSQLという用語は1998年に初めて用いられた
>   -  SQLインタフェースを持たない軽量な関係データベースのオープンソースソフトウェアの名前として
>   - その著者Carlo StrozziはNoSQL運動について、「関係モデル全体と一線を画すものであるから、『NoREL』などと名づけられるべきだった」と主張している
> - この用語は、2009年初頭にEric Evansによって再導入された
>   - この名前はMySQL、MS SQL、PostgreSQLなど関係データベースのシステムで広く用いられていた命名法を参照して付けられたものであり、非関係型の分散データストアの勃興を表現する意図が込められていた
- Eric EvansはNoSQLをNot only SQLのバクロニムとして理解するのが好ましいとしている

## アーキテクチャ

現代的な関係データベースは、
> - 小規模の高頻度なトランザクション、
> - 巨大だが書き込みをほとんど伴わないトランザクション

に最適化されて設計されているため、
> 近年必要とされてきている大規模データに基づく (data-intensive) 応用事例では性能が劣化してしまう。
 
> そのような応用の例として、
> - 検索のための文書のインデキシング
> - トラフィックの高いウェブサイトのサーバ
> - ストリーミングデータの配布などがあり
> - Diggのgreen badge、Facebookのインボックスの検索、eBayのシステム全体などがその実例である

NoSQLのアーキテクチャにおいては、
> - 結果整合性のみを保証するなどして一貫性の保証を弱く設計したり
> - トランザクションをひとつのデータアイテムに限るという制限を設けたりすることが多い
> - 補助的なミドルウェアの層を付加することによって完全なACID保証を提供している場合もある

いくつかのNoSQLシステムは分散アーキテクチャを採用している
そのようなシステムでは、
> - 多くの場合は分散ハッシュテーブルを用いて
> - データを複数のサーバに冗長性を持たせながら配置する
> - これにより、サーバを追加するだけでシステムを容易にスケールアップさせることができ、
> - 障害への耐性も強くなる

## データモデル
NoSQLのデータモデルには大別して次の4つがあります。

キー・バリュー型
> - Key : Valueを単位としてデータを格納する。
> - シンプルで応答が早い

カラム志向型
> - 一般の行志向型DBと同様に表の構造を持ちつつ
> - カラム単位でデータを保持する
> - 行志向では苦手な列単位の大量集計、大量更新が得意

グラフ型
> - ノード、リレーションシップ、プロパティによって定まるデータを単位とし、
> - 全体でグラフを形成する
> - Facebookの知り合い機能等で有効に利用できる

ドキュメント志向型
> - JSONやXMLのような構造を持ったドキュメントを単位としてデータを格納する
> - スキーマレスで格納できる。
