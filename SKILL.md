---
name: design-fitness-gym-reshape
description: "fitness gym / studio landing-page design study — 'reshape' theme/persona (pure HTML/CSS/JS, no build). Use when designing a 'reshape'-style fitness gym / studio site aesthetic. 静かに、確実に、鍛え直す. fitness gym / studioの「reshape」テーマLPのデザイン参照スキル。"
---

# design-fitness-gym-reshape

A landing-page **design study** for a fictional **reshape**-theme fitness gym / studio (pure HTML + CSS + vanilla JS, no build, GitHub-Pages ready). Use this as a **style / design-system reference** when building a similar aesthetic.

架空の「reshape」テーマのfitness gym / studio LP デザイン研究。同種の世界観を作るときの**スタイル／デザインシステム参照**として使う。

## When to use / 使いどころ
- **EN:** designing a 'reshape'-style fitness gym / studio site — match its palette, typography and layout discipline.
- **JP:** 「reshape」系のfitness gym / studioサイトを設計するとき。配色・タイポ・レイアウト規律を流用。

## Bundled assets / 同梱アセット
This skill folder is the reference implementation — start from these files:
- `index.html` — full page markup
- `style.css` — design tokens (CSS custom properties) + layout
- `script.js` — vanilla JS (if present)
- `README.md` — full bilingual doc, brand context and series links

## Design reference / デザイン参照
_Lifted from the repo README — see README.md for the complete, bilingual version._

### ブランドコンセプト
> **静かに、確実に、鍛え直す。**

RIZAP 的な「赤×黒×顔出しビフォーアフター」の煽り訴求の反面教師として、
体組成 metric（体脂肪率・除脂肪量・周径囲・VO₂ Max）の透明な開示によって
3〜6 ヶ月の transformation を証明する premium personal training boutique を演出している。

- **配色** — Carbon Black `#0e0e10` × Bone White `#f4f1ec` × Ember Orange `#c2410c`
- **書体** — Inter Tight（欧文 sans）/ Fraunces（欧文 serif）/ Shippori Mincho B1（和文 serif）/ Noto Sans JP（和文 sans）/ JetBrains Mono（数値）
- **写真** — グレースケール統一、鉄・汗・器具のマクロ（Unsplash）
- **CTA** — Ember Orange に唯一の彩度を集約し、「無料カウンセリング予約」に集約

### 反面教師として避けたこと
- 赤色のアクセント（純赤 = 煽り）→ Ember Orange（熱を持った金属色）に置換
- 顔出しビフォーアフター → 体組成 metric のモニタ風 SVG に置換
- 「○○ kg 痩せた！」訴求 → 平均値 + N 数 + 期間の透明開示に置換
- 月額サブスク mass-market 訴求 → 12週 / 16週 / 24週の有限期間 transformation

## Tech / 技術
- Pure HTML + CSS + Vanilla JS（ビルドステップなし）
- シングルファイル `index.html`
- Google Fonts （preconnect 付き）
- IntersectionObserver でスクロール reveal、`prefers-reduced-motion` 完全対応
- Mobile-first / 768px 以下で 1 カラム化（FR-10）

## How to apply / 適用方法
1. Reuse `style.css` custom properties (color / type / spacing tokens) as the design-system base.
2. Copy `index.html` layout as the starting structure, then swap brand name and content.
3. Keep the palette, font pairing and layout discipline described above.

---
> The brand is fictional (design study) — replace all brand/content. Full context: see **`README.md`**.
