---
id: 5900f4621000cf542c50ff74
title: 'Завдання 245: співстійкість'
challengeType: 1
forumTopicId: 301892
dashedName: problem-245-coresilience
---

# --description--

We shall call a fraction that cannot be canceled down a resilient fraction.

Також визначимо стійкість знаменника $R(d)$ як відношення стійких правильних дробів до загальної кількості правильних дробів із цим знаменником. Наприклад, $R(12) = \frac{4}{11}$.

Стійкість числа $d > 1$ становить $\frac{φ(d)}{d − 1}$, де $φ$ є функцією Ейлера.

Потім визначимо співстійкість числа $n > 1$ як $C(n) = \frac{n − φ(n)}{n − 1}$.

Співстійкість простого числа $p$ дорівнює $C(p) = \frac{1}{p − 1}$.

Знайдіть суму всіх складених цілих чисел $1 &lt; n ≤ 2 × {10}^{11}$, за яких $C(n)$ є аліквотним дробом.

# --hints--

`coresilience()` має повернути `288084712410001`.

```js
assert.strictEqual(coresilience(), 288084712410001);
```

# --seed--

## --seed-contents--

```js
function coresilience() {

  return true;
}

coresilience();
```

# --solutions--

```js
// solution required
```
