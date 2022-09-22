---
tags: [esspec/chain-production, esspec/cfg]
---

# chain production

右辺に含まれる非終端記号(NonTerminal)が 1 つだけな production のこと。(終端記号の数は問わない)

(production を可能な限り因数分解した上で非終端記号の数を数えること。)

### Note

右辺に **or** (つまり改行または `one of` など)、あるいは opt などなんらかのショートハンドが使われている場合、可能な限り因数分解した上で判断する。

例:

```txt
// StrUnsignedDecimalLiteral は NonTerminal であるとする。

StrDecimalLiteral :::
  StrUnsignedDecimalLiteral
  + StrUnsignedDecimalLiteral
  - StrUnsignedDecimalLiteral
```

上記の production はパッと見だと右辺に 3 つの NonTerminal があるので chain production ではないように見えるかもしれないが、そうではない。

実際は下記のように因数分解できるため、 3 つの別々の chain production が上記の定義には含まれている。

```txt
StrDecimalLiteral ::: StrUnsignedDecimalLiteral

StrDecimalLiteral ::: + StrUnsignedDecimalLiteral

StrDecimalLiteral ::: - StrUnsignedDecimalLiteral
```

また、改行だけでなく他にも opt 等、 production にはいろいろショートハンドがあるので chain production になるものを見落としがちなことに要注意。
