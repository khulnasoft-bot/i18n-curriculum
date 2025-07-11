---
id: 5900f3761000cf542c50fe88
title: '問題 9: 特殊なピタゴラスの三つ組数'
challengeType: 1
forumTopicId: 302205
dashedName: problem-9-special-pythagorean-triplet
---

# --description--

ピタゴラスの三つ組数とは、次の式を満たし、`a` &lt; `b` &lt; `c` である 3 つの自然数の集合です。

<div style='text-align: center;'><var>a</var><sup>2</sup> + <var>b</var><sup>2</sup> = <var>c</var><sup>2</sup></div>

例えば、3<sup>2</sup> + 4<sup>2</sup> = 9 + 16 = 25 = 5<sup>2</sup> です。

`a` + `b` + `c` = 1000 となるピタゴラスの三つ組数が 1 つだけ存在します。 `a` + `b` + `c` = `n` となるような積 `abc` を求めなさい。

# --hints--

`specialPythagoreanTriplet(24)` は数値を返す必要があります。

```js
assert.isNumber(specialPythagoreanTriplet(24));
```

`specialPythagoreanTriplet(24)` は 480 を返す必要があります。

```js
assert.strictEqual(specialPythagoreanTriplet(24), 480);
```

`specialPythagoreanTriplet(120)` は 49920, 55080, 60000 のいずれかを返す必要があります。

```js
assert.oneOf(specialPythagoreanTriplet(120), [49920, 55080, 60000]);
```

`specialPythagoreanTriplet(1000)` は 31875000 を返す必要があります。

```js
assert.strictEqual(specialPythagoreanTriplet(1000), 31875000);
```

# --seed--

## --seed-contents--

```js
function specialPythagoreanTriplet(n) {
 let sumOfabc = n;

 return true;
}

specialPythagoreanTriplet(1000);
```

# --solutions--

```js
function specialPythagoreanTriplet(n) {
  for (let a = 1; a <= n / 2; a++) {
    for (let b = a + 1; b <= n / 2; b++) {
      const c = Math.sqrt(a * a + b * b);

      if ((a + b + c) % n == 0) {
        const factor = n / (a + b + c);

        return (a * b * c) * (factor ** 3);
      }
    }
  }
}
```
