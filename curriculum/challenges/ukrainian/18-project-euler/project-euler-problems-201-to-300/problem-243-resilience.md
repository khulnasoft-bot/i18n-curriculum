---
id: 5900f4601000cf542c50ff73
title: 'Завдання 243: стійкість'
challengeType: 1
forumTopicId: 301890
dashedName: problem-243-resilience
---

# --description--

Додатний дріб, у якого чисельник менший за знаменник, називається правильним.

Для будь-якого знаменника $d$ існує $d−1$ правильних дробів. Наприклад, за умови $d = 12$:

$$\frac{1}{12}, \frac{2}{12}, \frac{3}{12}, \frac{4}{12}, \frac{5}{12}, \frac{6}{12}, \frac{7}{12}, \frac{8}{12}, \frac{9}{12}, \frac{10}{12}, \frac{11}{12}$$

We shall call a fraction that cannot be canceled down a resilient fraction.

Також визначимо стійкість знаменника $R(d)$ як відношення стійких правильних дробів до загальної кількості правильних дробів із цим знаменником. Наприклад, $R(12) = \frac{4}{11}$.

Фактично, $d = 12$ є найменшим знаменником зі стійкістю $R(d) &lt; \frac{4}{10}$.

Знайдіть найменший знаменник $d$ зі стійкістю $R(d) &lt; \frac{15\\,499}{94\\,744}$.

# --hints--

`resilience()` має повернути `892371480`.

```js
assert.strictEqual(resilience(), 892371480);
```

# --seed--

## --seed-contents--

```js
function resilience() {

  return true;
}

resilience();
```

# --solutions--

```js
// solution required
```
