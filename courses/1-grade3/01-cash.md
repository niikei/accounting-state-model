---
source: いぬぼき
course: 日商簿記3級無料講座
url: https://inuboki.com/3q-kouza/chapter1-1/
related_urls:
  - https://inuboki.com/3q-kouza/chapter1-2/
---
# 簿記3級 第1講 — 現金

> いぬぼき「日商簿記3級無料講座」の現金に関するページを ASM で読む Course Note。

## 1. この講座で学ぶこと

現金勘定の増減記録、簿記上の現金の範囲、帳簿残高と実際有高の照合を学ぶ。ASM では Recognition / Classification / Measurement / Validation を具体的に検証する。

## 2. 通常の簿記的説明

現金は資産であり、増加を借方、減少を貸方へ記録する。簿記上の現金には通貨だけでなく、通貨代用証券として扱うものが含まれる場合がある。帳簿残高と実際有高に差があれば原因を調査し、必要な処理を行う。

## 3. 関連するASM

- [01 — Reality and Recognition](../../theory/01-reality-and-recognition.md)
- [02 — State](../../theory/02-state.md)
- [04 — Accounts and Classification](../../theory/04-accounts-and-classification.md)
- [05 — Double Entry](../../theory/05-double-entry.md)
- [09 — Validation](../../theory/09-validation.md)

## 4. ASMによる説明

現金は Stock 状態 $s(t)$ の一座標であり、資産に分類される Debit-normal account である。

$$
c(\mathrm{Cash})=A,
\qquad
\sigma_{\mathrm{Cash}}=+1
$$

ただし現実世界の対象が自動的に Cash になるわけではない。対象を認識し、Cash に分類し、金額を測定する過程が必要である。

```mermaid
flowchart LR
    W["Real-world Instrument"]
    R["Recognition"]
    C["Classification as Cash?"]
    M["Measurement"]
    S["Cash(t)"]

    W --> R --> C --> M --> S
```

## 5. 数学モデル

現金残高の変化は、

$$
\Delta\mathrm{Cash}
=
\mathrm{Cash}(t^+)-\mathrm{Cash}(t^-)
$$

である。記録方向は、

$$
d_{\mathrm{Cash}}
=
\operatorname{sgn}(\Delta\mathrm{Cash})
\sigma_{\mathrm{Cash}}
$$

で求める。

実査残差を、

$$
r_{\mathrm{cash}}
=
\mathrm{Cash}_{\mathrm{book}}
-
\mathrm{Cash}_{\mathrm{actual}}
$$

とすれば、一致時は $r_{\mathrm{cash}}=0$ である。

## 6. 具体例

帳簿上の現金が500から600へ増えた場合、

$$
\Delta\mathrm{Cash}=+100
$$

なので借方に100を記録する。一方、帳簿残高600に対して実際有高が590なら、

$$
r_{\mathrm{cash}}=600-590=10
$$

である。貸借一致している帳簿でも、この差は実査しなければ分からない。

## 7. 現行ASMで説明できるか

**判定:** Partially

現金の状態、分類、D/C、実査残差は説明できる。具体的に何を簿記上の現金へ含めるかは会計ルールに依存し、認識作用 $\mathcal A$ の詳細が必要である。

## 8. ASMへの新しい洞察

正しさには少なくとも次の三層がある。

- Structural: 仕訳や帳簿の貸借が一致している。
- Semantic: 対象を正しく Cash に分類している。
- Empirical: 帳簿残高と実際有高・証憑が対応している。

## 9. Theory更新候補

この講座から得られた Recognition → Classification → Measurement の分解と、Structural / Semantic / Empirical Validity の区別は、[01 — Reality and Recognition](../../theory/01-reality-and-recognition.md) と [09 — Validation](../../theory/09-validation.md) に反映済み。

## 10. 未解決問題

- 通貨代用証券の範囲を、会計ルール $\rho$ の入力としてどう表現するか。
- 現金過不足の原因判明前後を、認識状態の更新としてどう扱うか。
- 外貨現金の換算測定を Measurement と状態変化へどう分けるか。
