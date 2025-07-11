---
id: 5900f36e1000cf542c50fe81
title: 'Problem 2: Gerade Fibonacci-Zahlen'
challengeType: 1
forumTopicId: 301838
dashedName: problem-2-even-fibonacci-numbers
---

# --description--

Jeder neue Term in der Fibonacci-Folge wird durch Addition der beiden vorherigen Terme erzeugt. Wenn man mit 1 und 2 beginnt, lauten die ersten 10 Terme:

<div style='text-align: center;'>1, 2, 3, 5, 8, 13, 21, 34, 55, 89, ...</div>

Bei der Betrachtung der Begriffe der Fibonacci-Folge, deren Werte `n` nicht überschreiten, ist die Summe der geradzahligen Begriffe zu ermitteln.

# --hints--

`fiboEvenSum(10)` sollte eine Zahl zurückgeben.

```js
assert.isNumber(fiboEvenSum(10));
```

Deine Funktion sollte einen geraden Wert zurückgeben.

```js
assert.equal(fiboEvenSum(10) % 2 === 0, true);
```

Deine Funktion sollte die geradzahligen Fibonacci-Zahlen summieren: `fiboEvenSum(8)` sollte 10 zurückgeben.

```js
assert.strictEqual(fiboEvenSum(8), 10);
```

`fiboEvenSum(10)` sollte 10 zurückgeben.

```js
assert.strictEqual(fiboEvenSum(10), 10);
```

`fiboEvenSum(34)` sollte 44 zurückgeben.

```js
assert.strictEqual(fiboEvenSum(34), 44);
```

`fiboEvenSum(60)` sollte 44 zurückgeben.

```js
assert.strictEqual(fiboEvenSum(60), 44);
```

`fiboEvenSum(1000)` sollte 798 zurückgeben.

```js
assert.strictEqual(fiboEvenSum(1000), 798);
```

`fiboEvenSum(100000)` sollte 60696 zurückgeben.

```js
assert.strictEqual(fiboEvenSum(100000), 60696);
```

`fiboEvenSum(4000000)` sollte 4613732 zurückgeben.

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
