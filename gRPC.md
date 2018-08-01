## 概要

### RPC

- Remote Procedure Callの略
```
Remote - 遠隔
Procedure - 手続き。処理のまとまり
Call - 呼び出し
```

- プログラムから別のアドレス空間（ネットワーク越しのコンピュータ）にあるプログラムを実行する技術
- 通信する構造化データはシリアライズ(バイト列の変換)が必要

エンコードの種類によって以下のものがある
```
JSON-RPC
XML-RPC
Java RMI
```

### gRPC
- Googleが開発したRPCフレームワーク
- シリアライザは Google 製の Protocol Buffers
- Open Source
- HTTP/2 for transport
- Interface記述言語にProtocol Buffers
- 以下のような機能を提供する
``` 
- 認証
- 双方向ストリーミング
- フロー制御
- ブロッキングまたはノンブロッキングバインディング
- キャンセルまたはタイムアウト
```
