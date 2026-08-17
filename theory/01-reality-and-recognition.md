# 01 — Reality and Recognition

## Scope

このモジュールは、

> 経済的現実が、どのように会計情報として認識されるか

を扱う。

ASMの出発点は、

$$
\boxed{
\text{Reality}
\neq
\text{Accounting Representation}
}
$$

という区別である。

企業に実際に存在する経済的事実と、
帳簿・財務諸表に表現される会計情報は同一ではない。

会計は現実そのものではなく、

> 一定の認識・分類・測定規則を通じて構成された現実の表現

である。

## Reality

時刻 $t$ における企業の経済的現実を、

$$
\boxed{
\omega(t)\in\Omega
}
$$

とする。

ここで、

$$
\Omega
$$

は、

> 企業が取りうる現実の経済状態の集合

である。

$\omega(t)$ には例えば、

- 現金の存在
- 商品の存在
- 建物や設備の存在
- 売掛債権
- 借入契約
- 顧客との契約
- 従業員
- 火災
- 盗難
- 将来の支払義務

など、企業に関係する多様な事実が含まれうる。

## Economic Event

現実世界で発生する事象を、

$$
e
$$

とする。

事象 $e$ によって現実が、

$$
\boxed{
\omega^-
\xrightarrow{e}
\omega^+
}
$$

と変化すると考える。

ここで、

- $\omega^-$：事象直前のReality
- $\omega^+$：事象直後のReality

である。

したがって、

$$
\boxed{
e
=
\text{a transition in economic reality}
}
$$

と捉えることができる。

## Reality Change Is Not Necessarily an Accounting Transaction

重要なのは、

$$
\boxed{
\text{Reality Change}
\neq
\text{Accounting Transaction}
}
$$

である。

現実に変化が起きたとしても、
その変化が必ず会計上認識されるとは限らない。

例えば、

- 注文を受けた
- 従業員の技能が向上した
- ブランド価値が高まった
- 将来売上の可能性が上昇した

といった現実変化が、
その時点で直ちに仕訳を生じさせるとは限らない。

したがってASMでは、

> Reality layer

と、

> Accounting layer

を明確に分離する。

## Recognition Pipeline

現実から会計情報を構成する過程を、
少なくとも次の三段階に分ける。

1. Recognition
2. Classification
3. Measurement

```mermaid
flowchart LR
    W["Economic Reality<br/>ω"]

    R["Recognition<br/>認識対象か"]

    C["Classification<br/>何として認識するか"]

    M["Measurement<br/>いくらとして認識するか"]

    A["Recognized Accounting Information"]

    W --> R --> C --> M --> A
```

それぞれの役割は異なる。

## Recognition

Recognitionとは、

> 現実の事象・状態を会計情報として取り込むかどうか

を決定する作用である。

例えば、
ある経済事象 $e$ が発生しても、

$$
\boxed{
\text{Recognized}(e)=0
}
$$

なら、
その時点では会計記録へ入らない。

一方、

$$
\boxed{
\text{Recognized}(e)=1
}
$$

なら、
Classification / Measurementの対象になる。

## Classification

Classificationとは、

> 認識された対象を、どの会計的意味へ割り当てるか

を決定する作用である。

例えば同じ100円の支出でも、

- Expense
- Equipment
- Inventory
- Prepaid Expense

など、
異なる会計的意味を持ちうる。

したがって、

$$
\boxed{
\text{Recognition}
\neq
\text{Classification}
}
$$

である。

認識対象であることと、
どの勘定・会計要素へ分類されるかは別問題である。

## Measurement

Measurementとは、

> 認識・分類された対象に会計上の金額を与えること

である。

例えば、

- 取得原価
- 償却後の帳簿価額
- 見積額
- 貸倒見積額

などが関係する。

したがって、

$$
\boxed{
\text{Classification}
\neq
\text{Measurement}
}
$$

である。

## Accounting Recognition Operator

Recognition / Classification / Measurementをまとめた会計作用を、
暫定的に、

$$
\boxed{
\mathcal A
}
$$

とする。

会計規則を $\rho$、
必要な見積りを $\eta$ とすれば、

$$
\boxed{
\mathcal A(\omega,t,\rho,\eta)
=
\text{recognized accounting information}
}
$$

と考える。

概念的には、

$$
\boxed{
\omega
\xrightarrow{\mathcal A}
\text{Accounting Meaning}
}
$$

である。

## Why Time and Rules Matter

同じRealityであっても、

- Recognition rule
- Accounting standard
- Measurement assumption
- Reporting date

が異なれば、
会計情報が異なる可能性がある。

したがって一般には、

$$
\boxed{
\mathcal A
=
\mathcal A(\omega,t,\rho,\eta)
}
$$

と考える必要がある。

これは特に、

- 減価償却
- 貸倒見積り
- 引当
- 決算整理
- 期間配分

などで重要になる。

## Recognized Accounting Effect

認識された経済的事象 $e$ は、
会計上、少なくとも二種類の効果を持ちうる。

### Stock Effect

Reporting Stock Stateに対する変化を、

$$
\boxed{
\Delta s(e)
}
$$

とする。

これは、

> 認識された事象によるSemantic Stock Transition

である。

### Profit/Loss Flow Effect

Revenue / Expenseのような
利益形成に関する期間情報を、

$$
\boxed{
f_{\mathrm{PL}}(e)
}
$$

とする。

これは、

> 認識された事象が生み出すProfit/Loss Flow情報

である。

## Accounting Effect

認識された事象の会計的意味をまとめて、

$$
\boxed{
\alpha(e)
=
\left(
\Delta s(e),
f_{\mathrm{PL}}(e)
\right)
}
$$

と定義する。

したがって、

$$
\boxed{
\alpha(e)
=
\text{semantic accounting effect of }e
}
$$

である。

ここで重要なのは、
$\alpha(e)$ はまだ仕訳ではないということである。

## Accounting Transaction

ASMでは現在の通常の財務会計の範囲において、
経済的事象 $e$ が非ゼロのAccounting Effectを生じるとき、
それを会計上のTransactionと呼ぶ。

取引集合を、

$$
\mathcal T
$$

とする。

すると暫定的に、

$$
\boxed{
e\in\mathcal T
\quad\Longleftrightarrow\quad
\alpha(e)\neq(0,0)
}
$$

と定義する。

すなわち、

$$
\boxed{
e\in\mathcal T
\quad\Longleftrightarrow\quad
\left(
\Delta s(e),
f_{\mathrm{PL}}(e)
\right)
\neq
(0,0)
}
$$

である。

## Example: Order

商品100の注文を受けたとする。

現実には、

$$
\omega^-
\neq
\omega^+
$$

となる可能性がある。

しかし、その時点では会計上、

$$
\Delta s(e)=0
$$

かつ、

$$
f_{\mathrm{PL}}(e)=0
$$

なら、

$$
\alpha(e)=(0,0)
$$

である。

したがって、

$$
e\notin\mathcal T
$$

となる。

## Example: Credit Sale

商品を掛けで100販売し、
売上を認識したとする。

この場合、

$$
\Delta s(e)\neq0
$$

かつ、

$$
f_{\mathrm{PL}}(e)\neq0
$$

である。

したがって、

$$
\alpha(e)\neq(0,0)
$$

となり、

$$
e\in\mathcal T
$$

である。

## Example: Borrowing

現金100を借り入れる。

この場合、

$$
\Delta s(e)\neq0
$$

だが、

$$
f_{\mathrm{PL}}(e)=0
$$

である。

したがって、

$$
\alpha(e)
=
(\Delta s(e),0)
\neq
(0,0)
$$

なので、

$$
e\in\mathcal T
$$

である。

つまり、

$$
\boxed{
\text{Accounting Transaction}
\not\Rightarrow
\text{Profit/Loss Flow}
}
$$

である。

## Example: Theft or Fire

盗難や火災は、
日常語では「取引」と呼ばれない場合がある。

しかし会計上、

$$
\Delta s(e)\neq0
$$

または、

$$
f_{\mathrm{PL}}(e)\neq0
$$

となるなら、

$$
\alpha(e)\neq(0,0)
$$

なので、
ASM上はAccounting Transactionとして扱いうる。

したがって、

$$
\boxed{
\text{Accounting Transaction}
\neq
\text{commercial exchange only}
}
$$

である。

## Accounting Effect Is Not Bookkeeping Change

$\alpha(e)$ は、
経済事象の**会計的意味**である。

一方、実際に帳簿へ記録される勘定変化を、
後続モジュールでは、

$$
\boxed{
\Delta x(e)
}
$$

とする。

したがって、

$$
\boxed{
\alpha(e)
\neq
\Delta x(e)
}
$$

である。

より具体的には、

$$
\boxed{
(\Delta s,f_{\mathrm{PL}})
\to
\Delta x
}
$$

というRepresentationが必要になる。

## From Reality to Journal

ASMの基本的な前向き経路は、

$$
\boxed{
\omega
\to
\alpha
\to
\Delta x
\to
J
}
$$

である。

```mermaid
flowchart LR
    W["Economic Reality<br/>ω"]

    E["Economic Event<br/>e"]

    A["Recognized Accounting Effect<br/>α(e)=(Δs,fPL)"]

    X["Bookkeeping Change<br/>Δx"]

    J["Journal Representation<br/>J"]

    W --> E --> A --> X --> J
```

この各矢印は異なる作用である。

## Layer Separation

したがって、

$$
\boxed{
\text{Reality}
\neq
\text{Accounting Meaning}
\neq
\text{Bookkeeping Representation}
\neq
\text{Journal}
}
$$

である。

この区別はASM全体の基本原則となる。

## Recognition and Bookkeeping Are Different

会計Recognitionが決まった後で、
その意味を帳簿勘定へRepresentationする。

したがって、

$$
\boxed{
\text{Recognition}
\neq
\text{Recording}
}
$$

である。

例えば、

> Revenue 100を認識する

というSemantic judgmentと、

> Sales accountをCredit 100する

というBookkeeping representationは別の概念である。

## Information Loss

会計は現実の完全な複製ではない。

現実 $\omega$ には例えば、

- 取引の目的
- 背景
- 関係者の意図
- 品質
- 将来可能性
- 時刻の細部
- 社会的関係
- 技術的事情

など、
会計表現に残らない情報が存在する。

したがって一般に、

$$
\boxed{
\mathcal A(\omega_1)
=
\mathcal A(\omega_2)
\not\Rightarrow
\omega_1=\omega_2
}
$$

である。

異なるRealityが、
同じAccounting Representationへ写される場合がある。

## Accounting as Abstraction

この意味で、

$$
\boxed{
\mathcal A
}
$$

は、

> 現実を会計目的に応じた情報へ圧縮・抽象化する作用

でもある。

したがって、

$$
\boxed{
\text{Accounting}
\approx
\text{purpose-dependent abstraction of economic reality}
}
$$

と考えられる。

## Recognition Errors

RealityからAccounting Meaningへの変換では、
少なくとも次の誤りがありうる。

### Recognition Error

認識すべき事象を認識しない、
または認識すべきでない事象を認識する。

### Classification Error

認識した対象を誤った会計要素・勘定へ割り当てる。

### Measurement Error

認識対象の金額を誤って測定する。

これらは、

[09 — Validation](09-validation.md)

でSemantic Validityとして扱う。

## Structural Correctness Does Not Guarantee Recognition Correctness

後続モジュールで、
仕訳のStructural Constraintとして、

$$
D(J)=C(J)
$$

が登場する。

しかし、

$$
\boxed{
D(J)=C(J)
\not\Rightarrow
\text{Recognition is correct}
}
$$

である。

完全に貸借一致している仕訳でも、
そもそもRecognition / Classification / Measurementが
誤っている可能性がある。

したがって、

$$
\boxed{
\text{Structural Validity}
\neq
\text{Semantic Validity}
}
$$

である。

## Canonical Role of This Module

本モジュールの責務は、

$$
\boxed{
\omega
\to
\alpha(e)
}
$$

までである。

つまり、

- Reality
- Economic Event
- Recognition
- Classification
- Measurement
- Semantic Accounting Effect

を扱う。

一方、

$$
\boxed{
\alpha(e)
\to
\Delta x
\to
J
}
$$

は後続モジュールの責務である。

## Relationship to Other Modules

- Reporting Stock State:
  [02 — State](02-state.md)
- Semantic Stock Transition / PL Flow:
  [03 — Transition](03-transition.md)
- Account Classification:
  [04 — Accounts and Classification](04-accounts-and-classification.md)
- Bookkeeping Representation / D/C:
  [05 — Double Entry](05-double-entry.md)
- Journal / Ledger:
  [06 — Journal and Ledger](06-journal-and-ledger.md)
- Period Flow / Reporting Reconstruction:
  [07 — Period and Stock-Flow](07-period-stock-flow.md)
- Validation:
  [09 — Validation](09-validation.md)

## Core Equations

**Reality State：**

$$
\boxed{
\omega(t)\in\Omega
}
$$

**Economic Event：**

$$
\boxed{
\omega^-
\xrightarrow{e}
\omega^+
}
$$

**Accounting Recognition：**

$$
\boxed{
\mathcal A(\omega,t,\rho,\eta)
=
\text{recognized accounting information}
}
$$

**Semantic Accounting Effect：**

$$
\boxed{
\alpha(e)
=
\left(
\Delta s(e),
f_{\mathrm{PL}}(e)
\right)
}
$$

**Accounting Transaction：**

$$
\boxed{
e\in\mathcal T
\quad\Longleftrightarrow\quad
\alpha(e)\neq(0,0)
}
$$

**Layer Separation：**

$$
\boxed{
\omega
\to
\alpha
\to
\Delta x
\to
J
}
$$

## Open Questions

- Recognition時点をどのように一般的に形式化するか。
- $\mathcal A$ をBoolean RecognitionとMeasurementまで含む写像としてどう分解するか。
- 見積りの不確実性を $\eta$ にどう形式化するか。
- Probability distributionを持つMeasurementをASMへどう導入するか。
- 注記情報など、$\alpha(e)=(0,0)$ でも報告が必要な情報をどう扱うか。
- 偶発事象・コミットメントなど、Journalを生じないAccounting Informationをどうモデル化するか。
- Accounting standardの違いを $\rho$ の違いとしてどこまで表現できるか。
