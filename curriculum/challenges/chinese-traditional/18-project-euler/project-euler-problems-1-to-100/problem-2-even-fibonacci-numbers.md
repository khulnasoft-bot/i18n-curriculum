---
id: 5900f36e1000cf542c50fe81
title: '問題2：斐波那契數列中的偶數'
challengeType: 1
forumTopicId: 301838
dashedName: problem-2-even-fibonacci-numbers
---

# --description--

在斐波那契數列中，每一項都是前兩項的和（第一項和第二項除外）。 從 1 和 2 開始，前 10 項將是：

<div style='text-align: center;'>1, 2, 3, 5, 8, 13, 21, 34, 55, 89, ...</div>

求出斐波那契數列中值是偶數的項的和，至第`n`項（包括第`n`項）爲止。

# --hints--

`fiboEvenSum(10)` 應該返回數字類型的數據。

```js
assert.isNumber(fiboEvenSum(10));
```

你的函數應該返回一個偶數。

```js
assert.equal(fiboEvenSum(10) % 2 === 0, true);
```

您的函數應該把偶數值的 Fibonacci 數字相加： `fiboEvenSum(8)` 應該返回 10。

```js
assert.strictEqual(fiboEvenSum(8), 10);
```

`fiboEvenSum(10)` 應該返回 10。

```js
assert.strictEqual(fiboEvenSum(10), 10);
```

`fiboEvenSum(34)` 應該返回 44。

```js
assert.strictEqual(fiboEvenSum(34), 44);
```

`fiboEvenSum(60)` 應該返回 44。

```js
assert.strictEqual(fiboEvenSum(60), 44);
```

`fiboEvenSum(1000)` 應該返回 798。

```js
assert.strictEqual(fiboEvenSum(1000), 798);
```

`fiboEvenSum(100000)` 應該返回 60696。

```js
assert.strictEqual(fiboEvenSum(100000), 60696);
```

`fiboEvenSum(4000000)` 應該返回 4613732。

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
