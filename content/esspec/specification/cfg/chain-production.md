---
tags: [esspec/chain-production, esspec/cfg]
---

# chain production

右辺に含まれる非終端記号が 1 つだけなもの(終端記号の数は問わない)

### memo

右辺に **or** (つまり改行または `one of` など)が使われている場合、そのうち NonTerminal が 1 個のみなケースは chain production になる。

例:

```txt
// StrUnsignedDecimalLiteral は NonTerminal であるとする。

StrDecimalLiteral :::
  StrUnsignedDecimalLiteral
  + StrUnsignedDecimalLiteral
  - StrUnsignedDecimalLiteral
```

上記の production は 3 つの or について全て NonTerminal は一つのみのため、それぞれ chain production になる。次のように 3 つの production に分解して考えると一目瞭然か。

```txt
StrDecimalLiteral ::: StrUnsignedDecimalLiteral

StrDecimalLiteral ::: + StrUnsignedDecimalLiteral

StrDecimalLiteral ::: - StrUnsignedDecimalLiteral
```

また、他にも opt 等、 production にはいろいろショートハンドがあるので chain production になるものを見落としがちなことに要注意。
