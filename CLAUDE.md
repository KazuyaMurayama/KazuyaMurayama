# KazuyaMurayama — GitHub プロフィール README リポジトリ

このリポジトリは GitHub プロフィール（`github.com/KazuyaMurayama`）の README を管理する特殊リポ。表示される情報は他の作業リポと並行して個人ブランドの第一印象を形成する。

> **本ファイルは VSCode版 / Web版 Claude Code（claude.ai）の両方で本リポジトリの単独完結ガイド**。
> Web版はグローバル `~/.claude/CLAUDE.md` を参照しない前提で、本リポの運用に必要な全ルールをここに集約。

---

## 0. このリポジトリの目的
- GitHub プロフィール README の管理
- `KazuyaMurayama/KazuyaMurayama` という特殊な命名（ユーザー名と同じ）のため、`github.com/KazuyaMurayama` の TOP に README が自動表示される
- 主に [README.md](README.md) のみを編集対象とする

---

## 1. 開発者情報・命名ルール（本リポは命名一貫性が最重要）

| 種別 | 表記 | 用途 |
|---|---|---|
| **システム識別子（変更不可）** | `KazuyaMurayama` | GitHub ユーザー名 / URL / `@KazuyaMurayama` |
| **システム識別子（変更不可）** | `kazuya.murayama.21@gmail.com` | git `user.email` / 連絡先 |
| **表記名（人間として記載する場合）** | **男座員也（Kazuya Oza / おざ かずや）** | プロフィール本文の表示名 / 自己紹介文 / 肩書き |

- プロフィール README の**表示名**は **男座員也（Kazuya Oza）** で統一
- 「Murayama」「村山」「Otokoza」「おとこざ」を**表記名**として記載しない（システム識別子としての `KazuyaMurayama`、URL中の `KazuyaMurayama` は許容）
- 肩書き例: AI Transformation Architect / データサイエンティスト / 生成AIコンサルタント

---

## 2. ブランディング留意事項
- プロフィール README は外部の第一印象。表記の一貫性が他リポでの記載品質を支える
- リポジトリ一覧（pinned）に出すリポは厳選（[claude-code-prompt](https://github.com/KazuyaMurayama/claude-code-prompt) / [NASDAQ_backtest](https://github.com/KazuyaMurayama/NASDAQ_backtest) など代表作）
- 連絡経路（メール・SNS）の整合性を確認

---

## 3. ツール実行・Git・ファイル保存
- 確認不要・即実行（事前確認文を出力しない）
- 例外（事前確認必須）: main への `git push --force`、`gh repo delete`
- **ブランチ管理**: デフォルトはmainへ直接コミット。プロフィール README は変更頻度が低いため、複数編集をまとめてコミット
- **ファイル保存**: 本リポ内のみ。`C:\Users\user\Desktop` への出力禁止

---

## 4. 成果物報告ルール

| 成果物 | 説明 | リンク |
|---|---|---|
| README.md | 1行説明 | [開く](https://github.com/KazuyaMurayama/KazuyaMurayama/blob/main/README.md) |

- Markdownリンク `[表示名](URL)` 形式必須 / `/blob/<実ブランチ>/<実パス>` 形式
- **報告前にURL存在確認**：`Invoke-WebRequest -Uri https://api.github.com/repos/KazuyaMurayama/KazuyaMurayama/contents/PATH?ref=main -UseBasicParsing` でステータス200確認
- push完了後のみURL生成

---

## 5. Skill 起動ルール

| トリガー | スキル |
|---|---|
| プロフィール構成・自己紹介ライティング | `.claude/skills/data-narrative-builder/SKILL.md` / `executive-summary-generator/SKILL.md` |
| 業績・成果のビジネス翻訳 | `.claude/skills/technical-to-business-translator/SKILL.md` |
| インパクト定量化（実績数値化） | `.claude/skills/impact-quantification/SKILL.md` |
| 競合リサーチ（他のAI Architectのプロフィール調査） | `.claude/skills/research-deep/SKILL.md` |
| 図表・バッジ生成 | `.claude/skills/mermaid-agents365/SKILL.md` |
| QC・レビュー（公開前） | `.claude/skills/analysis-qa-checklist/SKILL.md` |
| 成果物の納品・コミット前 | `.claude/skills/sp-verification-before-completion/SKILL.md` |
