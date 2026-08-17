# 02 — State

## Scope

このモジュールは、

- Reporting Stock State
- Stock coordinate
- Book Balanceとの区別
- Balance Sheet Constraint
- Aggregated State
- Degrees of Freedom
- State and History
- Accumulated Stock Transition

を扱う。

ASMでは、

$$
\boxed{
s(t)
=
\text{semantic / reporting Stock state at time }t
}
$$

とする。

重要なのは、

$$
\boxed{
s(t)
\neq
b(t)
}
$$

である。

$s(t)$ はReporting / Semantic layer、
$b(t)$ はBook / Ledger layerに属する。

## Stock State

時刻 $t$ におけるReporting Stock Stateを、

$$
\boxed{
s(t)\in\mathcal S
}
$$

とする。

ここで、

$$
\mathcal S
$$

は、

> Reporting上意味を持つStock quantitiesの状態空間

である。

例えば、

- Cash
- Accounts Receivable
- Inventory
- Equipment
- Debt
- Equity

などの時点量が含まれうる。

## Stock Means Point-in-time Quantity

Stockとは、

> ある特定時点において成立している量

である。

したがって、

$$
\boxed{
s=s(t)
}
$$

という時間依存性を持つ。

例えば、

$$
Cash(t)
$$

は時刻 $t$ におけるCashのReporting quantityである。

## Stock State Is Not a Flow Vector

RevenueやExpenseは、
一定期間について測られるFlowである。

したがって、

$$
\boxed{
\text{Stock State}
\neq
\text{Profit/Loss Flow}
}
$$

である。

具体的には、

$$
s(t)\in\mathcal S
$$

に対し、

$$
f(I)\in\mathcal F
$$

は異なる時間型を持つ。

ここで、

- $\mathcal S$：Stock-state space
- $\mathcal F$：Period-flow space

である。

## Reporting State and Book Balance

帳簿上のStock-valued account $i$ の残高を、

$$
\boxed{
b_i(t)
}
$$

とする。

一方、
Reporting State上の座標を、

$$
s_i(t)
$$

とする。

両者は対応する場合が多いが、
定義上同一ではない。

したがって、

$$
\boxed{
b_i(t)
\neq
s_i(t)
\quad\text{in general}
}
$$

である。

## Example: Cash

単純なCash accountでは、

$$
b_{\mathrm{Cash}}(t)
=
s_{\mathrm{Cash}}(t)
$$

となることが期待される。

しかしこれは、

> Book BalanceとReporting Stateが概念的に同じである

ことを意味しない。

単に、

> このAccountについてReporting Reconstructionが恒等的になる

という特別な場合である。

## Example: Equity During the Period

Revenueが発生した場合、
Reporting Equityはすでに増加している。

しかしClosing前のBook Equity accountへは、
その利益効果がまだ直接振り替えられていないことがある。

したがって、

$$
\boxed{
s_E(t)
\neq
b_E(t)
}
$$

となりうる。

この関係は、

[07 — Period and Stock-Flow](07-period-stock-flow.md)

で扱う。

## Reporting Coordinates

Reporting Stateを、

$$
s(t)
=
\begin{pmatrix}
s_1(t)\\
s_2(t)\\
\vdots\\
s_n(t)
\end{pmatrix}
$$

と考える。

各、

$$
s_i(t)
$$

は、

> Reporting Stock coordinate

である。

重要なのは、

$$
\boxed{
\text{Stock-valued Book Account}
\not\equiv
\text{Reporting State Coordinate}
}
$$

である。

## Account Space and State Space Are Different

帳簿勘定集合を、

$$
X
$$

とする。

Reporting State spaceを、

$$
\mathcal S
$$

とする。

両者は異なる概念である。

$$
\boxed{
X
\neq
\mathcal S
}
$$

である。

$X$ はBookkeeping representationのインデックス集合であり、
$\mathcal S$ はReporting meaningの状態空間である。

## Aggregated Stock

Reporting Stock Stateから、
主要な会計要素、

- Assets
- Liabilities
- Equity

を集約する作用を、

$$
\boxed{
G_S:
\mathcal S
\to
\mathbb R^3
}
$$

とする。

$$
\boxed{
G_S(s)
=
\begin{pmatrix}
A(s)\\
L(s)\\
E(s)
\end{pmatrix}
}
$$

である。

ここで、

- $A(s)$：Assets
- $L(s)$：Liabilities
- $E(s)$：Equity

である。

## Balance Sheet Constraint

有効なReporting Stock Stateでは、

$$
\boxed{
A(s)=L(s)+E(s)
}
$$

が成立する。

同値に、

$$
\boxed{
A(s)-L(s)-E(s)=0
}
$$

である。

## State Constraint Function

State Constraint functionを、

$$
\boxed{
g(s)
=
A(s)-L(s)-E(s)
}
$$

とする。

有効状態では、

$$
\boxed{
g(s)=0
}
$$

である。

## Valid State Space

Balance Sheet Constraintを満たす状態集合を、

$$
\boxed{
\mathcal S_{\mathrm{valid}}
=
\{
s\in\mathcal S
\mid
g(s)=0
\}
}
$$

とする。

したがって、

$$
\boxed{
s(t)\in\mathcal S_{\mathrm{valid}}
}
$$

であることが、
Reporting StateのStructural Validity条件となる。

## Degrees of Freedom at the Aggregated Level

Aggregate levelで、

$$
(A,L,E)\in\mathbb R^3
$$

とする。

しかし、

$$
A-L-E=0
$$

という1本の独立な制約が存在する。

したがって、
自由度は、

$$
\boxed{
3-1=2
}
$$

である。

例えば、

$$
A
$$

と、

$$
L
$$

が決まれば、

$$
\boxed{
E=A-L
}
$$

として決定される。

## Equity as a Dependent Aggregate Coordinate

Aggregate Balance Sheet上では、

$$
\boxed{
E=A-L
}
$$

なので、
Equityは独立な第三の自由度ではない。

ただしこれは、

> Equityが経済的に重要でない

という意味ではない。

意味論上は、
Assetsに対する残余請求権・所有者持分を表す重要なAccounting Elementである。

## Aggregate Degrees of Freedom Do Not Eliminate Detail

Aggregate levelの自由度が2であっても、
個別勘定レベルの情報が2個しか存在しないわけではない。

例えばAssetsは、

- Cash
- Accounts Receivable
- Inventory
- Equipment

など多数の座標へ分解されうる。

したがって、

$$
\boxed{
\text{aggregate degrees of freedom}
\neq
\text{number of detailed accounting coordinates}
}
$$

である。

## State and History

Current Stateは、
過去の履歴をすべて含むわけではない。

異なるAccounting History、

$$
H_1\neq H_2
$$

が、

$$
\boxed{
s_{H_1}(t)
=
s_{H_2}(t)
}
$$

という同じCurrent Stateへ到達する場合がある。

したがって、

$$
\boxed{
\text{Current State}
\not\Rightarrow
\text{Unique History}
}
$$

である。

## Example: Same Cash, Different History

企業Aが、

1. 出資100を受ける

ことでCash 100になった場合と、

企業Bが、

1. 売上150を得る
2. 費用50を支払う

ことでCash 100になった場合では、
Cashの現在値は同じでも履歴は異なる。

したがってCurrent Stockだけでは、
過去のFlowやTransaction Historyを復元できない。

## State as Accumulated Transition

各認識取引 $k$ のSemantic Stock Transitionを、

$$
\Delta s^{(k)}
$$

とする。

期間 $I$ に属する取引インデックス集合を、

$$
K(I)
$$

とする。

期間中の累積Stock Transitionを、

$$
\boxed{
F_S(I)
=
\sum_{k\in K(I)}
\Delta s^{(k)}
}
$$

とする。

すると、

$$
\boxed{
s(t_1)
=
s(t_0)
+
F_S(I)
}
$$

である。

すなわち、

$$
\boxed{
s(t_1)
=
s(t_0)
+
\sum_{k\in K(I)}
\Delta s^{(k)}
}
$$

である。

## Stock and Accumulated Effects

したがって、

$$
\boxed{
\text{Ending Stock}
=
\text{Beginning Stock}
+
\text{Accumulated Semantic Stock Changes}
}
$$

である。

ここで重要なのは、

$$
\boxed{
F_S(I)
\neq
f(I)
}
$$

である。

$F_S(I)$ はStock Transitionの累積、
$f(I)$ はPeriod Flowである。

## Flow Does Not Become Stock

Revenue / ExpenseなどのFlowそのものが、
Stock coordinateになるわけではない。

しかしProfit-forming transactionは、

$$
f_{\mathrm{PL}}(e)
$$

と同時に、

$$
\Delta s(e)
$$

を生じさせる。

したがって、

$$
\boxed{
\text{Flow itself is not Stock}
}
$$

だが、

$$
\boxed{
\text{the effects of Flow-forming transactions are reflected in Stock}
}
$$

である。

## Semantic Route to Ending State

ASMでは、
期間末Reporting StateへのSemantic routeを、

$$
\boxed{
s_{\mathrm{sem}}(t_1)
=
s(t_0)
+
F_S(I)
}
$$

と考える。

後にBook / Ledgerからも、

$$
\Phi_I
$$

を使って同じReporting Stateを再構成する。

正しい会計システムでは、
2つのrouteが一致する必要がある。

## Boundary

本モジュールは、

- Reporting Stock State
- State Coordinate
- Aggregate BS Constraint
- State / History distinction
- Accumulated Semantic Stock Transition

を扱う。

一方、

- $\Delta s$ の個別構造
- $f_{\mathrm{PL}}$
- Account Classification
- Book Balance $b_i(t)$ の更新
- Journal / Ledger
- Reporting Reconstruction $\Phi_I$

は後続モジュールで扱う。

## Core Equations

**Reporting Stock State：**

$$
\boxed{
s(t)\in\mathcal S
}
$$

**Book / Reporting Separation：**

$$
\boxed{
b(t)\neq s(t)
}
$$

**Aggregate Stock：**

$$
\boxed{
G_S(s)
=
\begin{pmatrix}
A(s)\\
L(s)\\
E(s)
\end{pmatrix}
}
$$

**State Constraint：**

$$
\boxed{
g(s)
=
A(s)-L(s)-E(s)
=
0
}
$$

**Valid State Space：**

$$
\boxed{
\mathcal S_{\mathrm{valid}}
=
\{
s\in\mathcal S
\mid
g(s)=0
\}
}
$$

**Aggregate Degrees of Freedom：**

$$
\boxed{
\dim=3-1=2
}
$$

**Accumulated Stock Transition：**

$$
\boxed{
F_S(I)
=
\sum_{k\in K(I)}
\Delta s^{(k)}
}
$$

**State Evolution：**

$$
\boxed{
s(t_1)
=
s(t_0)+F_S(I)
}
$$

## Relationship to Other Modules

- Reality / Recognition:
  [01 — Reality and Recognition](01-reality-and-recognition.md)
- Semantic Stock Transition:
  [03 — Transition](03-transition.md)
- Accounts / Temporal Type:
  [04 — Accounts and Classification](04-accounts-and-classification.md)
- Bookkeeping Representation:
  [05 — Double Entry](05-double-entry.md)
- Book Balance / History:
  [06 — Journal and Ledger](06-journal-and-ledger.md)
- Stock / Flow / Reporting Reconstruction:
  [07 — Period and Stock-Flow](07-period-stock-flow.md)
- Validation:
  [09 — Validation](09-validation.md)

## Open Questions

- $\mathcal S$ を正式なベクトル空間としてどこまで構造化するか。
- Reporting coordinateとBook accountの一般的対応写像をどう定義するか。
- Measurement uncertaintyをState coordinateへどう含めるか。
- Equity内部の複数構成要素をState spaceへどう展開するか。
- 非財務情報をAccounting Stateへ含める場合の境界をどう定めるか。
