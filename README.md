# FORGE STUDIO — fitness-gym / reshape

架空のパーソナルトレーニングブティック **FORGE STUDIO** のブランドサイト実装。
fitness-gym シリーズの `reshape` ペルソナ（ダイエット・体型変化を目的とした 25–45 歳層）向け。

## ブランドコンセプト

> **静かに、確実に、鍛え直す。**

RIZAP 的な「赤×黒×顔出しビフォーアフター」の煽り訴求の反面教師として、
体組成 metric（体脂肪率・除脂肪量・周径囲・VO₂ Max）の透明な開示によって
3〜6 ヶ月の transformation を証明する premium personal training boutique を演出している。

- **配色** — Carbon Black `#0e0e10` × Bone White `#f4f1ec` × Ember Orange `#c2410c`
- **書体** — Inter Tight（欧文 sans）/ Fraunces（欧文 serif）/ Shippori Mincho B1（和文 serif）/ Noto Sans JP（和文 sans）/ JetBrains Mono（数値）
- **写真** — グレースケール統一、鉄・汗・器具のマクロ（Unsplash）
- **CTA** — Ember Orange に唯一の彩度を集約し、「無料カウンセリング予約」に集約

## セクション構成

1. **Hero** — 静止画的な決意のコピー＋鉄のマクロ写真＋達成率 94% の単一数値
2. **METRIC** — InBody 実測平均値 4 指標 + モニタ風 SVG ラインチャート（FR-02 / FR-07）
3. **Programs** — 12週 / 16週 / 24週の 3 プラン比較・総額・分割例明記（FR-03 / FR-04）
4. **Trainers** — 3 名の経歴・資格・担当領域カード（FR-05）
5. **Philosophy** — Fraunces italic で短い founding principle
6. **FAQ** — 食事制限・続けられるか・返金保証など 6 項目（FR-08）
7. **Access** — 住所・営業時間・SVG 簡略地図（FR-09）
8. **Final CTA** — 60 分無料カウンセリングへ集約

「無料カウンセリング予約」CTA は header / hero / programs 末尾 / final CTA / footer の 5 箇所に固定（FR-06）。

## 技術スタック

- Pure HTML + CSS + Vanilla JS（ビルドステップなし）
- シングルファイル `index.html`
- Google Fonts （preconnect 付き）
- IntersectionObserver でスクロール reveal、`prefers-reduced-motion` 完全対応
- Mobile-first / 768px 以下で 1 カラム化（FR-10）

## デプロイ

GitHub Pages にて公開済（HTTPS 強制 ON、Let's Encrypt 証明書 approved）。

- **Live**: <https://design.fitness-gym-reshape.riumu.net/>
- **Repo**: <https://github.com/torifo/design-fitness-gym-reshape>

`.nojekyll` で Jekyll を無効化（SVG / `{{}}` の衝突回避）。

## 反面教師として避けたこと

- 赤色のアクセント（純赤 = 煽り）→ Ember Orange（熱を持った金属色）に置換
- 顔出しビフォーアフター → 体組成 metric のモニタ風 SVG に置換
- 「○○ kg 痩せた！」訴求 → 平均値 + N 数 + 期間の透明開示に置換
- 月額サブスク mass-market 訴求 → 12週 / 16週 / 24週の有限期間 transformation

## ファイル

| Path | Purpose |
|---|---|
| `index.html` | メイン実装 |
| `spec.md` | 要件定義（FR-01〜FR-10） |
| `DESIGN_LEARNINGS.md` | 実装から得た知見 |
| `.nojekyll` | GitHub Pages 用 |
| `CNAME` | カスタムドメイン設定 |

## License

架空のブランド / デザイン学習用途のみ。Unsplash 画像は各撮影者の Unsplash License に従う。

— *2026, by torifo*


## Install as a skill / スキルとして導入

This repo ships a cross-agent **`SKILL.md`** (open standard) usable by both Claude Code and Codex CLI as a design-reference skill. Link the repo into the agent's skills directory:

このリポジトリは Claude Code / Codex CLI 共通の **`SKILL.md`**（オープン標準）を同梱し、デザイン参照スキルとして使えます。

```bash
# Claude Code
ln -s "$(pwd)" ~/.claude/skills/design-fitness-gym-reshape
# Codex CLI
ln -s "$(pwd)" ~/.codex/skills/design-fitness-gym-reshape
```

Restart the agent; it is matched automatically by the skill's `description` (skill name: `design-fitness-gym-reshape`). / エージェント再起動後、`description` に基づき自動マッチします。
