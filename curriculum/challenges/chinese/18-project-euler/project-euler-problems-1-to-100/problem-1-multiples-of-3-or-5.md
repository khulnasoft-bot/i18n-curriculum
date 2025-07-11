---
id: 5900f36e1000cf542c50fe80
title: 'Problem 1: Multiples of 3 or 5'
challengeType: 1
forumTopicId: 301722
dashedName: problem-1-multiples-of-3-or-5
---

# --description--

如果我们列出所有10以下是3或5的倍数的自然数，我们会得到3，5，6和9。 这些倍数的总和是 23。

在提供的参数值 `number` 下找到所有 3 或 5 的倍数之和。

# --hints--

`multiplesOf3Or5(10)` should return a number.

```js
assert.isNumber(multiplesOf3Or5(10));
```

`multiplesOf3Or5(49)` should return 543.

```js
assert.strictEqual(multiplesOf3Or5(49), 543);
```

`multiplesOf3Or5(1000)` should return 233168.

```js
assert.strictEqual(multiplesOf3Or5(1000), 233168);
```

`multiplesOf3Or5(8456)` should return 16687353.

```js
assert.strictEqual(multiplesOf3Or5(8456), 16687353);
```

`multiplesOf3Or5(19564)` should return 89301183.

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
