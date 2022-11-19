# Mathematical Operations

[ecma262 - Mathematical Operations](https://tc39.es/ecma262/#sec-mathematical-operations)

## 仕様書中に登場する数値の種類

仕様書中に登場する数値は大きく分けて次の4種類に分類される。

### **Mathematical values**

任意の実数。仕様書中の数値型のデフォルトがこれ。実世界のコンピューターでは任意の実数全てを正確に表現でき**ない**ことに注意。あくまで仕様書上の概念。

よく `MV` 等と略される。

仕様書中に登場する `integer` という単語は何か特別に明示されない限りは `MV` における整数である。(その場合 `integer` は `Number` や `BigInt` ではない。)

### **Extended mathematical values**

$+\infty$, $-\infty$ を含めた `Mathematical values`

### **Numbers**

[IEEE 754-2019](https://ja.wikipedia.org/wiki/IEEE_754) [倍精度浮動小数点数](https://ja.wikipedia.org/wiki/%E5%80%8D%E7%B2%BE%E5%BA%A6%E6%B5%AE%E5%8B%95%E5%B0%8F%E6%95%B0%E7%82%B9%E6%95%B0) である `ECMAScript language values`

Tips:

- 倍精度浮動小数点数における整数の最大値は $2^{53}-1$
  - `Numbers.MAX_SAFE_INTEGER` でとれる。
- `NaN (Not-a-Number)` や `+0`, `-0`, `+∞`, `-∞` 等は JS 固有の概念ではなく IEEE 754-2019 で定義されているもの。
- 勘違いしやすいが、`NaN (Not-a-Number)` も `Number` である。

### **BigInts**

任意の整数を表現する `ECMAScript language values`

いわゆる多倍長整数。

:::{.sticky-note}
**TL;DR:**

仕様書オンリーなのが `(Extended) Mathematical values`

実世界で取り回す場合は `Numbers` か `BigInts`
:::

## 下付き文字

仕様書中に登場する数値には次の下付き文字が付く。

また下付き文字なしの場合は `(Extended) Mathematical Values` を表す。(`NaN` を除く。`NaN` は下付き文字が何もつかないが `Number`)

- $_\mathbb{F}$: `Number`
- $_\mathbb{Z}$: `BigInt`

## Conversions

- `Number` への変換
  - $\mathbb{F}(x)$
  - または `the Number value for x`
- `BigInt` への変換
  - $\mathbb{Z}(x)$
  - または `the BigInt value for x` 
- `Mathematical Values` への変換
  - $\mathbb{R}(x)$
  - または `the mathematical value of x`
  - non finite な Number の `Mathematical Values` への変換は未定義。
  - ちなみに `MV of` と記載される場合もあり、その場合の `MV` は [[ss]] あるいは [[rs]] 等として具体的なアルゴリズムがどこかに定義されている。

## 特殊な Number

特殊な Number について下記に補足する。

### **NaN**

IEEE 754-2019 倍精度浮動小数点数における NaN (Not-a-Number)

IEEE 754-2019 倍精度浮動小数点数においては指数部が `7FF0` で仮数部が `0` ではないものは全て `NaN` であり、つまり 2 進数的には $2^{53}-2$ 種類の `NaN` があるが、ECMAScript においてそれらは区別されない。

また、区別はされないことに加えそれぞれが `equal` になることもない。

`NaN == NaN` や `NaN === NaN` は `false` である。

ただし、`SameValue` 判定ではそれぞれ同値として扱われ、例えば `Object.is(NaN, NaN)` 等は `true` である。

```sh
# 例

7FF0 0000 0000 0001 # NaN A
7FF0 0000 0000 0002 # NaN B
7FF0 0000 0000 0003 # NaN C

# ここで、"NaN A", "NaN B", "NaN C" それぞれは2進数的には別の値だが、ECMAScript では区別されない。
# 区別されないが equal でもないことに注意。
```

### **Infinite**

$+\infty_\mathbb{F}$ および $-\infty_\mathbb{F}$

コード的には `+Infinity` `-Infinity` によってそれぞれ生成される。

### **finite**

$+\infty_\mathbb{F}$, $-\infty_\mathbb{F}$ あるいは `NaN` ではない `Number` 型全てのことを `finite numbers` と呼ぶ。(文脈によっては `finite values` や `finite Number values`等と呼ばれることもある。)

### **not finite または non finite**

`finite` ではない値は `not finite` や `non-finite` 等と呼ばれる。

具体的には $+\infty_\mathbb{F}$, $-\infty_\mathbb{F}$, `NaN` が `not finite` に該当する。