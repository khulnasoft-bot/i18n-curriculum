---
id: 5900f36f1000cf542c50fe82
title: '最大质因数'
challengeType: 1
forumTopicId: 301952
dashedName: problem-3-largest-prime-factor
---

# --description--

13195的质因数是5、7、13和29。

求给出数 `number` 的最大质因数是多少?

# --hints--

`largestPrimeFactor(2)` 应该返回一个数字。

```js
assert.isNumber(largestPrimeFactor(2));
```

`largestPrimeFactor(2)` 应该返回 2。

```js
assert.strictEqual(largestPrimeFactor(2), 2);
```

`largestPrimeFactor(3)` 应该返回 3。

```js
assert.strictEqual(largestPrimeFactor(3), 3);
```

`largestPrimeFactor(5)` 应该返回 5。

```js
assert.strictEqual(largestPrimeFactor(5), 5);
```

`largestPrimeFactor(7)` 应该返回 7。

```js
assert.strictEqual(largestPrimeFactor(7), 7);
```

`largestPrimeFactor(8)` 应该返回 2。

```js
assert.strictEqual(largestPrimeFactor(8), 2);
```

`largestPrimeFactor(13195)` 应该返回 29。

```js
assert.strictEqual(largestPrimeFactor(13195), 29);
```

`largestPrimeFactor(600851475143)` 应该返回 6857。

```js
assert.strictEqual(largestPrimeFactor(600851475143), 6857);
```

# --seed--

## --seed-contents--

```js
function largestPrimeFactor(number) {

  return true;
}

largestPrimeFactor(13195);
```

# --solutions--

```js
const largestPrimeFactor = (number) => {
  let largestFactor = number;

  for (let i = 2; i <= Math.sqrt(largestFactor); i++) {
    if (!(largestFactor % i)) {
      let factor = largestFactor / i;
      let candidate = largestPrimeFactor(factor);

      return i > candidate ? i : candidate;
    }
  }

  return largestFactor;
}
```
