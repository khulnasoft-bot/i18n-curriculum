---
id: 5900f37f1000cf542c50fe92
title: '問題19：計算星期日'
challengeType: 1
forumTopicId: 301827
dashedName: problem-19-counting-sundays
---

# --description--

You are given the following information, but you may prefer to do some research for yourself.

<ul>
  <li>1 Jan 1900 was a Monday.</li>
  <li>Thirty days has September,<br>April, June and November.<br>All the rest have thirty-one,<br>Saving February alone,<br>Which has twenty-eight, rain or shine.<br>And on leap years, twenty-nine.</li>
  <li>閏年發生在任何一年，可被4整除，但除非可被400整除，否則不會在一個世紀上。</li>
</ul>

How many Sundays fell on the first of the month during the twentieth century (1 Jan 1901 to 31 Dec 2000)?

# --hints--

`countingSundays(1943, 1946)` should return a number.

```js
assert.isNumber(countingSundays(1943, 1946));
```

`countingSundays(1943, 1946)` should return 6.

```js
assert.strictEqual(countingSundays(1943, 1946), 6);
```

`countingSundays(1995, 2000)` should return 10.

```js
assert.strictEqual(countingSundays(1995, 2000), 10);
```

`countingSundays(1901, 2000)` should return 171.

```js
assert.strictEqual(countingSundays(1901, 2000), 171);
```

# --seed--

## --seed-contents--

```js
function countingSundays(firstYear, lastYear) {

  return true;
}

countingSundays(1943, 1946);
```

# --solutions--

```js
function countingSundays(firstYear, lastYear) {
  let sundays = 0;

  for (let year = firstYear; year <= lastYear; year++) {
    for (let month = 0; month <= 11; month++) {
      const thisDate = new Date(year, month, 1);
      if (thisDate.getDay() === 0) {
        sundays++;
      }
    }
  }
  return sundays;
}
```
