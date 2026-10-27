# Codex AI Mentor Project Template

AIに実装を丸投げせず、要件整理から設計・実装・テスト・保守までを自分で学びながら進めるためのプロジェクトテンプレートです。
特定の言語やフレームワークに依存せず、AIを技術メンターや要件整理のPMとして活用するためのルール、作業手順、プロジェクト情報の置き場所を用意しています。

AI環境がファイルを参照できない場合は、必要なファイルの内容をチャットで提示してください。指示ファイルが自動で読み込まれるかどうかは、利用する環境により異なります。

## このテンプレートでできること

- 要件・設計・実装の相談やレビューを通じて、自分で判断しながら学習する
- プロジェクトの概要、技術、スコープ、決定事項、未決事項を継続的に管理する
- 作業ログとクライアントモードの議事録を分けて記録する
- AIがファイルを編集できる範囲を明確にし、明示した依頼の範囲に限定する
- 「クライアント」モードで要件を整理し、PMとのヒアリングを練習する
- 作業の開始・再開や終了時に、次の作業へ引き継ぐ

プロジェクトのソースコードやアプリケーション機能は含みません。これらの文書を、利用するプロジェクトに合わせて設定して使います。

## 利用開始

### 1. 自分の作業用リポジトリを用意する

GitHubでテンプレートからリポジトリを作成する機能が利用できる場合は、それを使います。利用できない場合はcloneし、自分用リポジトリを用意してください。

```bash
git clone https://github.com/Take-a-valley/codex-ai-mentor-template.git
cd codex-ai-mentor-template
```

cloneしただけでは、自分用リポジトリへの送信先には切り替わりません。pushする場合は、送信先リポジトリとGitの設定を確認してから操作してください。

### 2. 利用環境と初期情報を確認する

まず[AGENTS.md](AGENTS.md)でAIの役割、編集権限、例示の方針を確認し、[PROMPT.md](PROMPT.md)から利用する作業手順を確認します。次に、利用するプロジェクトに必要な範囲で以下を整理してください。

- [プロジェクト概要](docs/context/project_overview.md)
- [技術スタック](docs/context/technology_stack.md)
- [スコープ](docs/context/scope.md)
- [現在の作業](docs/context/current_tasks.md)
- [利用者設定](docs/context/mentor_preferences.md)

未定の項目は空欄や未定のままにし、決定事項として扱わないでください。

### 3. AIに開始を依頼する

AIに、AGENTS.mdとPROMPT.mdを確認し、現在の作業に必要な手順と関連するプロジェクト情報を読んでから開始するよう依頼します。全ファイルや全履歴を毎回読む必要はありません。必要な情報を参照できない環境では、その旨を伝え、該当する本文を共有してください。

テンプレートの初回起動では、利用者に確認するまで初期検証を実施したり、検証結果・変更履歴を記録したりしません。承認されない場合はそれらを未実施のままにし、通常の作業開始と区別します。詳細は[開始・再開の手順](docs/mentor/session.md)と[テンプレート動作確認](docs/mentor/validation.md)を参照してください。

## 日常の使い方

| 場面                 | 使い方                                                                             |
| -------------------- | ---------------------------------------------------------------------------------- |
| 作業開始・再開       | 現在の作業と関連資料を確認し、次の作業や未確認事項を整理する                       |
| 解説・レビュー・調査 | 対象と知りたい点を伝える。レビュー依頼だけではファイル編集を許可したことにならない |
| 要件整理             | `【クライアント】`で開始する。終了時は`クライアント終了`と伝える                   |
| 作業の終了           | `終了報告`で作業内容と次のタスクを整理する。Git操作は別途依頼する                  |

各場面の詳しい手順は[PROMPT.md](PROMPT.md)から参照できます。

## ファイル構成

```text
.
├── AGENTS.md
├── PROMPT.md
├── README.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── CHANGELOG.md
├── LICENSE
├── FILE_LIST.txt
├── .gitattributes
├── .gitignore
└── docs/
    ├── architecture/
    │   ├── README.md
    │   └── .gitkeep
    ├── context/
    │   ├── architecture_summary.md
    │   ├── current_tasks.md
    │   ├── decisions.md
    │   ├── glossary.md
    │   ├── learning_notes.md
    │   ├── mentor_preferences.md
    │   ├── open_questions.md
    │   ├── project_overview.md
    │   ├── scope.md
    │   └── technology_stack.md
    ├── logs/
    │   ├── AI_mentor_log.md
    │   └── Agenda_log.md
    └── mentor/
        ├── client.md
        ├── learning.md
        ├── requirements.md
        ├── session.md
        └── validation.md
```

## 主な文書

| ファイル・フォルダ                                         | 役割                                               |
| ---------------------------------------------------------- | -------------------------------------------------- |
| [AGENTS.md](AGENTS.md)                                     | AIの共通ルール、編集許可、例示と安全性の方針       |
| [PROMPT.md](PROMPT.md)                                     | 読み込み順と作業別手順への入口                     |
| [docs/mentor/session.md](docs/mentor/session.md)           | 開始・再開、引き継ぎ、ログ管理、終了報告           |
| [docs/mentor/learning.md](docs/mentor/learning.md)         | 解説、レビュー、実装・調査支援                     |
| [docs/mentor/requirements.md](docs/mentor/requirements.md) | 要件、技術、認証・権限、MVPの整理                  |
| [docs/mentor/client.md](docs/mentor/client.md)             | クライアントモードでのヒアリングと議事録           |
| [docs/mentor/validation.md](docs/mentor/validation.md)     | 初回承認後に行うテンプレートの検証手順             |
| [docs/context/](docs/context/)                             | プロジェクトの最新状態、決定、未決事項、利用者設定 |
| [docs/logs/](docs/logs/)                                   | 作業・学習ログとクライアントモードの議事録         |
| [docs/architecture/README.md](docs/architecture/README.md) | ユーザー主体で作成する設計書・仕様書の案内         |
| [CONTRIBUTING.md](CONTRIBUTING.md)                         | PR提出条件と変更提案時の確認事項                   |
| [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)                   | 参加者の行動指針                                   |
| [SECURITY.md](SECURITY.md)                                 | AI利用と機密情報に関する注意                       |
| [CHANGELOG.md](CHANGELOG.md)                               | テンプレートの変更履歴                             |
| [LICENSE](LICENSE)                                         | MIT Licenseの条件                                  |

## 編集権限と安全上の注意

通常、AIが直接編集できるのは`docs/context/`と`docs/logs/`配下のMarkdownです。それ以外のファイルは、対象と変更範囲を明示して編集を依頼した場合に限り、その範囲内で扱います。レビュー・解説・相談や、例示を求める依頼だけではファイル編集を許可したことになりません。詳しいルールは[AGENTS.md](AGENTS.md)を正本として確認してください。

業務情報、個人情報、認証情報、APIキーなどをAIへ入力する前に、所属組織と利用サービスのルールを確認してください。[SECURITY.md](SECURITY.md)も参照してください。

## PR提出について

PRを提出できるのは、事前にリポジトリへの参加を許可されたCollaboratorsのみです。詳細は[CONTRIBUTING.md](CONTRIBUTING.md)を確認してください。

## ライセンスと関連情報

このリポジトリはMIT Licenseです。利用条件は[LICENSE](LICENSE)を参照してください。
テンプレートの目的と利用例については[関連記事](https://qiita.com/Take-a-valley/items/ed6c524d78d16c0a8bc5)も参照ください。
