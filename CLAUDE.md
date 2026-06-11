# KazuyaMurayama — GitHub プロフィール README リポジトリ

このリポジトリは GitHub プロフィール（`github.com/KazuyaMurayama`）の README を管理する特殊リポ。表示される情報は他の作業リポと並行して個人ブランドの第一印象を形成する。

> **本ファイルは VSCode版 / Web版 Claude Code（claude.ai）の両方で本リポジトリの単独完結ガイドです。**
> Web版はグローバル `~/.claude/CLAUDE.md` を参照しません。本リポの運用に必要な全ルールをこの1ファイルに集約しています（他リポ・グローバルとの重複は完結性のため許容）。

---

## 1. このリポジトリの目的（本リポ固有）

- GitHub プロフィール README の管理
- `KazuyaMurayama/KazuyaMurayama` という特殊な命名（ユーザー名と同じ）のため、`github.com/KazuyaMurayama` の TOP に README が自動表示される
- 主に [README.md](README.md) のみを編集対象とする

---

## 2. 開発者情報・命名ルール（本リポは命名一貫性が最重要）

| 種別 | 表記 | 用途 |
|---|---|---|
| **システム識別子（変更不可）** | `KazuyaMurayama` | GitHub ユーザー名 / URL / `@KazuyaMurayama` |
| **システム識別子（変更不可）** | `kazuya.murayama.21@gmail.com` | git `user.email` / 連絡先 |
| **表記名（人間として記載する場合）** | **男座員也（Kazuya Oza / おざ かずや）** | プロフィール本文の表示名 / 自己紹介文 / 肩書き |

- プロフィール README の**表示名**は **男座員也（Kazuya Oza）** で統一。
- 「Murayama」「村山」「Otokoza」「おとこざ」を**表記名**として記載しない（システム識別子としての `KazuyaMurayama`・URL中の `KazuyaMurayama` は許容）。
- 肩書き例: AI Transformation Architect / データサイエンティスト / 生成AIコンサルタント

---

## 3. ツール実行ルール

- **確認不要・即実行**。「Allow〜?」「Should I…?」等の事前確認文を出力しない。即実行 → 事後報告。
- 長時間処理は積極的にバックグラウンド実行する。
- ファイル操作（編集・検索・読み込み）は専用ツール（Edit/Write/Read/Grep/Glob）を直接使用する。
- Shell は PowerShell 5.1 基準（`&&` 不可 → `;` + `if ($?)`）/ Bash 併用可。
- **例外（事前確認必須）**: main への `git push --force`、`gh repo delete`。

---

## 4. ブランチ管理

- **既定: main へ直接コミット**。プロフィール README は変更頻度が低いため、複数編集をまとめてコミット可。
- ブランチ作成はユーザーが明示指示した場合のみ。作成した場合は main へマージ → 削除 → push まで完了させる。
- 「完了 = main にマージ済み＆push済み」。ブランチにファイルを残したまま回答を終えない。

---

## 5. ファイル保存ルール

- 生成物はすべて**本リポジトリ内**に保存する。
- `C:\Users\user\Desktop` への出力は禁止（ユーザーが明示した場合のみ例外）。
- ログ・一時ファイルを無断で作らない。

---

## 6. 成果物報告ルール（毎回必須）

ファイルを1つでも作成・更新・push したら、**すべての**成果物を次の3列表で報告する。例外なし。

| 成果物 | 説明 | リンク |
|---|---|---|
| README.md | 1行説明 | [開く](https://github.com/KazuyaMurayama/KazuyaMurayama/blob/main/README.md) |

**厳守事項**
1. 必ず Markdownリンク `[表示名](URL)` 形式。plain text URL 禁止。
2. `/blob/<実ブランチ>/<実パス>` 形式。リポトップ URL 禁止。
3. **報告前に URL 存在確認**: `gh api repos/KazuyaMurayama/KazuyaMurayama/contents/PATH?ref=BRANCH` で存在確認。
4. ブランチ名は推測せず `git rev-parse --abbrev-ref HEAD` で実値取得。
5. **push 完了後にのみ URL 生成**。未push ファイルは絶対パス＋「（ローカル）」と明記。
6. 404 を出したら即訂正版を提示し、原因を1行報告。

---

## 7. ドキュメント命名・日付ルール（v2.0 / 2026-06-03 改訂）

### ファイル名
- 基本形 `<TOPIC>_YYYYMMDD.md`（**サフィックス・ハイフンなし**）。例: `PROFILE_DRAFT_20260603.md`
- 同日中の追加更新は `-v2`、`-v3`（例: `PROFILE_DRAFT_20260603-v2.md`）。
- 日付が変わったら v サフィックスをリセット。

### 表記の区別
- **ファイル名**: ハイフン**なし** `YYYYMMDD`（例: `20260603`）。
- **本文中の日付**: ハイフン**あり** `YYYY-MM-DD`（例: `2026-06-03`）。

### H1直下の日付メタデータ
レポート系 .md 新規作成時は H1直下に必ず記載し、更新時は **最終更新日のみ** 当日付に書き換える（作成日は固定）：
```
作成日: YYYY-MM-DD
最終更新日: YYYY-MM-DD
```

### 対象外（日付サフィックスを入れない）
README / CLAUDE.md / CHANGELOG / LICENSE

### 旧形式（廃止・新規禁止）
- ❌ `<TOPIC>_2026-06-03.md`（ハイフン区切り）
- ✅ `<TOPIC>_20260603.md`（現行ルール）

---

## 8. モデル使い分け

- **メイン: Claude Fable 5（`claude-fable-5`）** — 計画・中〜高難易度の実装/分析・全体指揮。
- **実行フェーズ（定型実装・ファイル編集・テスト実行）**: サブエージェントを `model: "sonnet"` で起動して委譲。
- ※難易度ベースの自動メイン切替は不可。Fable の自動切替は安全性ブロック時の Opus 4.8 フォールバックのみ。

---

## 9. Skill 起動ルール

> 本リポには `.claude/skills/` ディレクトリが存在しません。Skill が必要な場合は、グローバル（VSCode版: `~/.claude/skills/`）を参照してください。

| トリガー | 参照先（グローバル） |
|---|---|
| プロフィール構成・ライティング | `~/.claude/skills/sp-writing-skills/SKILL.md` |
| 成果物の納品・コミット前チェック | `~/.claude/skills/sp-verification-before-completion/SKILL.md` |
| QC・レビュー（公開前） | `~/.claude/skills/analysis-qa-checklist/SKILL.md` |

---

## 10. ブランディング留意事項

- プロフィール README は外部への第一印象。表記の一貫性が他リポでの記載品質を支える。
- リポジトリ一覧（pinned）に出すリポは厳選（[claude-code-prompt](https://github.com/KazuyaMurayama/claude-code-prompt) / [NASDAQ_backtest](https://github.com/KazuyaMurayama/NASDAQ_backtest) など代表作）。
- 連絡経路（メール・SNS）の整合性を確認。

---

## 11. 回答スタイル

- 日本語で回答する。
- 回答末尾に「**Next Action:**」でユーザーの次アクションを具体的に推奨する。迷う場面は「**推奨:**」で明示する。