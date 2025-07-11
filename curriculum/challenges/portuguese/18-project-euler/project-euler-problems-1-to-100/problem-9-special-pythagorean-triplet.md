---
id: 5900f3761000cf542c50fe88
title: 'Problema 9: Terno pitagórico especial'
challengeType: 1
forumTopicId: 302205
dashedName: problem-9-special-pythagorean-triplet
---

# --description--

Um terno pitagórico é um conjunto de três números naturais, `a` &lt; `b` &lt; `c` tal que

<div style='text-align: center;'><var>a</var><sup>2</sup> + <var>b</var><sup>2</sup> = <var>c</var><sup>2</sup></div>

Por exemplo, 3<sup>2</sup> + 4<sup>2</sup> = 9 + 16 = 25 = 5<sup>2</sup>.

Há exatamente um terno pitagórico para o qual `a` + `b` + `c` = 1000. Encontre o produto `abc` tal que `a` + `b` + `c` = `n`.

# --hints--

`specialPythagoreanTriplet(24)` deve retornar um número.

```js
assert.isNumber(specialPythagoreanTriplet(24));
```

`specialPythagoreanTriplet(24)` deve retornar 480.

```js
assert.strictEqual(specialPythagoreanTriplet(24), 480);
```

`specialPythagoreanTriplet(120)` deve retornar 49920, 55080 ou 60000.

```js
assert.oneOf(specialPythagoreanTriplet(120), [49920, 55080, 60000]);
```

`specialPythagoreanTriplet(1000)` deve retornar 31875000.

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
