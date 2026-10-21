# Knowledge Work Plugins

Claudeを、あなたの職種・チーム・会社に詳しい業務パートナーにするプラグイン集です。[Claude Cowork](https://claude.com/product/cowork)向けに開発されており、[Claude Code](https://claude.com/product/claude-code)でも利用できます。

## この日本語版の対象

セールス、CS（カスタマーサポート）、マーケティングを優先して日本語化しています。各領域のREADME、スキル、コネクターの説明は、次のページから確認できます。

- [セールス](sales/README.md)：顧客調査、商談準備、営業メール、案件管理、売上予測
- [CS（カスタマーサポート）](customer-support/README.md)：問い合わせ対応、回答案、エスカレーション、ナレッジ整備
- [マーケティング](marketing/README.md)：コンテンツ作成、キャンペーン計画、ブランド確認、効果分析

ファイル名、コマンド名、スキルの識別子、設定キーは英語のまま維持しています。上記以外の領域や、リンク先の外部資料には英語の内容が残っています。

## プラグインでできること

Coworkでは、目標を伝えるとClaudeが実務で使える成果物を作成します。プラグインを使うと、仕事の進め方、参照するツールやデータ、重要な業務手順、利用可能なスラッシュコマンドを指定できます。チーム全体で、より一貫した業務品質を実現するための仕組みです。

各プラグインは、特定の職種で使うスキル、コネクター、スラッシュコマンド、サブエージェントをまとめたものです。そのままでも業務の出発点として使えますが、自社のツール、用語、手順に合わせて調整すると、さらに役立ちます。

## プラグインの一覧

私たち自身の業務経験をもとに開発した、次の11種類のプラグインをオープンソースで公開しています。

| プラグイン | 主な用途 | 接続先の例 |
|--------|-------------|------------|
| **[productivity](./productivity)** | タスク、予定、日々の業務、自分の仕事に関する情報を管理し、毎回背景を説明する手間を減らします。 | Slack、Notion、Asana、Linear、Jira、Monday、ClickUp、Microsoft 365 |
| **[sales](./sales)** | 見込み顧客の調査、商談準備、案件の進捗確認、営業メールの下書き、競合比較資料の作成を支援します。 | Slack、HubSpot、Close、Clay、ZoomInfo、Notion、Jira、Fireflies、Microsoft 365 |
| **[customer-support](./customer-support)** | 問い合わせの振り分け、回答案の作成、エスカレーション資料の整理、顧客情報の調査、解決事例のナレッジ化を支援します。 | Slack、Intercom、HubSpot、Guru、Jira、Notion、Microsoft 365 |
| **[product-management](./product-management)** | 仕様書やロードマップの作成、ユーザー調査の整理、関係者への進捗共有、競合動向の把握を支援します。 | Slack、Linear、Asana、Monday、ClickUp、Jira、Notion、Figma、Amplitude、Pendo、Intercom、Fireflies |
| **[marketing](./marketing)** | コンテンツ作成、施策の計画、ブランド表現の統一、競合調査、チャネル別の効果報告を支援します。 | Slack、Canva、Figma、HubSpot、Amplitude、Notion、Ahrefs、SimilarWeb、Klaviyo |
| **[legal](./legal)** | 契約書のレビュー、秘密保持契約の一次確認、コンプライアンス対応、リスク評価、会議準備、定型回答の作成を支援します。 | Slack、Box、Egnyte、Jira、Microsoft 365 |
| **[finance](./finance)** | 仕訳の準備、勘定照合、財務諸表の作成、予実差異の分析、決算管理、監査対応を支援します。 | Snowflake、Databricks、BigQuery、Slack、Microsoft 365 |
| **[data](./data)** | SQLの作成、統計分析、可視化、ダッシュボードの構築、共有前の検証を通じて、データから示唆を得る作業を支援します。 | Snowflake、Databricks、BigQuery、Definite、Hex、Amplitude、Jira |
| **[enterprise-search](./enterprise-search)** | メール、チャット、ドキュメント、Wikiを横断して、必要な情報をまとめて検索します。 | Slack、Notion、Guru、Jira、Asana、Microsoft 365 |
| **[bio-research](./bio-research)** | 文献検索、ゲノム解析、研究標的の優先順位付けなど、前臨床の生命科学研究を支援します。 | PubMed、BioRender、bioRxiv、ClinicalTrials.gov、ChEMBL、Synapse、Wiley、Owkin、Open Targets、Benchling |
| **[cowork-plugin-management](./cowork-plugin-management)** | 新しいプラグインの作成や、自社のツールと業務フローに合わせた既存プラグインの調整を支援します。 | — |

Coworkから直接インストールすることも、このGitHubリポジトリで内容を確認することも、独自のプラグインを作ることもできます。

## はじめに

### Coworkで使う

[claude.com/plugins](https://claude.com/plugins/)からプラグインをインストールします。

### Claude Codeで使う

```bash
# マーケットプレイスを追加
claude plugin marketplace add anthropics/knowledge-work-plugins

# 使いたいプラグインをインストール
claude plugin install sales@knowledge-work-plugins
```

上記は原版マーケットプレイスのインストール例です。この日本語版のファイルを使う場合は、このチェックアウトにあるプラグインを読み込んでください。Claude Codeでは、たとえば次のようにローカルのプラグインディレクトリを指定できます。

```bash
claude --plugin-dir ./sales
```

インストールすると、関連する場面でスキルが自動的に使われます。スラッシュコマンドも利用できます（例：`/sales:call-prep`、`/data:write-query`）。

## プラグインの構成

各プラグインは、基本的に次の構成になっています。

```text
plugin-name/
├── .claude-plugin/plugin.json   # プラグインの定義
├── .mcp.json                    # ツール接続の設定
├── commands/                    # 明示的に実行するスラッシュコマンド
└── skills/                      # Claudeが必要に応じて参照する専門知識
```

- **スキル**：分野ごとの専門知識、実務上の推奨事項、作業手順をまとめます。Claudeが関連する場面で参照します。
- **コマンド**：明示的に呼び出す操作です。例：`/finance:reconciliation`、`/product-management:write-spec`。
- **コネクター**：[MCPサーバー](https://modelcontextprotocol.io/)を通じて、CRM、プロジェクト管理ツール、データウェアハウス、デザインツールなどに接続します。

中心となる構成要素はMarkdownとJSONです。プラグイン本体に共通のビルド工程や専用インフラはありません。一部のスキルに付属する補助スクリプトは、用途に応じて別途実行環境が必要です。

## 自社の業務に合わせる

これらのプラグインは、幅広い組織で使える出発点です。次のように調整できます。

- **接続先を変更する**：`.mcp.json`を編集し、自社で使っているツールに接続します。
- **社内情報を追加する**：用語、組織構成、業務手順をスキルファイルに記載します。
- **業務フローを調整する**：現場の進め方に合わせて、スキルの指示を変更します。
- **新しいプラグインを作成する**：`cowork-plugin-management`プラグインや、上記の構成を参考にします。

日本の業務で使う場合は、会計年度、日付・時刻、通貨、敬語、社内承認の手順などを自社の運用に合わせて指定してください。法務・会計・人事の記述に含まれる海外の制度名や規制は、日本の制度に自動的に置き換わるものではありません。対象の法域や適用する基準を確認して使ってください。

チームでプラグインを作成・共有すると、会社固有の知識や手順を日々の作業に反映しやすくなります。

## コントリビューション

リポジトリをフォークし、Markdownなどのファイルを編集して、プルリクエストを送ってください。ファイル名、スキルの識別子、コマンド名、設定キーは英語のまま維持できます。
