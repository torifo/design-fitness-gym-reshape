# Design Learnings — FORGE STUDIO

「煽らずに transformation を訴求する」という制約は、配色と写真の選択をほぼ自動的に決めた。
赤を捨てた瞬間、CTA は唯一の彩度として Ember Orange に集約され、写真はすべてグレースケールに統一できた。
**色を引き算するほど、CTA の存在感が増す** という逆説的な体験が得られた。

METRIC セクションでは、顔写真ビフォーアフターを「体組成計のモニタ風 SVG ラインチャート」に置き換えた。
JetBrains Mono の tabular-nums と細い罫線だけで「客観性」を演出でき、感情訴求を完全に排除しながら
"証明" の機能だけは残せる。**情報量の量ではなく、フォーマットの選択が信頼を作る**という気づきがあった。

書体は Fraunces（欧文 serif）× Shippori Mincho B1（和文 serif）の見出しと、
Inter Tight × Noto Sans JP の本文を組み合わせ、数値だけは JetBrains Mono に分離。
serif の縦線が「決意の儀式性」、mono の等幅が「数値の客観性」を担い、役割分担が明快になった。

モバイルでは Light ウェイト（300）を 400 に切り替え、Hero h1 のフォントサイズも `clamp()` で下限を確保。
serif italic は小サイズでディセンダーが潰れやすいため、`line-height` を 1.4 以上に保つ調整が必要だった。

最大の学びは、**「禁止事項を spec に明記すると、デザインの自由度はむしろ上がる」** ということ。
RIZAP 的なるものを最初に "捨てる" と決めたことで、配色・写真・コピーの判断軸が一貫した。

— *Vol.02 / 2026, FORGE STUDIO build notes*
