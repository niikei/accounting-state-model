# 04 — Accounts and Classification

## Scope

このモジュールは、

- Account Set
- Reporting Account
- Provisional Account
- Accounting Element Classification
- Stock / Flow Temporal Type
- Book Balance
- Semantic Period Flow
- Flow-account Book Accumulator
- Classification Map
- Account Granularity

を扱う。

ASMでは、

$$
\boxed{
\text{Account}
=
\text{bookkeeping classification unit}
}
$$

と考える。

AccountはRealityそのものではなく、
認識された会計情報を帳簿上整理するための分類単位である。

## Account Set

帳簿で使用される全勘定集合を、

$$
\boxed{
X
}
$$

とする。

ASMでは、

$$
\boxed{
X
=
X_{\mathrm{report}}
\mathbin{\dot\cup}
X_{\mathrm{provisional}}
}
$$

とする。

ここで、

- $X_{\mathrm{report}}$：Reporting meaningが確定している勘定
- $X_{\mathrm{provisional}}$：仮置き・未分類・処理途中の勘定

である。

## Why Provisional Rather Than Temporary

一般的なAccounting terminologyでは、
Revenue / Expenseのように期末Closingされる勘定を
Temporary Accountと呼ぶ場合がある。

ASMでは混同を避けるため、

> 未分類・処理途中・仮置きのAccount

を、

$$
\boxed{
\text{Provisional Account}
}
$$

と呼ぶ。

## Account Roles

Reporting Accountは、
Financial Reporting上の意味を持つ。

Provisional Accountは、

- Suspense
- Clearing
- Unclassified Amount
- Processing Intermediate

など、
最終的なReporting Classificationが未確定な情報を保持しうる。

## Accounting Element Classification

Reporting AccountからAccounting Elementへの写像を、

$$
\boxed{
c:
X_{\mathrm{report}}
\to
\{A,L,E,R,C\}
}
$$

とする。

ここで、

- $A$：Asset
- $L$：Liability
- $E$：Equity
- $R$：Revenue
- $C$：Cost / Expense

である。

## Element-wise Account Sets

各Accounting Elementに属するAccount集合を、

$$
\boxed{
X_q
=
\{
i\in X_{\mathrm{report}}
\mid
c(i)=q
\}
}
$$

とする。

したがって、

$$
\boxed{
X_{\mathrm{report}}
=
X_A
\mathbin{\dot\cup}
X_L
\mathbin{\dot\cup}
X_E
\mathbin{\dot\cup}
X_R
\mathbin{\dot\cup}
X_C
}
$$

である。

## Temporal Type

Accounting ElementからTemporal Typeへの写像を、

$$
\boxed{
\bar\tau:
\{A,L,E,R,C\}
\to
\{\mathrm{Stock},\mathrm{Flow}\}
}
$$

とする。

$$
\boxed{
\bar\tau(A)
=
\bar\tau(L)
=
\bar\tau(E)
=
\mathrm{Stock}
}
$$

$$
\boxed{
\bar\tau(R)
=
\bar\tau(C)
=
\mathrm{Flow}
}
$$

である。

## Account Temporal Type

Reporting Account $i$ のTemporal Typeを、

$$
\boxed{
\tau(i)
=
\bar\tau(c(i))
}
$$

とする。

したがって、

$$
\boxed{
\tau
=
\bar\tau\circ c
}
$$

である。

## Accounting Element and Temporal Type

```mermaid
flowchart LR
    ACCOUNT["Reporting Account<br/>i"]
    ELEMENT["Accounting Element<br/>c(i)"]
    TYPE["Temporal Type<br/>τ(i)"]

    ACCOUNT --> ELEMENT
    ELEMENT -->|"τ̄"| TYPE
```

Accounting Elementが決まることで、
そのAccountの基本的な時間型も決まる。

## Stock-valued Accounts

Stock-valued Reporting Account集合を、

$$
\boxed{
X_S
=
X_A
\mathbin{\dot\cup}
X_L
\mathbin{\dot\cup}
X_E
}
$$

とする。

$i\in X_S$ について、

$$
\tau(i)=\mathrm{Stock}
$$

である。

## Book Balance of a Stock-valued Account

Stock-valued Account $i$ のBook Balanceを、

$$
\boxed{
b_i(t)
}
$$

とする。

これは、

> 時刻 $t$ におけるAccount $i$ の帳簿残高

である。

## Book Balance and Reporting State

Book Balance、

$$
b_i(t)
$$

と、
Reporting State coordinate、

$$
s_i(t)
$$

は、
一般には区別する。

$$
\boxed{
b_i(t)
\neq
s_i(t)
\quad\text{in general}
}
$$

である。

Cashなどでは一致することが多い。

しかしEquityなどでは、
Closing前に異なる場合がある。

## Stock-valued Account Is Not Definitionally a State Coordinate

したがって、

$$
\boxed{
\text{Stock-valued Account}
\not\equiv
\text{Reporting State Coordinate}
}
$$

である。

AccountはBook layerの分類単位、
State coordinateはSemantic / Reporting layerの量である。

## Flow-valued Accounts

Flow-valued Reporting Account集合を、

$$
\boxed{
X_F
=
X_R
\mathbin{\dot\cup}
X_C
}
$$

とする。

$j\in X_F$ について、

$$
\tau(j)=\mathrm{Flow}
$$

である。

## Semantic Period Flow

Flow-valued account coordinate $j$ に対応する、
期間 $I$ のSemantic / Reporting Flow quantityを、

$$
\boxed{
f_j(I)
}
$$

とする。

例えば、

$$
Sales(I)
$$

$$
SalaryExpense(I)
$$

$$
DepreciationExpense(I)
$$

などである。

## Stock Quantity and Flow Quantity

Stock-valued Accountに対応するBook quantityは、

$$
b_i(t)
$$

という時点量である。

一方、
Flow-valued Accounting Informationは、

$$
f_j(I)
$$

という期間量である。

したがって、

$$
\boxed{
b_i(t)
\text{ and }
f_j(I)
}
$$

は異なる時間型を持つ。

## Flow Space

すべてのFlow coordinateをまとめて、

$$
\boxed{
f(I)
=
\left(
f_j(I)
\right)_{j\in X_F}
}
$$

とする。

$$
\boxed{
f(I)\in\mathcal F
}
$$

とし、

$$
\mathcal F
$$

をPeriod Flow Spaceと呼ぶ。

## Running Book Accumulator of a Flow Account

実際のLedgerでは、
Flow-valued accountにも期間途中のRunning Balanceが存在する。

期間 $I=(t_0,t_1]$ において、
時刻 $t$ までのFlow-account Book Accumulatorを、

$$
\boxed{
u_j(t;I)
}
$$

とする。

これは、

> 期間開始から時刻 $t$ までにAccount $j$ へ記録されたBook changesの累積

である。

## Pre-closing Flow Book Accumulator

期末Closing直前のAccumulatorを、

$$
\boxed{
u_j^-(I)
}
$$

とする。

Flow accounts全体について、

$$
\boxed{
u_F^-(I)
=
\left(
u_j^-(I)
\right)_{j\in X_F}
}
$$

とする。

## Flow Quantity and Book Accumulator Are Different

重要なのは、

$$
\boxed{
f_j(I)
\neq
u_j^-(I)
\quad\text{by definition}
}
$$

である。

$f_j(I)$ はSemantic / Reporting period quantity、
$u_j^-(I)$ はBook / Ledger accumulatorである。

正しいClassification / Representationの下では、
両者が対応することが要求されるが、
同一概念ではない。

## Flow Account Accumulator Is Not Stock

$$
u_j(t;I)
$$

は時刻 $t$ に値を持つが、
Reporting Stockではない。

それは、

> Period Flowを帳簿上累積するための技術的状態

である。

したがって、

$$
\boxed{
\text{Flow-account Book Accumulator}
\neq
\text{Reporting Stock}
}
$$

である。

## Classification Maps

認識された詳細対象の集合を、

$$
Z
$$

とする。

認識対象をBookkeeping Accountへ分類する写像を、

$$
\boxed{
\kappa:
Z\to X
}
$$

とする。

## Reporting Classification Pipeline

Reporting Accountについては、

$$
z
\xrightarrow{\kappa}
i
\xrightarrow{c}
c(i)
\xrightarrow{\bar\tau}
\tau(i)
$$

という分類構造を持つ。

```mermaid
flowchart LR
    DETAIL["Recognized Detail<br/>z"]
    ACCOUNT["Bookkeeping Account<br/>i"]
    ELEMENT["Accounting Element<br/>c(i)"]
    TYPE["Temporal Type<br/>τ(i)"]

    DETAIL -->|"κ"| ACCOUNT
    ACCOUNT -->|"c"| ELEMENT
    ELEMENT -->|"τ̄"| TYPE
```

## Provisional Accounts

Provisional Account、

$$
i\in X_{\mathrm{provisional}}
$$

については、
Accounting Element、

$$
c(i)
$$

が未確定の場合がある。

したがって、

$$
\tau(i)=\bar\tau(c(i))
$$

も一般には定義できない。

Provisional Accountの、

- Temporal Type
- Normal Orientation
- Reporting treatment

は、
用途に応じて別途定義する。

## Provisional Account Lifecycle

Provisional Accountは概念的に、

$$
\boxed{
\text{Unclassified Information}
\to
X_{\mathrm{provisional}}
\to
X_{\mathrm{report}}
}
$$

というLifecycleを持ちうる。

## Provisional Account Closing Condition

期末までに解消すべきProvisional Account $i$ については、

$$
\boxed{
b_i(t_{\mathrm{close}})=0
}
$$

を終了条件として要求できる。

ただし、
これはすべてのProvisional Accountへ無条件に課す公理ではない。

## Granularity

Accountは、
会計情報の粒度を決定する。

概念的には、

$$
\boxed{
\text{Detail}
\to
\text{Account}
\to
\text{Accounting Element}
\to
\text{Financial Statement}
}
$$

という情報解像度の階層がある。

## Classification Is Not Reality

現実の対象が、
自然に特定のAccountへ属しているわけではない。

$$
\boxed{
\text{Reality Object}
\xrightarrow{\text{Recognition / Classification}}
\text{Account}
}
$$

である。

したがって、

$$
\boxed{
\text{Classification}
\neq
\text{Reality itself}
}
$$

である。

## Semantic Errors

Journalが貸借一致していても、
Classificationが正しいとは限らない。

$$
D(J)=C(J)
$$

でも、

$$
\boxed{
D(J)=C(J)
\not\Rightarrow
\kappa\text{ is correct}
}
$$

である。

したがって、

$$
\boxed{
\text{Structural Correctness}
\neq
\text{Semantic Correctness}
}
$$

である。

## Core Equations

**Account Set：**

$$
\boxed{
X
=
X_{\mathrm{report}}
\mathbin{\dot\cup}
X_{\mathrm{provisional}}
}
$$

**Accounting Element Classification：**

$$
\boxed{
c:
X_{\mathrm{report}}
\to
\{A,L,E,R,C\}
}
$$

**Reporting Account Partition：**

$$
\boxed{
X_{\mathrm{report}}
=
X_A
\mathbin{\dot\cup}
X_L
\mathbin{\dot\cup}
X_E
\mathbin{\dot\cup}
X_R
\mathbin{\dot\cup}
X_C
}
$$

**Temporal Type：**

$$
\boxed{
\tau
=
\bar\tau\circ c
}
$$

**Stock-valued Accounts：**

$$
\boxed{
X_S
=
X_A
\mathbin{\dot\cup}
X_L
\mathbin{\dot\cup}
X_E
}
$$

**Flow-valued Accounts：**

$$
\boxed{
X_F
=
X_R
\mathbin{\dot\cup}
X_C
}
$$

**Stock Account Book Balance：**

$$
\boxed{
b_i(t),
\qquad
i\in X_S
}
$$

**Semantic Period Flow：**

$$
\boxed{
f_j(I),
\qquad
j\in X_F
}
$$

**Flow Book Accumulator：**

$$
\boxed{
u_j(t;I),
\qquad
j\in X_F
}
$$

**Flow Space：**

$$
\boxed{
f(I)
=
\left(
f_j(I)
\right)_{j\in X_F}
\in\mathcal F
}
$$

**Classification Map：**

$$
\boxed{
\kappa:
Z\to X
}
$$

## Relationship to Other Modules

- Reality / Recognition:
  [01 — Reality and Recognition](01-reality-and-recognition.md)
- Reporting State:
  [02 — State](02-state.md)
- Semantic Transition:
  [03 — Transition](03-transition.md)
- Bookkeeping Change / D/C:
  [05 — Double Entry](05-double-entry.md)
- Ledger / Book Accumulators:
  [06 — Journal and Ledger](06-journal-and-ledger.md)
- Period Flow / Reporting Reconstruction:
  [07 — Period and Stock-Flow](07-period-stock-flow.md)
- Aggregation:
  [08 — Aggregation](08-aggregation.md)
- Validation:
  [09 — Validation](09-validation.md)

## Open Questions

- $\mathcal F$ の正式なベクトル空間構造。
- $f_j(I)$ と $u_j^-(I)$ を接続するReporting interpretation map。
- Book Balance $b_i(t)$ とReporting State $s_i(t)$ の一般的対応。
- Provisional AccountのTemporal Typeの一般理論。
- 会計基準差による $c$ の変化。
- 多通貨Accountや数量Accountを同じ型体系へどう含めるか。
