---
id: 5900f4ca1000cf542c50ffdc
title: '问题349：兰顿的蚂蚁'
challengeType: 1
forumTopicId: 302008
dashedName: problem-349-langtons-ant
---

# --description--

An ant moves on a regular grid of squares that are colored either black or white.

从一个完全是白色的网格开始，在蚂蚁1018次移动后，有多少个方块是黑色的？

- if it is on a black square, it flips the color of the square to white, rotates 90° counterclockwise and moves forward one square.
- if it is on a white square, it flips the color of the square to black, rotates 90° clockwise and moves forward one square.

Starting with a grid that is entirely white, how many squares are black after ${10}^{18}$ moves of the ant?

# --hints--

`langtonsAnt()` should return `115384615384614940`.

```js
assert.strictEqual(langtonsAnt(), 115384615384614940);
```

# --seed--

## --seed-contents--

```js
function langtonsAnt() {

  return true;
}

langtonsAnt();
```

# --solutions--

```js
// solution required
```
