# チャット分析アプリ開発計画書

## 1. 目的
ユーザーと会話しつつ、自然言語でDBからのデータ抽出と加工、可視化を行うツールを作成することで、分析の効率化を実現する。
## 2. 主要機能
- 自然言語での会話
- 自然言語での指示と、テーブル定義のRAGに基づくSQLの生成と実行
- 自然言語での指示に基づくPandasでのデータ加工
- 自然言語での指示に基づくmatplotlibでのデータ可視化
## 3. 環境
- 開発にはPython3.12を使用する。
- バックエンドに使用する主要なPythonライブラリ：langgraph, langchain, pandas, matplotlib
- フロントエンドに使用する主要なPythonライブラリ: chainlit
- 生成AIはAzure Open AIのAPIを経由してChatGPT4O miniを使用する。接続の際は.envでAPI keyやendpointを指定する形とする。
- 接続するDBにはSQLiteを使用
- RAGにはAzure OpenAI の Embedding APIでベクトル化した文書を使い、 Retrieverにはlangchain_community.vectorstores.FAISSを利用する。
## フォルダ構成イメージ
app/
  ├─ nodes/          # 各 LangGraph ノード
  ├─ db/             # SQL 実行ユーティリティ
  ├─ prompts/        # プロンプトテンプレート 
  ├─ ui/             # Chainlit関連 \n 
  └─ main.py         # LangGraph + Chainlit 起動
## 注意点
- コードは実行可能な最小構成。
- コメントは日本語で簡潔にすること。
