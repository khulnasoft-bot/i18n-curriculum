---
id: 5900f3781000cf542c50fe8b
title: '問題12：高度可整除的三角數'
challengeType: 1
forumTopicId: 301746
dashedName: problem-12-highly-divisible-triangular-number
---

# --description--

三角形數序列是由自然數相加而成的。 所以第七個三角形的數字是1 + 2 + 3 + 4 + 5 + 6 + 7 = 28。 序列的前十項是：

<div style='text-align: center;'>1, 3, 6, 10, 15, 21, 28, 36, 45, 55, ...</div>

讓我們列出前七個三角形數字的因數：

<div style='padding-left: 4em;'><b>1:</b> 1</div>
<div style='padding-left: 4em;'><b>3:</b> 1, 3</div>
<div style='padding-left: 4em;'><b>6:</b> 1, 2, 3, 6</div>
<div style='padding-left: 4em;'><b>10:</b> 1, 2, 5, 10</div>
<div style='padding-left: 4em;'><b>15:</b> 1, 3, 5, 15</div>
<div style='padding-left: 4em;'><b>21:</b> 1, 3, 7, 21</div>
<div style='padding-left: 4em;'><b>28:</b> 1, 2, 4, 7, 14, 28</div>

我們可以看到28是第一個有超過5個因數的三角形數。

第一個超過 `n` 除數的三角形數字是多少？

# --hints--

`divisibleTriangleNumber(5)` 應該返回一個數字。

```js
assert.isNumber(divisibleTriangleNumber(5));
```

`divisibleTriangleNumber(5)`應該返回28。

```js
assert.strictEqual(divisibleTriangleNumber(5), 28);
```

`divisibleTriangleNumber(23)`應該返回630。

```js
assert.strictEqual(divisibleTriangleNumber(23), 630);
```

`divisibleTriangleNumber(167)`應該返回1385280。

```js
assert.strictEqual(divisibleTriangleNumber(167), 1385280);
```

`divisibleTriangleNumber(374)`應該返回17907120。

```js
assert.strictEqual(divisibleTriangleNumber(374), 17907120);
```

`divisibleTriangleNumber(500)`應該返回76576500。

```js
assert.strictEqual(divisibleTriangleNumber(500), 76576500);
```

# --seed--

## --seed-contents--

```js
function divisibleTriangleNumber(n) {

  return true;
}

divisibleTriangleNumber(500);
```

# --solutions--

```js
function divisibleTriangleNumber(n) {
  if (n === 1) return 3;
  let counter = 1;
  let triangleNumber = counter++;


 while (noOfFactors(triangleNumber) < n) {
   triangleNumber += counter++;
 }
return triangleNumber;
}

function noOfFactors(num) {
  const primeFactors = getPrimeFactors(num);
  let prod = 1;
  for(let p in primeFactors) {
    prod *= (primeFactors[p] + 1)
  }
  return prod;
}

function getPrimeFactors(num) {
  let n = num;
  let primes = {};

  let p = 2;
  let sqrt = Math.sqrt(num);

  function checkAndUpdate(inc) {
    if (n % p === 0) {
      const curr = primes[p];
      if (curr) {
        primes[p]++
      } else {
        primes[p] = 1;
      }
      n /= p;
    } else {
      p += inc;
    }
  }

  while(p === 2 && p <= n) {
    checkAndUpdate(1);
  }

  while (p <= n && p <= sqrt) {
    checkAndUpdate(2);
  }
  if(Object.keys(primes).length === 0) {
    primes[num] = 1;
  } else if(n !== 1) {
    primes[n] = 1;
  }
  return primes;
}
```
