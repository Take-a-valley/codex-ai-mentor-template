# Codex AI Mentor Project Template

Codexを「コード生成AI」ではなく、**自己学習を支援するAIメンター**として使うためのプロジェクトテンプレートです。

開発未経験・ジュニアエンジニアが、AIに実装を丸投げせず、要件定義・設計・実装・レビュー・保守の流れを学ぶことを目的にしています。

---

## 概要

AIツールを使うと、コード生成や修正は非常に簡単になります。

一方で、開発経験が浅い段階でAIに実装を任せすぎると、次のような状態になりやすいです。

- 動くものはできたが、中身を説明できない
- エラーが出たときに原因を追えない
- 設計や実装方針の判断基準が身につかない
- AIがどこを変更したのか把握できない
- 再起動後にAIが過去の文脈を忘れてしまう

このテンプレートでは、Codexにコード生成をさせるのではなく、以下のような支援を行うAIメンターとして振る舞わせます。

- 実装方針の整理
- 設計・コードレビュー
- エラー原因の切り分け支援
- 調査キーワードや学習順序の提示
- 要件定義・設計の壁打ち
- 作業ログとコンテキストの整理

---

## このテンプレートでできること

- 長大なプロンプトを `PROMPT.md` に保存し、Codexに読み込ませて運用できます
- `AGENTS.md` にAIエージェント共通の最上位ルールを定義できます
- `/docs/context/` に現在の状況や決定事項を保存できます
- `/docs/logs/` に作業ログや議事録を保存できます
- `/docs/architecture/` にユーザー作成の設計書を配置できます
- Codexに直接編集させる範囲を限定できます
- `【クライアント】` モードで要件定義の練習ができます
- `終了報告` により学習ログを継続できます

---

## 想定する利用者

- AIを使いながら開発学習したい人
- Codexにコードを丸投げせず、自分で理解して実装したい人
- ジュニアエンジニア・未経験エンジニア
- 要件定義や設計も少しずつ学びたい人
- AIエージェント用の運用ルールを整備したい人

---

## 想定プロジェクト

このテンプレートでは、学習題材として **プロジェクト管理統合Webシステム** を想定しています。

具体的には、プロジェクトごとに以下の機能を統合管理するWebシステムです。

1. カンバン方式のタスク管理
2. Wikiによるドキュメント管理
3. WBS・ガントチャートによる進捗管理
4. プロジェクト内チャット

この題材はあくまで初期設定です。必要に応じて `PROMPT.md` や `docs/context/project_overview.md` を編集すれば、別の学習プロジェクトにも流用できます。

---

## 使用予定技術

| 領域 | 技術 |
|---|---|
| エディタ | VSCode |
| AIツール | Codex |
| フロントエンド | Next.js |
| バックエンド | Spring Boot |
| DB | MySQL |
| 認証 | メールログイン |

---

## ディレクトリ構成

```text
.
├─ PROMPT.md
├─ AGENTS.md
├─ CLAUDE.md
├─ README.md
├─ LICENSE
├─ CONTRIBUTING.md
├─ CODE_OF_CONDUCT.md
├─ SECURITY.md
├─ CHANGELOG.md
├─ .gitignore
├─ .github/
│  ├─ ISSUE_TEMPLATE/
│  │  ├─ bug_report.md
│  │  └─ feature_request.md
│  └─ pull_request_template.md
└─ docs/
   ├─ context/
   │  ├─ current_tasks.md
   │  ├─ project_overview.md
   │  ├─ architecture_summary.md
   │  ├─ technology_stack.md
   │  ├─ scope.md
   │  ├─ decisions.md
   │  ├─ open_questions.md
   │  ├─ glossary.md
   │  └─ learning_notes.md
   ├─ logs/
   │  ├─ AI_mentor_log.md
   │  └─ Agenda_log.md
   └─ architecture/
      ├─ README.md
      └─ .gitkeep
```

---

## セットアップ

### 1. このテンプレートを取得する

```bash
git clone https://github.com/your-name/codex-ai-mentor-project-template.git
cd codex-ai-mentor-project-template
```

または、このリポジトリをテンプレートとしてコピーして使ってください。

### 2. VSCodeで開く

```bash
code .
```

### 3. Codexに初期プロンプトを送る

```text
PROMPT.md を読み込んで、このプロジェクトのAIメンターとして動作してください。
あわせて AGENTS.md、README.md、docs/context/、docs/logs/、docs/architecture/ を確認し、現在の状況を復元してください。
```

---

## 基本的な使い方

### 通常メンターモード

通常時、CodexはAIメンターとして振る舞います。

- 実装方針の整理
- 設計レビュー
- コードレビュー
- エラー原因の切り分け支援
- 調査キーワードの提示
- 学習順序の提案
- 作業ログの整理

### クライアントモード

ユーザーが文頭に `【クライアント】` と入力した場合、CodexはPMとして振る舞います。

```text
【クライアント】
プロジェクトごとにタスクとWikiを一元管理できるシステムが欲しいです。
```

終了する場合は以下を入力します。

```text
クライアント終了
```

Codexはクライアントモード中のやり取りを `docs/logs/Agenda_log.md` に保存します。

### 終了報告

作業終了時は以下を入力します。

```text
終了報告
```

Codexは作業内容、学習内容、決定事項、未決事項、次回タスクを整理し、`docs/logs/AI_mentor_log.md` に追記します。

---

## 編集許可範囲

Codexが直接編集してよいファイルは以下です。

```text
docs/context/*.md
docs/logs/*.md
```

以下は原則として直接編集禁止です。

```text
docs/architecture/*.md
ソースコード
設定ファイル
packageや依存関係ファイル
Markdown以外のファイル
```

---

## 注意事項

このテンプレートは、AIに実装を丸投げするためのものではありません。

AIを使いながらも、自分で考え、自分で実装できる力を身につけることを目的としています。

また、業務コードや機密情報をAIツールに入力する場合は、所属組織やプロジェクトの利用ルールを必ず確認してください。

---

## ライセンス

MIT License
