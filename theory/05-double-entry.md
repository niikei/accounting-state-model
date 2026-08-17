# 05 — Double Entry

## Scope

このモジュールは、認識された会計的変化を借方・貸方へ符号化し、仕訳として表現する構造を扱う。

## Debit and Credit Are Directions

借方・貸方は数学的な正負そのものではない。

$$
\boxed{\mathrm{Debit}\neq+}
$$

$$
\boxed{\mathrm{Credit}\neq-}
$$

両者は、勘定変化を左右に配置する記録方向である。

## Normal Orientation

各勘定 $i$ に normal orientation $\sigma_i$ を持たせる。

$$
\boxed{
\sigma_i=
\begin{cases}
+1 & \text{Debit-normal}\\
-1 & \text{Credit-normal}
\end{cases}}
$$

基本的な分類は、

$$
\sigma_A=\sigma_C=+1,
\qquad
\sigma_L=\sigma_E=\sigma_R=-1
$$

である。資産・費用は Debit-normal、負債・純資産・収益は Credit-normal となる。

## Encoding a Change

勘定 $i$ の変化を $\Delta x_i$ とし、D/C 方向を $d_i$ とする。

$$
\boxed{d_i=\operatorname{sgn}(\Delta x_i)\sigma_i}
$$

ここで、

$$
d_i=
\begin{cases}
+1 & \mathrm{Debit}\\
-1 & \mathrm{Credit}
\end{cases}
$$

である。したがって、同じ $+100$ の増加でも、資産なら借方、負債なら貸方になる。

## Journal Entry

会計的変化 $\Delta x$ の非ゼロ成分を、

$$
\operatorname{supp}(\Delta x)
=
\{i\mid\Delta x_i\neq0\}
$$

とする。仕訳を概念的に、

$$
\boxed{
J(\Delta x)
=
\{(i,d_i,|\Delta x_i|)
\mid i\in\operatorname{supp}(\Delta x)\}}
$$

と表す。

```mermaid
flowchart LR
    E["Economic Event<br/>e"]
    X["Accounting Change<br/>Δx"]
    J["Journal Entry<br/>J(Δx)"]

    E -->|"Recognition"| X
    X -->|"D/C Encoding"| J
```

仕訳は取引そのものではない。認識・分類・測定された変化を、複式簿記の記法へ変換した表現である。

## Balance of a Journal Entry

仕訳 $J$ の借方合計を $D(J)$、貸方合計を $C(J)$ とする。有効な仕訳は、

$$
\boxed{D(J)=C(J)}
$$

を満たす。仕訳残差を、

$$
r_J=D(J)-C(J)
$$

とすれば、形式的整合条件は、

$$
\boxed{r_J=0}
$$

である。

## Double-entry Does Not Mean Exactly Two Accounts

複合仕訳では3つ以上の勘定が動きうる。

$$
|\operatorname{supp}(\Delta x)|\neq2
$$

であっても、借方合計と貸方合計が一致し、複数の会計的側面を同時記録していれば複式簿記である。

## Formal and Economic Correctness

貸借一致は必要だが十分ではない。誤った勘定を使っても同額を左右へ置けば $r_J=0$ になりうる。

$$
\boxed{r_J=0\not\Rightarrow\text{economic correctness}}
$$

形式的、意味的、実証的な正しさの区別は [09 — Validation](09-validation.md) で扱う。

## Relationship to State Constraints

$A-L-E=0$、$\Delta A-\Delta L-\Delta E=0$、$D(J)-C(J)=0$ は同一の式ではない。前二者は状態・遷移レイヤー、後者は記録レイヤーの制約である。D/C encoding は、整合した会計的変化を、整合した記録へ写す役割を持つ。
