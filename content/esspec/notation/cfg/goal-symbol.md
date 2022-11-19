---
tags: [esspec/goal-symbol, esspec/cfg]
---

# goal symbol

その文法によって一番最初に生成される非終端記号。CFG の文脈で start symbol (開始記号)と呼ばれてるもの相当。

(おそらく bottom up parser からみたらそれは goal なので goal symbol と記載されていると思われる。)

なお ecma262 における goal symbol についての定義は Java の仕様書からそのまま流用されたもの。

> ecma262 の 5.1.1 の Context-Free Grammars の文章について、`chain production` 以外はどうやら Java の仕様書のコピペ。
>
> - [ecma262](https://tc39.es/ecma262/#sec-context-free-grammars)
> - [Java 18](https://docs.oracle.com/javase/specs/jls/se18/html/jls-2.html)
> - [Java 1.0](http://titanium.cs.berkeley.edu/doc/java-langspec-1.0/2.doc.html)