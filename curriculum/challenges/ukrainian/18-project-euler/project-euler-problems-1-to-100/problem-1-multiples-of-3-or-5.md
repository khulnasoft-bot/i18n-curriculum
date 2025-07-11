---
id: 5900f36e1000cf542c50fe80
title: 'Завдання 1: кратні чисел 3 та 5'
challengeType: 1
forumTopicId: 301722
dashedName: problem-1-multiples-of-3-or-5
---

# --description--

Якщо ми запишемо усі натуральні числа до 10, кратних 3 та 5, то отримаємо 3, 5, 6 та 9. Сумою цих кратних є 23.

Знайдіть суму всіх чисел кратних 3 та 5, які менші певного заданого значення `number`.

# --hints--

`multiplesOf3Or5(10)` має повернути число.

```js
assert.isNumber(multiplesOf3Or5(10));
```

`multiplesOf3Or5(49)` має повернути 543.

```js
assert.strictEqual(multiplesOf3Or5(49), 543);
```

`multiplesOf3Or5(1000)` має повернути 233168.

```js
assert.strictEqual(multiplesOf3Or5(1000), 233168);
```

`multiplesOf3Or5(8456)` має повернути 16687353.

```js
assert.strictEqual(multiplesOf3Or5(8456), 16687353);
```

`multiplesOf3Or5(19564)` має повернути 89301183.

```js
assert.strictEqual(multiplesOf3Or5(19564), 89301183);
```

# --seed--

## --seed-contents--

```js
function multiplesOf3Or5(number) {

  return true;
}

multiplesOf3Or5(1000);
```

# --solutions--

```js
const multiplesOf3Or5 = (number) => {
  var total = 0;

  for(var i = 0; i < number; i++) {
    if(i % 3 == 0 || i % 5 == 0) {
      total += i;
    }
  }
  return total;
};
```
