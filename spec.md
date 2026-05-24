# FORGE STUDIO — fitness-gym/reshape Spec

**Status:** Approved
**Author:** torifo
**Created:** 2026-05-24
**Updated:** 2026-05-24

---

## 1. Overview

### Problem Statement
ダイエット・体型変化を目的としたパーソナルジムのWebは、RIZAP的な「赤×黒×ビフォーアフター大写し」の煽り表現に寄りやすく、結果は欲しいが下品な訴求は嫌う 25–45 歳層に届きにくい。一方、洗練側に振り切ると「本当に変われるのか」という証拠の弱さを生む。煽らずに数値で証明する premium transformation の表現が不足している。

### Goal
架空のパーソナルトレーニングブティック「FORGE STUDIO」を実装し、「3〜6 ヶ月で本気で変わる」という強い目的意識を、煽りではなく **数値・データ・静かな決意のトーン** で訴求する。ビフォーアフターは "顔出し感情訴求" ではなく "metric（体組成・周径囲）の変化" として提示する。

### Non-Goals
- 赤×黒の煽りビジュアル
- 「○○ kg 痩せました！」型の顔出しビフォーアフター
- 月額サブスク型 mass-market 訴求（チョコザップ系）
- カート / オンライン決済（CTA は無料カウンセリング予約に集約）

---

## 2. User Stories

| ID | Persona | Want to | So that |
|----|---------|---------|---------|
| US-01 | 30代会社員（結婚式・撮影など期限あり） | 3〜6 ヶ月で確実に変わる根拠を知りたい | 投資判断ができる |
| US-02 | 35歳女性・産後体型を戻したい | 煽られず、寄り添う姿勢の店を選びたい | 続けられそうか判断できる |
| US-03 | 40代経営者・時間が限られる | 効率・科学的根拠・トレーナー経歴を確認したい | 短時間で結果が出るか判断できる |
| US-04 | 検討初期の見込み客 | 料金を事前に把握したい | カウンセリング前に予算判断できる |

---

## 3. Functional Requirements

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-01 | ヒーローに静止画的な決意のコピー（煽りなし）と数値1点 | P0 |
| FR-02 | "METRIC" セクション：体組成・周径囲の平均変化値を数字のみで提示 | P0 |
| FR-03 | プログラム 3 種（12 週 / 16 週 / 24 週）の比較テーブル | P0 |
| FR-04 | 料金を明示（隠さない）。総額・分割例を併記 | P0 |
| FR-05 | トレーナー紹介（経歴・保有資格・担当領域）| P0 |
| FR-06 | 無料カウンセリング CTA を header / hero / プログラム末尾 / footer の4箇所に固定 | P0 |
| FR-07 | ビフォーアフターは顔写真ではなく、体組成計データのスクリーン風グラフィックで提示 | P1 |
| FR-08 | FAQ（食事制限・続けられるか・返金保証）5〜7 項目 | P1 |
| FR-09 | 店舗情報（住所・営業時間・アクセス）| P0 |
| FR-10 | モバイル 1 カラム化（768px 以下）、ヒーロー数値の縦積み | P0 |

---

## 4. Key Design Decisions

| Decision | Chosen | Rationale | Rejected |
|----------|--------|-----------|----------|
| 配色 | Carbon Black × Bone White × Ember Orange（差し色） | "鍛造（forge）"の質感。煽りの赤ではなく、熱を持った金属色で決意を表現 | RIZAP の純赤・REBORN の薄ベージュ |
| 書体（欧文） | Söhne / 代替 Inter Tight + セリフ見出し Fraunces | sans の精度感＋ serif の重みで「数値の信頼」と「決意の重さ」を両立 | Helvetica（ありがち）、Bebas（煽り） |
| 書体（和文） | Noto Sans JP（数値・本文）／ Shippori Mincho（見出し一部） | 明朝の縦線で「儀式性」、ゴシックの数値で「客観性」 | 游ゴシックのみ単体 |
| 装飾 | 細い罫線・等幅数値・余白多め、写真は B&W グレースケール統一 | 静かな緊張感。色味で煽らず、構図とコントラストで強度を出す | グラデーション、ネオン、炎エフェクト |
| ビフォーアフター表現 | 体組成データのモニタ風ビジュアル（数値とライン） | 「顔出し感情訴求」を回避し、metric で証明する | 上半身比較写真の並置 |
| CTA ボタン | Ember Orange 塗り + Carbon Black 文字、角丸 2px | 唯一の彩度を CTA に集約し、行動誘導を曖昧にしない | 黒ボタン白文字（弱い）、赤グラデ（煽り） |
| ヒーロー動画/画像 | グレースケール静止画（鉄・汗・器具のマクロ）| 静の中の熱量。動画は通信負荷とトーンを乱す | 笑顔のトレーナー集合写真 |
| 料金開示 | 全プラン総額・分割例を明記 | BEYOND 型「価格隠し」より、検討中ユーザーの離脱が少ない | 「カウンセリング時にご案内」 |

---

## 5. Design System

```css
--bg:        #f4f1ec;  /* Bone White：紙の白ではなく僅かに温度のある下地 */
--fg:        #0e0e10;  /* Carbon Black：純黒より僅かに青み */
--muted:     #6b6864;  /* Ash：補助テキスト */
--line:      #cfc9c0;  /* Bone Line：罫線・区切り */
--accent:    #c2410c;  /* Ember Orange：CTA と数値ハイライト専用 */
--accent-hi: #ea580c;  /* Ember Hover */
--metric:    #1a1a1d;  /* Metric Black：数値表示の引き締め色 */
--font-sans: 'Inter Tight','Noto Sans JP',sans-serif;
--font-serif:'Fraunces','Shippori Mincho',serif;
--font-mono: 'JetBrains Mono',ui-monospace,monospace; /* 体組成数値用 */
```

---

## 6. References

- RIZAP — https://www.rizap.jp/ （煽り訴求の典型例・反面教師）
- BEYOND — https://www.beyond-gym.com/ （洗練系パーソナルのトーン参考）
- REBORNMYSELF — https://reborn-myself.com/ （女性向け premium の寄り添いトーン）
- Equinox — https://www.equinox.com/ （"It's Not Fitness. It's Life." の lifestyle 訴求）
- Font: [Inter Tight](https://fonts.google.com/specimen/Inter+Tight)
- Font: [Fraunces](https://fonts.google.com/specimen/Fraunces)
- Font: [Noto Sans JP](https://fonts.google.com/noto/specimen/Noto+Sans+JP)
- Font: [Shippori Mincho](https://fonts.google.com/specimen/Shippori+Mincho)
- Font: [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono)
