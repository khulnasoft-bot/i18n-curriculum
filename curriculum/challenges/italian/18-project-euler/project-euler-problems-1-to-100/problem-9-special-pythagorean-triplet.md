---
id: 5900f3761000cf542c50fe88
title: 'Problema 9: terna pitagorica speciale'
challengeType: 1
forumTopicId: 302205
dashedName: problem-9-special-pythagorean-triplet
---

# --description--

Una terna pitagorica è una serie di tre numeri naturali, `a` &lt; `b` &lt; `c` tali per cui

<div style='text-align: center;'><var>a</var><sup>2</sup> + <var>b</var><sup>2</sup> = <var>c</var><sup>2</sup></div>

Ad esempio, 3<sup>2</sup> + 4<sup>2</sup> = 9 + 16 = 25 = 5<sup>2</sup>.

Esiste esattamente una terna pitagorica per cui `a` + `b` + `c` = 1000. Trova il prodotto `abc` tale che `a` + `b` + `c` = `n`.

# --hints--

`specialPythagoreanTriplet(24)` dovrebbe restituire un numero.

```js
assert.isNumber(specialPythagoreanTriplet(24));
```

`specialPythagoreanTriplet(24)` dovrebbe restituire 480.

```js
assert.strictEqual(specialPythagoreanTriplet(24), 480);
```

`specialPythagoreanTriplet(120)` dovrebbe restituire 49920, 55080 o 60000.

```js
assert.oneOf(specialPythagoreanTriplet(120), [49920, 55080, 60000]);
```

`specialPythagoreanTriplet(1000)` dovrebbe restituire 31875000.

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
