# gRPC is A high performance, open-source universal RPC framework
- [公式](https://grpc.io/)
- [RPC wiki](https://en.wikipedia.org/wiki/Remote_procedure_call)
- [gRPC wiki](https://en.wikipedia.org/wiki/GRPC)

#### RPC 
RPC wiki(原文)
```
In distributed computing, a remote procedure call (RPC) is when a computer program causes a procedure (subroutine) to execute in a different address space (commonly on another computer on a shared network), which is coded as if it were a normal (local) procedure call, without the programmer explicitly coding the details for the remote interaction. That is, the programmer writes essentially the same code whether the subroutine is local to the executing program, or remote.[1] This is a form of client–server interaction (caller is client, executor is server), typically implemented via a request–response message-passing system. In the object-oriented programming paradigm, RPC calls are represented by remote method invocation (RMI). The RPC model implies a level of location transparency, namely that calling procedures is largely the same whether it is local or remote, but usually they are not identical, so local calls can be distinguished from remote calls. Remote calls are usually orders of magnitude slower and less reliable than local calls, so distinguishing them is important.

RPCs are a form of inter-process communication (IPC), in that different processes have different address spaces: if on the same host machine, they have distinct virtual address spaces, even though the physical address space is the same; while if they are on different hosts, the physical address space is different. Many different (often incompatible) technologies have been used to implement the concept. 
```

RPC wiki(訳)
```
分散コンピューティングでは、リモートプロシージャコール（RPC）は、コンピュータプログラムが異なるアドレス空間（通常は共有ネットワーク上の別のコンピュータ上）でプロシージャ（サブルーチン）を実行させ、ローカルの）プロシージャコールを使用して、リモートインタラクションの詳細を明示的にコーディングする必要はありません。つまり、プログラマは、サブルーチンが実行中のプログラムに対してローカルであるか、リモートであるかにかかわらず、基本的に同じコードを書き込みます。[1]これは、クライアントとサーバーの対話形式（呼び出し元はクライアント、エグゼキュータはサーバー）であり、通常は要求 - 応答メッセージ・パッシング・システムを介して実装されます。オブジェクト指向プログラミングのパラダイムでは、RPC呼び出しはリモートメソッド呼び出し（RMI）によって表されます。 RPCモデルは、ローカルかリモートかにかかわらず、呼び出し手順がほぼ同じであるが、通常は同一ではないため、ローカル呼び出しをリモート呼び出しと区別することができるレベルの透過性を意味します。リモートコールは通常、ローカルコールよりも遅く信頼性が低いため、それらを区別することが重要です。

RPCはプロセス間通信（IPC）の一種で、異なるプロセスには異なるアドレス空間があります。物理アドレス空間が同じであっても、同じホストマシン上では異なる仮想アドレス空間を持ちます。異なるホスト上にある場合は、物理アドレス空間が異なります。多くの異なる（しばしば互換性のない）テクノロジがコンセプトを実装するために使用されています
```
#### gRPC
gRPC wiki(原文)
```
gRPC (gRPC Remote Procedure Calls[1]) is an open source remote procedure call (RPC) system initially developed at Google. It uses HTTP/2 for transport, Protocol Buffers as the interface description language, and provides features such as authentication, bidirectional streaming and flow control, blocking or nonblocking bindings, and cancellation and timeouts. It generates cross-platform client and server bindings for many languages.
```
gRPC wiki(訳)
```
gRPC（gRPCリモートプロシージャコール[1]）は、Googleで最初に開発されたオープンソースのリモートプロシージャコール（RPC）システムです。 トランスポートにHTTP / 2、インターフェイス記述言語にプロトコルバッファを使用し、認証、双方向ストリーミングとフロー制御、ブロッキングまたはノンブロッキングバインディング、キャンセルおよびタイムアウトなどの機能を提供します。 それは、多くの言語のためのクロスプラットフォームのクライアントとサーバーのバインディングを生成します。

```

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
