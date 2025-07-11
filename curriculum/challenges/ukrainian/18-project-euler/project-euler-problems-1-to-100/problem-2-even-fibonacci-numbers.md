---
id: 5900f36e1000cf542c50fe81
title: 'Завдання 2: парні числа Фібоначчі'
challengeType: 1
forumTopicId: 301838
dashedName: problem-2-even-fibonacci-numbers
---

# --description--

Кожен новий член послідовності Фібоначчі дорівнює сумі двох попередніх членів. Якщо почати з 1 та 2, то першими десятьма членами послідовності будуть:

<div style='text-align: center;'>1, 2, 3, 5, 8, 13, 21, 34, 55, 89, ...</div>

Розглядаючи члени послідовності Фібоначчі, які не перевищують певне число (`n`), знайдіть суму парних членів.

# --hints--

`fiboEvenSum(10)` має повернути число.

```js
assert.isNumber(fiboEvenSum(10));
```

Функція має повернути парне значення.

```js
assert.equal(fiboEvenSum(10) % 2 === 0, true);
```

Функція має підсумувати парні члени послідовності Фібоначчі: `fiboEvenSum(8)` має повернути 10.

```js
assert.strictEqual(fiboEvenSum(8), 10);
```

`fiboEvenSum(10)` має повернути 10.

```js
assert.strictEqual(fiboEvenSum(10), 10);
```

`fiboEvenSum(34)` має повернути 44.

```js
assert.strictEqual(fiboEvenSum(34), 44);
```

`fiboEvenSum(60)` має повернути 44.

```js
assert.strictEqual(fiboEvenSum(60), 44);
```

`fiboEvenSum(1000)` має повернути 798.

```js
assert.strictEqual(fiboEvenSum(1000), 798);
```

`fiboEvenSum(100000)` має повернути 60696.

```js
assert.strictEqual(fiboEvenSum(100000), 60696);
```

`fiboEvenSum(4000000)` має повернути 4613732.

```js
assert.strictEqual(fiboEvenSum(4000000), 4613732);
```

# --seed--

## --seed-contents--

```js
function fiboEvenSum(n) {

  return true;
}
```

# --solutions--

```js
const fiboEvenSum = (number) => {
  if (number <= 1) {
    return 0;
  } else {
    let evenSum = 0,
      prevFibNum = 1,
      fibNum = 2; // According to problem description our Fibonacci series starts with 1, 2
    for (let i = 2; fibNum <= number; i++) {
      if (fibNum % 2 == 0) {
        evenSum += fibNum;
      }
      [prevFibNum, fibNum] = [fibNum, prevFibNum + fibNum];
    }
    return evenSum;
  }
};
```
