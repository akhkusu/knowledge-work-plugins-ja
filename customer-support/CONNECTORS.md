# コネクター

## ツール参照の仕組み

プラグイン内の`~~category`は、その分類で利用者が接続しているツールを表すプレースホルダーです。例えば`~~support platform`は、Intercom、Zendesk、またはMCPサーバーを備えた他のサポートツールを指します。

プラグインは**特定の製品に依存しません**。業務手順は製品名ではなく、サポート管理、CRM、チャットなどの分類で記述します。`.mcp.json`には特定のMCPサーバーがあらかじめ設定されていますが、同じ分類に属する他のMCPサーバーでも利用できます。

## このプラグインの接続先

| 分類 | プレースホルダー | 同梱サーバー | その他の選択肢 |
|----------|-------------|-----------------|---------------|
| チャット | `~~chat` | Slack | Microsoft Teams |
| メール | `~~email` | Microsoft 365 | — |
| クラウドストレージ | `~~cloud storage` | Microsoft 365 | — |
| サポート管理 | `~~support platform` | Intercom | Zendesk、Freshdesk、HubSpot Service Hub |
| CRM | `~~CRM` | HubSpot | Salesforce、Pipedrive |
| ナレッジベース | `~~knowledge base` | Guru、Notion | Confluence、Help Scout |
| プロジェクト管理 | `~~project tracker` | Atlassian（Jira/Confluence） | Linear、Asana |
