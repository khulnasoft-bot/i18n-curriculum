---
id: 5900f3711000cf542c50fe84
title: '问题5：最小公倍数'
challengeType: 1
forumTopicId: 302160
dashedName: problem-5-smallest-multiple
---

# --description--

2520是可以除以1到10中的每个数字而没有任何余数的最小数字。

能被从 1 到 `n` 的所有数整除的最小正整数是多少？

# --hints--

`smallestMult(5)` 应该返回数字

```js
assert.isNumber(smallestMult(5));
```

`smallestMult(5)` 应该返回 60。

```js
assert.strictEqual(smallestMult(5), 60);
```

`smallestMult(7)` 应该返回 420。

```js
assert.strictEqual(smallestMult(7), 420);
```

`smallestMult(10)` 应返回 2520。

```js
assert.strictEqual(smallestMult(10), 2520);
```

`smallestMult(13)` 应返回 360360。

```js
assert.strictEqual(smallestMult(13), 360360);
```

`smallestMult(20)` 应该返回 232792560。

```js
assert.strictEqual(smallestMult(20), 232792560);
```

# --seed--

## --seed-contents--

```js
function smallestMult(n) {

  return true;
}

smallestMult(20);
```

# --solutions--

```js
function smallestMult(n){
  function gcd(a, b) {
    return b === 0 ? a : gcd(b, a%b); // Euclidean algorithm
  }

  function lcm(a, b) {
    return a * b / gcd(a, b);
  }
  var result = 1;
  for(var i = 2; i <= n; i++) {
    result = lcm(result, i);
  }
  return result;
}
```
