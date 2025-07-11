---
id: 5900f4cf1000cf542c50ffe1
title: '問題 354: 蜂の巣の中における距離'
challengeType: 1
forumTopicId: 302014
dashedName: problem-354-distances-in-a-bees-honeycomb
---

# --description--

それぞれの部屋が辺長１の完全な正六角形であるような蜂の巣について考えます。

<img alt="辺長 1 の六角形の部屋がある蜂の巣" src="https://cdn.freecodecamp.org/curriculum/project-euler/distances-in-a-bees-honeycomb.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

ある特定の部屋は女王蜂が占有しています。 For a positive real number $L$, let $B(L)$ count the cells with distance $L$ from the queen bee cell (all distances are measured from center to center); you may assume that the honeycomb is large enough to accommodate for any distance we wish to consider.

例: $B(\sqrt{3}) = 6$, $B(\sqrt{21}) = 12$, $B(111\\,111\\,111) = 54$

$B(L) = 450$ となるような $L ≤ 5 \times {10}^{11}$ の数を求めなさい。

# --hints--

`distancesInHoneycomb()` は `58065134` を返す必要があります。

```js
assert.strictEqual(distancesInHoneycomb(), 58065134);
```

# --seed--

## --seed-contents--

```js
function distancesInHoneycomb() {

  return true;
}

distancesInHoneycomb();
```

# --solutions--

```js
// solution required
```
