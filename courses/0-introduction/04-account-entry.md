---
source: いぬぼき
course: 初めて学ぶ簿記入門講座
url: https://inuboki.com/nyuumon/nyuumon-text4/
---
# 第4講 — 勘定記入とは

> いぬぼき「初めて学ぶ簿記入門講座」第4講を ASM で読む Course Note。

## 1. この講座で学ぶこと

勘定の左を借方、右を貸方と呼び、勘定の種類と増減に応じて記入方向が決まることを学ぶ。

## 2. 通常の簿記的説明

資産・費用は借方が通常の増加側、負債・純資産・収益は貸方が通常の増加側である。減少は反対側へ記入する。

## 3. 関連するASM

- [04 — Accounts and Classification](../../theory/04-accounts-and-classification.md)
- [05 — Double Entry](../../theory/05-double-entry.md)

## 4. ASMによる説明

借方・貸方は正負ではなく記録方向である。勘定ごとの normal orientation $\sigma_i$ と実際の増減符号を組み合わせて D/C を決める。

## 5. 数学モデル

$$
\sigma_i=
\begin{cases}
+1 & \text{Debit-normal}\\
-1 & \text{Credit-normal}
\end{cases}
$$

$$
d_i=\operatorname{sgn}(\Delta x_i)\sigma_i
$$

## 6. 具体例

現金と借入金がともに100増加しても、

$$
\sigma_{\mathrm{Cash}}=+1,
\qquad
\sigma_{\mathrm{Debt}}=-1
$$

なので現金は借方、借入金は貸方になる。

## 7. 現行ASMで説明できるか

**判定:** Yes

D/C を状態変化の本体ではなく符号化規約として分離することで説明できる。

## 8. ASMへの新しい洞察

「増加 = 借方」という暗記ではなく、分類と増減の組で方向を導出できる。

## 9. Theory更新候補

なし。normal orientation と符号化規則は [05 — Double Entry](../../theory/05-double-entry.md) に反映済み。

## 10. 未解決問題

 contra account など通常残高と異なる性質を持つ勘定を $\sigma_i$ だけで十分に表せるか。
