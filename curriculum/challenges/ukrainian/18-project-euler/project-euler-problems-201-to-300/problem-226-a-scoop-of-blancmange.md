---
id: 5900f4511000cf542c50ff62
title: 'Завдання 226: крива бланманже'
challengeType: 1
forumTopicId: 301869
dashedName: problem-226-a-scoop-of-blancmange
---

# --description--

Крива бланманже — це множина точок ($x$,$y$) за умов $0 ≤ x ≤ 1$ та $\displaystyle y = \sum_{n = 0}^{\infty} \frac{s(2^nx)}{2^n}$, де $s(x)$ є відстанню від $x$ до найближчого цілого числа.

Площа під кривою бланманже дорівнює $\frac{1}{2}$, як показано на рисунку нижче рожевим.

<img alt="рисунок кривої бланманже з колом С" src="https://cdn.freecodecamp.org/curriculum/project-euler/a-scoop-of-blancmange.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Let $C$ be the circle with center ($\frac{1}{4}$,$\frac{1}{2}$) and radius $\frac{1}{4}$, shown in black in the diagram.

Яка площа під кривою бланманже обмежена колом $C$? Дайте відповідь, заокруглену до восьми знаків після коми у форматі 0.abcdefgh

# --hints--

`scoopOfBlancmange()` має повернути `0.11316017`.

```js
assert.strictEqual(scoopOfBlancmange(), 0.11316017);
```

# --seed--

## --seed-contents--

```js
function scoopOfBlancmange() {

  return true;
}

scoopOfBlancmange();
```

# --solutions--

```js
// solution required
```
