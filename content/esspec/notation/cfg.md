---
tags: [cfg, esspec/cfg, esspec/chain-production, esspec/goal-symbol]
order: -998
---

# Context-Free Grammars

[ecma262 - Context-Free Grammars](https://tc39.es/ecma262/#sec-context-free-grammars)

日本語では文脈自由文法などと呼ばれる。略称は CFG.

例: 「数字とは 0, 1, 2, ..., のいずれかである」や「小数とは 符号, 数字の連続, 小数点, 数字の連続...」, のような文法の定義。その定義ひとつひとつを [[production]] (生成規則) と呼ぶ。

→ 関連: [[production]]

## ecma262 and CFG

ecma262 上では (E)BNF ライクな独自の記法が構文・字句文法の記述時に使われる。

大きく分けて Syntactic Grammar, Numeric String Grammar, Lexical and RegExp Grammars の 3 種類存在する。(また、[[sdo]] の定義中でその 3 種類が使われる可能性もある)

## terms/words

- [[production]]
- [[chain-production]]
- [[goal-symbol]]

## 豆知識

ecma262 の 5.1.1 の Context-Free Grammars の文章について、`chain production` 以外はどうやら Java の仕様書のコピペ。

- [ecma262](https://tc39.es/ecma262/#sec-context-free-grammars)
- [Java 18](https://docs.oracle.com/javase/specs/jls/se18/html/jls-2.html)
- [Java 1.0](http://titanium.cs.berkeley.edu/doc/java-langspec-1.0/2.doc.html)
