---
id: 5900f3ec1000cf542c50feff
title: '问题128：六边形瓷砖差异'
challengeType: 1
forumTopicId: 301755
dashedName: problem-128-hexagonal-tile-differences
---

# --description--

A hexagonal tile with number 1 is surrounded by a ring of six hexagonal tiles, starting at "12 o'clock" and numbering the tiles 2 to 7 in an anti-clockwise direction.

新环以相同的方式添加，下一个环编号为8至19,20至37,38至61，依此类推。 下图显示了前三个环。

<img alt="前三圈排列好的六角砖，数字编号为 1 到 37，其中砖 8 和砖 17高亮" src="https://cdn.freecodecamp.org/curriculum/project-euler/hexagonal-tile-differences.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

By finding the difference between tile $n$ and each of its six neighbors we shall define $PD(n)$ to be the number of those differences which are prime.

例如，围绕砖 8 顺时针方向的差额分别为 12、29、11、6、1 和 13。 则 $PD(8) = 3$。

同理，围绕砖 17 的差额为 1、17、16、1、11 和 10，所以 $PD(17) = 2$。

可以发现 $PD(n)$ 的最大值是 $3$。

如果 $PD(n) = 3$ 的砖按升序排列，那么第 10 块砖将会是 271。

求序列中的第 2000 块砖。

# --hints--

hexagonalTile(10) 应该返回 271

```js
assert.strictEqual(hexagonalTile(10), 271);
```

hexagonalTile(2000)  应该返回14516824220

```js
assert.strictEqual(hexagonalTile(2000), 14516824220);
```

# --seed--

## --seed-contents--

```js
function hexagonalTile(tileIndex) {

  return true;
}

hexagonalTile(10);
```

# --solutions--

```js
class PrimeSeive {
  constructor(num) {
    const seive = Array(Math.floor((num - 1) / 2)).fill(true);
    const upper = Math.floor((num - 1) / 2);
    const sqrtUpper = Math.floor((Math.sqrt(num) - 1) / 2);

    for (let i = 0; i <= sqrtUpper; i++) {
      if (seive[i]) {
        // Mark value in seive array
        const prime = 2 * i + 3;
        // Mark all multiples of this number as false (not prime)
        const primeSquaredIndex = 2 * i ** 2 + 6 * i + 3;
        for (let j = primeSquaredIndex; j < upper; j += prime) {
          seive[j] = false;
        }
      }
    }

    this._seive = seive;
  }

  isPrime(num) {
    return num === 2
      ? true
      : num % 2 === 0
        ? false
        : this.isOddPrime(num);
  }

  isOddPrime(num) {
    return this._seive[(num - 3) / 2];
  }
};

function hexagonalTile(tileIndex) {
  const primeSeive = new PrimeSeive(tileIndex * 420);
  let count = 1;
  let n = 1;
  let number = 0;

  while (count < tileIndex) {
    if (primeSeive.isPrime(6*n - 1) &&
        primeSeive.isPrime(6*n + 1) &&
        primeSeive.isPrime(12*n + 5)) {
      number = 3*n*n - 3*n + 2;
      count++;
      if (count >= tileIndex) break;
    }
    if (primeSeive.isPrime(6*n + 5) &&
        primeSeive.isPrime(6*n - 1) &&
        primeSeive.isPrime(12*n - 7) && n != 1) {
      number = 3*n*n + 3*n + 1;
      count++;
    }
    n++;
  }
  return number;
}
```
