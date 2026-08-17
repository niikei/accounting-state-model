# 04 — Accounts and Classification

## Scope

このモジュールは、勘定科目を会計情報の分類軸として定義し、Stock / Flow、会計5要素、情報粒度を整理する。

## Account Classification

勘定 $i$ の分類を、

$$
\boxed{c(i)\in\{A,L,E,R,C\}}
$$

とする。

- $A$: Asset / 資産
- $L$: Liability / 負債
- $E$: Equity / 純資産
- $R$: Revenue / 収益
- $C$: Cost or Expense / 費用

$A,L,E$ は主として時点残高を持つ Stock account、$R,C$ は期間中に累積される Flow account である。

```mermaid
flowchart TD
    ACCOUNT["Account"]
    STOCK["Stock Account"]
    FLOW["Flow Account"]
    A["Asset"]
    L["Liability"]
    E["Equity"]
    R["Revenue"]
    C["Expense"]

    ACCOUNT --> STOCK
    ACCOUNT --> FLOW
    STOCK --> A
    STOCK --> L
    STOCK --> E
    FLOW --> R
    FLOW --> C
```

## Accounts as Coordinates and Categories

Stock 勘定は状態 $s(t)$ の座標として扱える。一方、すべての勘定科目は、現実を会計目的に従ってまとめるカテゴリーでもある。

$$
\boxed{
\text{Account}
\approx
\text{state coordinate or flow classification axis}}
$$

例えば、パソコン、机、椅子を別々に追跡するか、まとめて「備品」とするかは、会計情報の粒度の選択である。

## Classification Maps

詳細な認識対象の集合を $Z$、勘定集合を $X$ とすれば、分類写像を、

$$
\kappa:Z\to X
$$

と書ける。さらに勘定を5要素へ集約する写像を、

$$
c:X\to\{A,L,E,R,C\}
$$

とする。

```mermaid
flowchart LR
    DETAIL["Recognized Detail<br/>z ∈ Z"]
    ACCOUNT["Account<br/>x ∈ X"]
    ELEMENT["Element<br/>A / L / E / R / C"]

    DETAIL -->|"κ"| ACCOUNT -->|"c"| ELEMENT
```

## Granularity

会計情報には複数の粒度がある。

$$
\text{Detail}
\longrightarrow
\text{Account}
\longrightarrow
\text{Accounting Element}
\longrightarrow
\text{Financial Statement}
$$

粒度を細かくすると追跡可能性が高まるが、記録コストも増える。粗くすると扱いやすいが、内訳を復元できなくなる。集約の数学的性質は [08 — Aggregation](08-aggregation.md) で扱う。

## Classification Is Not Reality

現実の対象が、そのまま特定勘定に属するわけではない。分類は規則と目的に依存する。

$$
\text{Reality Object}
\xrightarrow{\text{Recognition / Classification}}
\text{Account}
$$

同じ「お金のようなもの」でも、会計上の現金に含むか、預金や受取手形など別の勘定へ分類するかは定義に従う。

## Semantic Errors

貸借が一致していても、誤った勘定へ分類されていれば会計的に正しくない。

$$
D(J)=C(J)
\not\Rightarrow
\kappa\text{ is correct}
$$

この区別は [09 — Validation](09-validation.md) で Structural Validity と Semantic Validity に分ける。

## Open Questions

- Flow account を状態ベクトルとは別に、帳簿上でどう統一表現するか。
- 勘定体系の変更や組織固有の勘定科目をどう写像として扱うか。
- 複数の会計基準による分類差をどうモデル化するか。
