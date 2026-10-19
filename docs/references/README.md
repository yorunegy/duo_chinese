# 中国語DUO: 選定資料の出典と統合方針

このディレクトリは、ユーザーが選んだ3資料を中国語DUOの計画・レビュー向けに限定して翻案したプロジェクト内参照文書。上流のエージェント人格・実行指示・スクリプトを実行権限として扱わない。自動ランタイムロードやスキルのインストールを行う構成ではない。

## 対象と既存文書との比較

2026-10-19に保存環境の `/workspace/duo_chinese` を確認。originは `https://github.com/yorunegy/duo_chinese.git`、GitHub API上のリポジトリIDは `1425369084`、既定ブランチは `main`。作業ブランチは `work` で、HEADはリモートmainと同じ `524d7d6fe43c422f0efb093e488e98783ae93934`（空の初期コミット）だった。中国語DUOの対象リポジトリであることは接続先・IDで確認し、まだ存在しない実装や教材の仕様は推測していない。

統合前の追跡ファイル、未コミット変更、AGENTS.md、チェックアウト内の `.agents/skills/SKILL.md` はなかった。親の `/workspace/AGENTS.md` と `/AGENTS.md` もなかった。このため既存ルールとの重複・競合や上書き対象はなく、文書を新規追加した。ユーザーから指定された制約を適用し、形式・件数・難易度・反復頻度など未決定の仕様は追加していない。

| ローカル参照文書 | 採用する観点 | 採用しない範囲 |
| --- | --- | --- |
| [学習設計](learning-design.md) | 計画した語彙・文法、学習目標、例文、確認方法の対応 | 企業研修運用、ROI、製品・配信基盤、数値目標 |
| [物語設計](mini-story-design.md) | ミニストーリーの連続性、人物・固有名詞・設定の整合 | ゲーム分岐・エンジン・計測の実装、上流の台詞例 |
| [品質レビュー](content-quality.md) | 網羅漏れ、参照整合性、意図しない重複の発見 | 無差別な重複排除、外部フレームワークの導入・実行 |

3資料に共通する「目標との対応」「整合性」「評価」を役割別に整理した。対応計画は学習設計、人物・場面の整合は物語設計、横断的な欠落・重複候補は品質レビューに置き、相互リンクで接続する。上流の一意性という観点は、中国語DUOでは意図的な反復を残すよう限定した。自然な中国語であるかの確認は別レビューとして保持し、構造チェックで代替しない。

## 固定した上流出典

原文3件と各リポジトリのLICENSEを、下記コミットのraw URLから2026-10-19に取得・全文確認した。ローカル参照文書は用途を限定した日本語の翻案であり、原文の完全コピーではない。原文のフロントマターや実行可能な例は転記しない。上流リポジトリのAGENTS.mdはコピーしていない。下記SHA-256は取得した原文バイト列の値で、翻案後の文書の値ではない。

### Corporate Training Designer

- リポジトリ: `msitarzewski/agency-agents`
- 固定コミット: `652b2692f8d8ec2b1f1a38e559073e287dfdc469`
- 原文パス: `specialized/corporate-training-designer.md`
- [固定出典](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/specialized/corporate-training-designer.md)
- [取得元raw](https://raw.githubusercontent.com/msitarzewski/agency-agents/652b2692f8d8ec2b1f1a38e559073e287dfdc469/specialized/corporate-training-designer.md)
- 原文SHA-256: `e70733229e87dde01bd404f502d2f5b491821f681d7230b314b18d98111b898c`
- 翻案先: [学習設計](learning-design.md)
- ライセンス: MIT、Copyright (c) 2025 AgentLand Contributors

### Narrative Designer

- リポジトリ: `msitarzewski/agency-agents`
- 固定コミット: `652b2692f8d8ec2b1f1a38e559073e287dfdc469`
- 原文パス: `game-development/narrative-designer.md`
- [固定出典](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/game-development/narrative-designer.md)
- [取得元raw](https://raw.githubusercontent.com/msitarzewski/agency-agents/652b2692f8d8ec2b1f1a38e559073e287dfdc469/game-development/narrative-designer.md)
- 原文SHA-256: `7a5489c7b0502aa167030018137e3f349d2c32505c0ad7b9ec1de066a9a93f0d`
- 翻案先: [物語設計](mini-story-design.md)
- ライセンス: MIT、Copyright (c) 2025 AgentLand Contributors

### Data Quality Frameworks

- リポジトリ: `wshobson/agents`
- 固定コミット: `0874a27b17a22e2b7c2e2bcd725768e0803cad06`
- 原文パス: `plugins/data-engineering/skills/data-quality-frameworks/SKILL.md`
- [固定出典](https://github.com/wshobson/agents/blob/0874a27b17a22e2b7c2e2bcd725768e0803cad06/plugins/data-engineering/skills/data-quality-frameworks/SKILL.md)
- [取得元raw](https://raw.githubusercontent.com/wshobson/agents/0874a27b17a22e2b7c2e2bcd725768e0803cad06/plugins/data-engineering/skills/data-quality-frameworks/SKILL.md)
- 原文SHA-256: `58e61444165ba7caa572fb7f1ba2d23cfd5038cfa6699f86b5648e7fcb71d34d`
- 翻案先: [品質レビュー](content-quality.md)
- ライセンス: MIT、Copyright (c) 2024 Seth Hobson
- 原文には追加の詳細資料への案内とコード断片があるが、この統合は選定されたSKILL.mdの概念に限定する。追加資料・コードは取り込まず、実行しない。

## ライセンスの保持

原文の著作権表示・許諾・免責を含むLICENSE全文をそのまま保持する。これらのライセンス表示は対応する翻案資料の出典に関するもので、プロジェクト全体のライセンスを新たに決定するものではない。

- [agency-agents LICENSE全文](licenses/agency-agents-MIT.txt) — [固定出典](https://github.com/msitarzewski/agency-agents/blob/652b2692f8d8ec2b1f1a38e559073e287dfdc469/LICENSE)、SHA-256 `9a45258434d5cedf0af73c9ad4771373701225038d246c49219026c33677f66f`
- [wshobson/agents LICENSE全文](licenses/wshobson-agents-MIT.txt) — [固定出典](https://github.com/wshobson/agents/blob/0874a27b17a22e2b7c2e2bcd725768e0803cad06/LICENSE)、SHA-256 `f89abb55d9f073f38f1703e4518f0613c788c6174be7f13b8dfe48a1c076c746`

## 適用状態と作業範囲

初回の文書作成は保存環境のチェックアウト内の参照文書と[ルートAGENTS.md](../../AGENTS.md)への案内に限定し、コミット・push・公開は行わなかった。その後、ユーザーがこの7つの文書・ライセンスファイルのみをGitHubのmainへcommit・pushすることを別途承認した。この承認は製品・教材の開発や追加の公開作業を許可するものではない。

教材の大量生成、カリキュラム・データセット変更、製品開発、ビルド・テスト、インストーラー、フック、グローバル設定、チーム・モデル変更、課金は今回の許可範囲に含まれない。上流スクリプトやコード例を実行せず、既存のローカルCodexメモリも変更しない。文書リンク・出典・ライセンス・差分の確認を行い、ランタイム検証や中国語教材のレビューを済ませたとは扱わない。
