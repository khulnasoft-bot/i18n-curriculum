---
id: 5900f4891000cf542c50ff9b
title: 'Завдання 284: незмінні квадрати'
challengeType: 1
forumTopicId: 301935
dashedName: problem-284-steady-squares
---

# --description--

Тризначне число 376 в десятковій системі є прикладом чисел зі спеціальною властивістю: його квадрат закінчується тими ж цифрами (${376}^2 = 141376$). Назвемо такі числа незмінними квадратами.

Незмінні квадрати існують також і в інших системах числення. В системі числення з основою 14, тризначне число $c37$ також є незмінним квадратом: $c37^2 = aa0c37$, а сума його цифр в тій же системі дорівнює $c+3+7=18$. Літери $a$, $b$, $c$ та $d$ використовують для позначення цифр 10, 11, 12 та 13 відповідно, так само як і в шістнадцятковій системі числення.

За умови $1 ≤ n ≤ 9$ сума цифр всіх $n$-значних незмінних квадратів в системі числення з основою 14 дорівнює $2d8$ (582 в десятковій системі). Незмінні квадрати з нулями на початку заборонені.

Знайдіть суму цифр всіх $n$-значних незмінних квадратів в системі числення з основою 14, якщо $1 ≤ n ≤ 10000$ (у десятковій системі) та надайте відповідь у вигляді рядка в системі числення з основою 14, використовуючи нижній регістр за потреби.

# --hints--

`steadySquares()` має повернути рядок.

```js
assert.isString(steadySquares());
```

`steadySquares()` має повернути рядок `5a411d7b`.

```js
assert.strictEqual(steadySquares(), '5a411d7b');
```

# --seed--

## --seed-contents--

```js
function steadySquares() {

  return true;
}

steadySquares();
```

# --solutions--

```js
// solution required
```
