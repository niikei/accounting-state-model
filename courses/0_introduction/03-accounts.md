# 第3講 — 勘定科目とは

## 1. この講座で学ぶこと

企業の変化を資産・負債などの合計だけでなく、現金、売掛金、備品、借入金などの勘定科目に分けて記録する理由を学ぶ。

## 2. 通常の簿記的説明

勘定科目は、取引内容を同じ性質ごとに分類して記録・集計する単位である。各勘定は資産、負債、純資産、収益、費用のいずれかに分類される。

## 3. 関連するASM

- [02 — State](../../theory/02-state.md)
- [04 — Accounts and Classification](../../theory/04-accounts-and-classification.md)
- [08 — Aggregation](../../theory/08-aggregation.md)

## 4. ASMによる説明

Stock 勘定は状態ベクトルの座標、Flow 勘定は期間量の分類軸として扱う。勘定から5要素への写像は集約であり、合計だけを見るとどの勘定が動いたかという情報を失う。

```mermaid
flowchart LR
    DETAIL["Cash / AR / Equipment / ..."]
    CLASS["Account Classification"]
    ELEMENT["A / L / E / R / C"]

    DETAIL --> CLASS --> ELEMENT
```

## 5. 数学モデル

$$
c(i)\in\{A,L,E,R,C\}
$$

$$
G_S(s)=(A,L,E)^\top
$$

## 6. 具体例

資産が100増えたという情報だけでは、現金なのか売掛金なのか分からない。

$$
s=
\begin{pmatrix}
\mathrm{Cash}\\
\mathrm{AccountsReceivable}\\
\mathrm{Equipment}\\
\vdots
\end{pmatrix}
$$

という座標を持てば、変化の内訳を保持できる。

## 7. 現行ASMで説明できるか

**判定:** Yes

勘定を座標と分類カテゴリーの両方として捉えることで説明できる。

## 8. ASMへの新しい洞察

勘定科目の設計は、必要な情報量と記録コストの間で粒度を選ぶ問題でもある。

## 9. Theory更新候補

なし。粒度と分類写像は [04 — Accounts and Classification](../../theory/04-accounts-and-classification.md) に反映済み。

## 10. 未解決問題

組織固有の勘定体系や会計基準の違いを、分類写像の差としてどう表現するか。
