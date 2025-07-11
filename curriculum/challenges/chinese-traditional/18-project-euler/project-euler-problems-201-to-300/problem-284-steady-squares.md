---
id: 5900f4891000cf542c50ff9b
title: '問題284：平穩正方形'
challengeType: 1
forumTopicId: 301935
dashedName: problem-284-steady-squares
---

# --description--

The 3-digit number 376 in the decimal numbering system is an example of numbers with the special property that its square ends with the same digits: ${376}^2 = 141376$. Let's call a number with this property a steady square.

在其他編號系統中也可以看到穩定的正方形。 In the base 14 numbering system, the 3-digit number $c37$ is also a steady square: $c37^2 = aa0c37$, and the sum of its digits is $c+3+7=18$ in the same numbering system. The letters $a$, $b$, $c$ and $d$ are used for the 10, 11, 12 and 13 digits respectively, in a manner similar to the hexadecimal numbering system.

For $1 ≤ n ≤ 9$, the sum of the digits of all the $n$-digit steady squares in the base 14 numbering system is $2d8$ (582 decimal). 不允許以 0 開頭的穩定正方形。

Find the sum of the digits of all the $n$-digit steady squares in the base 14 numbering system for $1 ≤ n ≤ 10000$ (decimal) and give your answer as a string in the base 14 system using lower case letters where necessary.

# --hints--

`steadySquares()` should return a string.

```js
assert.isString(steadySquares());
```

`steadySquares()` should return the string `5a411d7b`.

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
