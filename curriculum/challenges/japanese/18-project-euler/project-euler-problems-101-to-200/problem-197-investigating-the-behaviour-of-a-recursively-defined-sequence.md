---
id: 5900f4311000cf542c50ff44
title: 'Problem 197: Investigating the behavior of a recursively defined sequence'
challengeType: 1
forumTopicId: 301835
dashedName: problem-197-investigating-the-behaviour-of-a-recursively-defined-sequence
---

# --description--

関数 $f(x) = ⌊{2}^{30.403243784 - x^2}⌋ × {10}^{-9}$ ( ⌊ ⌋ は床関数) が与えられ、数列 $u_n$ は $u_0 = -1$ と $u_{n + 1} = f(u_n)$ で定義されます。

$n = {10}^{12}$ のとき、$u_n + u_{n + 1}$ を求めなさい。 回答は、四捨五入して小数第 9 位まで示すこと。

# --hints--

`recursivelyDefinedSequence()` は `1.710637717` を返す必要があります。

```js
assert.strictEqual(recursivelyDefinedSequence(), 1.710637717);
```

# --seed--

## --seed-contents--

```js
function recursivelyDefinedSequence() {

  return true;
}

recursivelyDefinedSequence();
```

# --solutions--

```js
// solution required
```
