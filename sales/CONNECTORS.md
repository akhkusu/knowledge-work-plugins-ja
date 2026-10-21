# コネクター

## ツールの参照方法

プラグインは**特定のツールに依存しません**。特定製品ではなく、CRM、チャット、メールなどの分類を使って業務フローを記述します。`.mcp.json`には特定のMCPサーバーが事前設定されていますが、同じ分類のMCPサーバーなら利用できます。

多くのプラグインでは、ファイル内で`~~category`の形式のプレースホルダーを使います。このプラグインのスキルでは、代わりに「CRM」「メール」「カレンダー」「通話の文字起こし」のように分類名を通常の文章で記載します。いずれの場合も分類を参照しているため、同じ分類のコネクターが使えます。下表のプレースホルダー列は、各分類と、プラグイン間で共通の表記との対応を示します。

すべてのスキルは、未接続でも動作します。エクスポートしたファイルやメモをアップロード・貼り付けすれば、その情報で作業できます。

## このプラグインのコネクター

| 分類 | プレースホルダー | 同梱サーバー | その他の選択肢 |
|----------|-------------|-----------------|---------------|
| CRM | `~~CRM` | HubSpot、Salesforce\*、Close、Monday | Pipedrive、Attio、Zoho CRM、Copper |
| メール | `~~email` | Gmail、Microsoft 365（Outlook）\* |  |
| カレンダー | `~~calendar` | Google Calendar、Calendly、Microsoft 365（Outlook）\* |  |
| チャット | `~~chat` | Slack、Microsoft 365（Teams）\* |  |
| 文書・ナレッジベース | `~~knowledge base` | Google Drive、Notion、Atlassian（Confluence）、Microsoft 365（SharePoint）\* | Box、Dropbox、Guru |
| 会話分析 | `~~conversation intelligence` | Gong、Fireflies、Zoom、Otter.ai | Granola、Fathom、Chorus |
| 情報拡充 | `~~data enrichment` | Clay、ZoomInfo、Apollo、Lusha、Crunchbase | Clearbit |
| 営業支援 | `~~sales engagement` | Outreach、Apollo | Salesloft |
| 競合情報 | `~~competitive intelligence` | Similarweb | Crayon、Klue |
| プロジェクト管理 | `~~project tracker` | Atlassian（Jira） | Linear、Asana |

## SalesforceとMicrosoft 365

**SalesforceとMicrosoft 365（上表の\*付き）は同梱されており、どちらも組織単位の設定が必要です。利用者がサインインする前に、管理者がClaudeでコネクターを有効にします。Salesforceでは、自社組織のSalesforceアプリの設定も必要です。**

接続後は、同じ分類の他のツールと同様にスキルから利用できます。

Google Calendar、Gmail、Google Driveは、`.mcp.json`にURLなしで記載されています。Claudeのコネクター設定から接続してください。

## 権限

コネクターが実行できる操作は、そのコネクター自体で設定します。ツールごとに許可・確認・禁止を指定でき、スキルはその範囲を超えません。定期実行で推奨される設定はREADMEを参照してください。
