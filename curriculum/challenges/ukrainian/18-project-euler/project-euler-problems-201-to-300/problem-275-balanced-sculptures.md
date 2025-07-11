---
id: 5900f4801000cf542c50ff92
title: 'Завдання 275: збалансовані скульптури'
challengeType: 1
forumTopicId: 301925
dashedName: problem-275-balanced-sculptures
---

# --description--

Визначимо збалансовану скульптуру $n$-го порядку як:

- Поліміно, що складається з $n + 1$ плиток, відомих як блоки ($n$ плиток), та основи (залишкової плитки);
- the plinth has its center at position ($x = 0$, $y = 0$);
- $y$-координати блоків більші за нуль (тому основа є унікальною найнижчою плиткою);
- the center of mass of all the blocks, combined, has $x$-coordinate equal to zero.

Під час підрахунку скульптур будь-які композиції, які є просто відбиттям навколо осі $y$, <u>не</u> зараховуються як окремі. Наприклад, знизу наведено 18 збалансованих скульптур 6-го порядку. Зауважте, що кожна пара дзеркальних зображень (на осі $y$) зараховується як одна скульптура:

<img alt="18 збалансованих скульптур шостого порядку" src="https://cdn.freecodecamp.org/curriculum/project-euler/balanced-sculptures.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Існує 964 збалансованих скульптур 10-го порядку та 360505 15-го порядку.

Скільки існує збалансованих скульптур 18-го порядку?

# --hints--

`balancedSculptures()` має повернути `15030564`.

```js
assert.strictEqual(balancedSculptures(), 15030564);
```

# --seed--

## --seed-contents--

```js
function balancedSculptures() {

  return true;
}

balancedSculptures();
```

# --solutions--

```js
// solution required
```
