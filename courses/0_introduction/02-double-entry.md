# 第2講 — 複式簿記とは

## 1. この講座で学ぶこと

簿記上の取引が企業の複数の会計的側面を同時に変化させることと、複式簿記の「二面性」を学ぶ。

## 2. 通常の簿記的説明

複式簿記は、取引を原因と結果、増加と減少など複数の側面から記録する。日常語の取引でなくても、盗難や火災のように会計要素を変化させれば簿記上の取引になる。

## 3. 関連するASM

- [01 — Reality and Recognition](../../theory/01-reality-and-recognition.md)
- [02 — State](../../theory/02-state.md)
- [03 — Transition](../../theory/03-transition.md)
- [05 — Double Entry](../../theory/05-double-entry.md)

## 4. ASMによる説明

取引は、認識された状態変化 $\Delta s$ を生じさせる事象である。二面性は「一増一減」ではなく、有効状態から有効状態へ移る制約保存変化として捉える。

## 5. 数学モデル

$$
s^+=s^-+\Delta s
$$

$$
\Delta A-\Delta L-\Delta E=0
$$

$$
e\in\mathcal T\Longleftrightarrow\Delta x(e)\neq0
$$

## 6. 具体例

現金100で備品を購入すると、

$$
\Delta\mathrm{Cash}=-100,
\qquad
\Delta\mathrm{Equipment}=+100
$$

で、$\Delta A=0$ となる。銀行から100を借りれば、$\Delta A=+100$、$\Delta L=+100$ となり、両方が増えても制約は保存される。

## 7. 現行ASMで説明できるか

**判定:** Yes

状態遷移と制約保存によって、入門段階の取引の二面性を統一して説明できる。

## 8. ASMへの新しい洞察

「複式」は必ず2勘定という意味ではなく、会計的側面を整合した記録へ束ねる構造である。

## 9. Theory更新候補

なし。複式簿記を制約保存遷移の記録体系とみなす解釈は [03 — Transition](../../theory/03-transition.md) に反映済み。

## 10. 未解決問題

収益・費用を含む Flow 記録と Stock 制約の接続を、複式簿記の定義にどこまで含めるか。
