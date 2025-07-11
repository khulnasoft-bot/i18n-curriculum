---
id: 5900f4e81000cf542c50fffb
title: 'Завдання 380: дивовижні лабіринти!'
challengeType: 1
forumTopicId: 302044
dashedName: problem-380-amazing-mazes
---

# --description--

Лабіринт $m×n$ — це прямокутна сітка $m×n$ зі стінками, розміщеними між клітинками сітки таким чином, що існує лише один шлях від верхнього лівого квадрата до будь-якого іншого квадрата. Нижче наведено приклади лабіринту 9×12 та лабіринту 15×20:

<img alt="Лабіринт 9х12 і лабіринт 15х20" src="https://cdn.freecodecamp.org/curriculum/project-euler/amazing-mazes.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Нехай $C(m, n)$ буде кількістю різних лабіринтів $m×n$. Лабіринти, які можна утворити шляхом обертання та відбиття від іншого лабіринту, вважаються різними.

Можна довести, що $C(1, 1) = 1$, $C(2, 2) = 4$, $C(3, 4) = 2415$ та $C(9, 12) = 2.5720\mathrm{e}\\,46$ (в експоненційному записі заокруглено до п’яти знаків після коми).

Знайдіть $C(100, 500)$ та надайте відповідь у вигляді рядка в експоненційному записі, заокругливши до п’яти знаків після коми.

При цьому використайте e в нижньому регістрі, щоб розділити мантису та показник степеня. Наприклад, якщо відповідь дорівнює 1234567891011, то форматом буде рядок `1.2346e12`.

# --hints--

`amazingMazes()` має повернути рядок.

```js
asset.isString(amazingMazes());
```

`amazingMazes()` має повернути рядок `6.3202e25093`.

```js
assert.strictEqual(amazingMazes(), '6.3202e25093');
```

# --seed--

## --seed-contents--

```js
function amazingMazes() {

  return true;
}

amazingMazes();
```

# --solutions--

```js
// solution required
```
