---
id: 5900f36e1000cf542c50fe80
title: 'Problem 1: Multiplikatoren von 3 oder 5'
challengeType: 1
forumTopicId: 301722
dashedName: problem-1-multiples-of-3-or-5
---

# --description--

Wenn wir alle natürlichen Zahlen unter 10 auflisten, die Multiplikatoren von 3 oder 5 sind, erhalten wir 3, 5, 6 und 9. Die Summe dieser Zahlen ist 23.

Finde die Summe aller Multiplikatoren von 3 oder 5 unter dem angegebenen Parameterwert `number`.

# --hints--

`multiplesOf3Or5(10)` sollte eine Zahl zurückgeben.

```js
assert.isNumber(multiplesOf3Or5(10));
```

`multiplesOf3Or5(49)` sollte 543 zurückgeben.

```js
assert.strictEqual(multiplesOf3Or5(49), 543);
```

`multiplesOf3Or5(1000)` sollte 233168 zurückgeben.

```js
assert.strictEqual(multiplesOf3Or5(1000), 233168);
```

`multiplesOf3Or5(8456)` sollte 16687353 zurückgeben.

```js
assert.strictEqual(multiplesOf3Or5(8456), 16687353);
```

`multiplesOf3Or5(19564)` sollte 89301183 zurückgeben.

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
