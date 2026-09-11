# native-ads — 長文ネイティブ広告の製造ライン（Claude Code skill）

xarkr の「$1M ad」（1画像＋10段の一人称ストーリー → advertorial → PDP）を日本市場向けに翻案した Claude Code スキル。

**流れ**: VoCリサーチ（海外＋日本の一次発言を実取得・逐語照合）→ アバター（68問・WHY×3・根拠付き）→ 10段コピー（60代ブログ文体）→ 画像（食材×間違った使い方×薬袋）→ QC（書き換え禁止）→ advertorial（取材記事型）。

## 入れ方
```
git clone https://github.com/yuyurun73-dev/native-ads-skill ~/.claude/skills/native-ads
```
Claude Code で `/native-ads` と打つか、「ネイティブ広告」「advertorial」と言えば起動する。

## 中身
- `SKILL.md` — 工程0〜6と地雷
- `references/ten-sections.md` — 10段の定義と原典の実文
- `references/voice-research-prompt.md` — xarkr の Customer Voice Research プロンプト（穴埋め式）
- `references/avatar-questionnaire.md` — 10章68問の質問票
- `references/register-ja.md` — 60代の本人語りの文体ルールと禁止事項
- `references/image-rules.md` — 画像の心理（講座 Phase 5）＋ 本人裁定の上書き
- `references/qc-checklist.md` — 薬機法・構造・出典・声の検査票
- `references/headlines-melao.md` — 見出しの型
- `references/exemplar-melao-v3.html` — 完成見本（広告本文・見出し・画像候補）
- `references/exemplar-melao-advertorial-v2.html` — 完成見本（advertorial）
- `references/xarkr-teardown.md` — 原典の分解

## 前提
- リサーチ・アバター・QC は Opus のサブエージェントで回す。コピーはメインが自分で書く。
- 画像は Higgsfield（GPT Image 2, 3:4）。
- 成果物は .md ファイルでなく本文か Artifact で出す。
- 出典は WebSearch で実在確認。捏造しない。
