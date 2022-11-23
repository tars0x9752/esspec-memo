---
tags: [esspec/production, esspec/cfg]
order: -1
---

# Production

[ecma262 - nonterminal-symbols-and-productions](https://tc39.es/ecma262/#sec-nonterminal-symbols-and-productions)

非終端記号の定義。日本語では生成規則などと呼ばれたりする。

左辺に定義対象の非終端記号、右辺には非終端記号と終端記号の任意の組み合わせ、左辺と右辺の間には `Punctuation` 記号、という記法で書かれる。

`Punctuation` 記号は1つ以上のコロン (`:`) が使われる。コロンの数の違いについては後述。

なお、右辺の改行は `or` を意味する。

また、右辺には再帰的に左辺の非終端記号が登場する場合もある。

## 終端記号 - Terminal symbol

それ以上分解できないシンボル。等幅フォントの場合はその表記文字通りのトークンを表す。

## 非終端記号 - NonTerminal symbol

非終端記号と終端記号の任意の組み合わせで定義されるシンボル。

(雑に言うと、構文を表す変数。)

## Punctuation

- Syntactic Grammar は `:`
- Lexical and RegExp Grammars は `::`
- Numeric String Grammar は `:::`

## Todo

- [ ] opt とか Grammatical Parameters についての補足を書く
- [ ] await とか yield についての補足を書く

