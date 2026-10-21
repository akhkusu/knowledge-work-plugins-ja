# コネクター

## ツール参照の仕組み

プラグインでは、各カテゴリーでユーザーが接続したツールを表すプレースホルダーとして`~~category`を使います。たとえば`~~marketing automation`は、HubSpot、Marketo、またはMCPサーバーを備えた他のマーケティング基盤を意味します。

プラグインは**特定のツールに依存しません**。製品名ではなく、デザイン、SEO、メールマーケティングなどのカテゴリーで業務手順を記述します。`.mcp.json`には特定のMCPサーバーが事前設定されていますが、同じカテゴリーの他のMCPサーバーも利用できます。

## このプラグインのコネクター

| カテゴリー | プレースホルダー | 同梱のサーバー | その他の選択肢 |
|----------|-------------|-----------------|---------------|
| チャット | `~~chat` | Slack | Microsoft Teams |
| デザイン | `~~design` | Canva, Figma | Adobe Creative Cloud |
| マーケティング自動化 | `~~marketing automation` | HubSpot | Marketo, Pardot, Mailchimp |
| プロダクト分析 | `~~product analytics` | Amplitude | Mixpanel, Google Analytics |
| ナレッジベース | `~~knowledge base` | Notion | Confluence, Guru |
| SEO | `~~SEO` | Ahrefs, Similarweb | Semrush, Moz |
| メールマーケティング | `~~email marketing` | Klaviyo | Mailchimp, Brevo, Customer.io |
| マーケティング分析 | `~~marketing analytics` | Supermetrics | Google Analytics, Mailchimp, Semrush |
