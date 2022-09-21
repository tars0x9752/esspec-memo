---
tags: [cfg, esspec/cfg, esspec/chain-production, esspec/goal-symbol]
---

# Context-Free Grammars

文脈自由文法

例: 「数字とは 0, 1, 2, ..., のいずれかである」や「小数とは 符号, 数字の連続, 小数点, 数字の連続...」, のような文法の定義。その定義ひとつひとつを production (生成規則あるいは導出規則など) と呼ぶ。

- 終端記号(Terminal symbol): それ以上分解できないもの。
- 非終端記号(NonTerminal symbol): 非終端記号と終端記号の任意の組み合わせで定義されるもの。構文変数。

### ecma262 and CFG

ecma262 上では (E)BNF ライクな独自の記法が構文・字句文法の記述時に使われる。

大きく分けて Syntactic Grammar, Numeric String Grammar, Lexical and RegExp Grammars の 3 種類存在する。(また、[[sdo]] の定義中でその 3 種類が使われる可能性もある)

**Punctuation の違い**

- Syntactic Grammar は `:`
- Lexical and RegExp Grammars は `::`
- Numeric String Grammar は `:::`

### terms/words

#### chain production

![[chain-production]]

#### goal symbol

![[goal-symbol]]

### 豆知識

ecma262 の 5.1.1 の Context-Free Grammars の文章について、`chain production` 以外はどうやら Java の仕様書のコピペ。

- [ecma262](https://tc39.es/ecma262/#sec-context-free-grammars)
- [Java 18](https://docs.oracle.com/javase/specs/jls/se18/html/jls-2.html)
- [Java 1.0](http://titanium.cs.berkeley.edu/doc/java-langspec-1.0/2.doc.html)
