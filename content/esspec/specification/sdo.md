---
tags: [esspec/syntax-directed-operations]
---

# Syntax-Directed Operations

ECMAScript のコードの文法に紐付いたアルゴリズムを記載するときに使う仕様書上の概念。

生成規則とそれに対する algorithm steps を書いて定義される。

algorithm steps の中で `SDOの名称 of NonTerminalなParseNode` のようにして使われる。

例えば `X of Y` と記載されていて `X` は Syntax-Directed Operation の名称で、`Y` はソースコード断片(非終端記号な Parse Node)なとき、その `Parse Node Y` に対して `Hoge` という Syntax-Directed Operation を適用する、というように読む。
