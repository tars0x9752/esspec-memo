---
tags: [esspec/abstract-operations]
order: -997
---

# Abstract Operations

汎用的なアルゴリズム断片を関数形式にして使い回せるようにした仕様書上の概念。アルゴリズム定義に使われる。抽象操作。

あくまで仕様書上のみの概念で実際の ECMAScript 言語の関数ではないが、仕様書上では関数ライクに振る舞い、任意の引数と返り値を持つ。

なお、仕様書上のみの概念ではあるものの、JS による実装がライブラリとして公開されていたりする。(polyfill 作成時のリファレンスなどの役目か)

JS による実装: https://github.com/ljharb/es-abstract
