---
tags: [esspec/static-semantics]
order: -994
---

# Static Semantics

[ecma262 - Static Semantics](https://tc39.es/ecma262/#sec-static-semantic-rules)

主にコードの静的な解析関連で、例えばコードが ECMAScript として正しいかとか、コードを見てこれはこういう意味をもったコードだと判定したりといった Static な Semantics をもったアルゴリズムのこと。[[cfg]] だけでは表現しきれないルールのために用いられる。

略称は `SS`

:::{.sticky-note}
**TL;DR:**

アルゴリズム名の接頭辞に `Static Semantics:` とついていたら Runtime ではなくコードの静的な解析とかに関連するアルゴリズムだと考えればよい。
:::

関連: [[rs]]
