---
id: 5900f4301000cf542c50ff42
title: 'Завдання 196: прості трійки'
challengeType: 1
forumTopicId: 301834
dashedName: problem-196-prime-triplets
---

# --description--

Побудуйте трикутник з усіх натуральних чисел таким чином:

$$\begin{array}{rrr}   &  1 \\\\
  &  \color{red}{2} &  \color{red}{3} \\\\   &  4 & \color{red}{5} &  6 \\\\
  &  \color{red}{7} &  8 &  9 & 10 \\\\   & \color{red}{11} & 12 & \color{red}{13} & 14 & 15  \\\\
  & 16 & \color{red}{17} & 18 & \color{red}{19} & 20 & 21 \\\\   & 22 & \color{red}{23} & 24 & 25 & 26 & 27 & 28 \\\\
  & \color{red}{29} & 30 & \color{red}{31} & 32 & 33 & 34 & 35 & 36 \\\\   & \color{red}{37} & 38 & 39 & 40 & \color{red}{41} & 42 & \color{red}{43} & 44 & 45 \\\\
  & 46 & \color{red}{47} & 48 & 49 & 50 & 51 & 52 & \color{red}{53} & 54 & 55 \\\\   & 56 & 57 & 58 & \color{red}{59} & 60 & \color{red}{61} & 62 & 63 & 64 & 65 & 66 \\\\
  & \cdots \end{array}$$

Each positive integer has up to eight neighbors in the triangle.

A set of three primes is called a prime triplet if one of the three primes has the other two as neighbors in the triangle.

Наприклад, у другому ряді прості числа 2 і 3 є елементами простої трійки.

Якщо розглянути восьмий рядок, то він містить два простих числа, які є елементами простої трійки, тобто 29 та 31. Якщо розглянути дев’ятий рядок, то він містить лише одне просте число, яке є елементом простої трійки: 37.

Визначимо $S(n)$ як суму простих чисел у рядку №$n$, які є елементами будь-якої простої трійки. Тоді $S(8) = 60$ та $S(9) = 37$.

Дано, що $S(10000) = 950007619$.

Знайдіть $S(5678027) + S(7208785)$.

# --hints--

`primeTriplets()` має повернути `322303240771079940`.

```js
assert.strictEqual(primeTriplets(), 322303240771079940);
```

# --seed--

## --seed-contents--

```js
function primeTriplets() {

  return true;
}

primeTriplets();
```

# --solutions--

```js
// solution required
```
