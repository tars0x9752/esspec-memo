---
tags: [esspec/syntax-directed-operations, esspec/chain-production]
---

# Syntax-Directed Operations

ECMAScript のコードの文法に紐付いたアルゴリズムを記載するときに使う仕様書上の概念。

---

production (生成規則) とそれに対する algorithm steps を書いて定義される。

algorithm steps の中で `名称 of NonTerminalParseNode` のようにして使われる。

例えば `X of Y` と記載されていて `X` は Syntax-Directed Operation の名称で、`Y` はソースコード断片(NonTerminal な ParseNode)なとき、その `Parse Node Y` に対して `Hoge` という Syntax-Directed Operation を適用する、というように読む。

## chain production

明示的な定義がない場合を除き、[[chain-production]] に関しては **暗黙的に** 右辺の唯一の NonTerminal に対して同じ Syntax-Directed Operation を適用するという定義が含まれる。

例:

```txt
Syntax

  Hoge : Fuga

  Fuga : SomeNonTerminal

Runtime Semantics: SomeOperation

  Fuga : SomeNonTerminal

    1. Return null.
```

のような定義があった場合、Runtime Semantics に `Hoge` に関しての定義は書かれていないが、chain production ルールによって暗黙的に下記定義が含まれる。

```txt
  Hoge : Fuga

    1. Return SomeOperation of Fuga
```

**Memo:** production の右辺で or(改行) や `one of` あるいはその他のショートハンドなどが使われている場合に chain production を見をとしがちなので注意。(詳細は [[chain-production]] を参照。)
