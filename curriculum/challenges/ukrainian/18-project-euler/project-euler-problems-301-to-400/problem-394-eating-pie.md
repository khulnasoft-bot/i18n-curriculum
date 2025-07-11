---
id: 5900f4f71000cf542c510009
title: 'Завдання 394: споживання пирога'
challengeType: 1
forumTopicId: 302059
dashedName: problem-394-eating-pie
---

# --description--

Джефф їсть пиріг незвично.

Пиріг має круглу форму. Перший розріз пирога він робить по радіусу.

Поки залишається принаймні дана частка пирога $F$, він виконує таку процедуру:

- He makes two slices from the pie center to any point of what is remaining of the pie border, any point on the remaining pie border equally likely. Це розділить решту пирога на три частини.
- Йдучи з початкового розрізу проти годинникової стрілки, він бере перші два куски пирога та з’їдає їх.

Коли залишається менше частки пирога $F$, він не повторює цю процедуру. Натомість він з’їдає все, що залишилось.

<img alt="анімація процедури нарізання пирога" src="https://cdn.freecodecamp.org/curriculum/project-euler/eating-pie.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Нехай $E(x)$, де $x ≥ 1$, буде очікуваною кількістю разів, коли Джефф повторює процедуру вище за умови $F = \frac{1}{x}$. Можна довести, що $E(1) = 1$, $E(2) ≈ 1.2676536759$ та $E(7.5) ≈ 2.1215732071$.

Знайдіть $E(40)$, округливши до 10 знаків після коми.

# --hints--

`eatingPie()` має повернути `3.2370342194`.

```js
assert.strictEqual(eatingPie(), 3.2370342194);
```

# --seed--

## --seed-contents--

```js
function eatingPie() {

  return true;
}

eatingPie();
```

# --solutions--

```js
// solution required
```
