# MCP

## MCPとは

- MCPはAnthropicが2024年11月25日にオープンソースとして公開した、LLMと外部ツール／データソースを標準化して繋ぐプロトコル
- 通信はJSON-RPC 2.0をベースに設計されており、Language Server Protocol由来のしくみを活用してる
- USB-C が様々なデバイスを標準化されたインターフェースで接続できるように、MCPは生成 AI モデルと様々なデータソースやツールを標準化された方法で接続する

## クライアント・サーバモデル

### ローカルMCPサーバー
```mermaid
flowchart TD
  Client["MCP</br>クライアント"]
  Context["MCP</br>サーバー"]

  Client --標準入力--> Context
  Context --標準出力--> Client
```
### リモートMCPサーバー

- **旧方式**
```mermaid
flowchart TD
  Client["MCP</br>クライアント"]
  Context["MCP</br>サーバー"]
  
  Client --HTTP--> Context
  Context --SSE--> Client
```
- **新方式**
```mermaid
flowchart TD
  Client["MCP</br>クライアント"]
  Context["MCP</br>サーバー"]
  
  Client <--Streamable HTTP--> Context

```

## 
