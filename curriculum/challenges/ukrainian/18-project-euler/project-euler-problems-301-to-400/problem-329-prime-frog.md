---
id: 5900f4b51000cf542c50ffc8
title: 'Завдання 329: проста жаба'
challengeType: 1
forumTopicId: 301986
dashedName: problem-329-prime-frog
---

# --description--

У Сьюзен є проста жаба.

Її жаба стрибає по 500 квадратам, пронумерованими від 1 до 500.

Вона може стрибнути лише на один квадрат ліворуч або праворуч з однаковою ймовірністю і не може вистрибнути з діапазону [1;500]. (Якщо вона опиниться на будь-якому з кінців, то автоматично перестрибне на єдиний доступний квадрат під час наступного ходу.)

Якщо вона знаходиться на квадраті з простим числом, вона квакає «P» (ПРОСТЕ) з ймовірністю $\frac{2}{3}$ або «N» (НЕПРОСТЕ) з ймовірністю $\frac{1}{3}$ перед тим, як перестрибнути на наступний квадрат. Коли вона опиняється на квадраті з числом, яке не є простим, вона квакає «P» з ймовірністю $\frac{1}{3}$ або «N» з ймовірністю $\frac{2}{3}$ перед тим, як перестрибнути на наступний квадрат.

Припустимо, що початкова позиція жаби випадкова з однаковою ймовірністю для кожного квадрату, і що Сьюзен слухає перші 15 квакань. Яка ймовірність того, що Сьюзен почує таку послідовність: PPPPNNPPPNPPNPN?

Надайте відповідь у вигляді дробу `p/q` в скороченій формі.

# --hints--

`primeFrog()` має повернути рядок.

```js
asset.isString(primeFrog());
```

`primeFrog()` має повернути рядок `199740353/29386561536000`.

```js
assert.strictEqual(primeFrog(), '199740353/29386561536000');
```

# --seed--

## --seed-contents--

```js
function primeFrog() {

  return true;
}

primeFrog();
```

# --solutions--

```js
// solution required
```
