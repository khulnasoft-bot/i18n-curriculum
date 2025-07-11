---
id: 5900f4511000cf542c50ff62
title: '問題 226: 一すくいのブラマンジェ'
challengeType: 1
forumTopicId: 301869
dashedName: problem-226-a-scoop-of-blancmange
---

# --description--

ブラマンジェ曲線は、0 ≤ x ≤ 1 かつ $\displaystyle y = \sum_{n = 0}^{\infty} \frac{s(2^nx)}{2^n}$ であるような点 ($x$,$y$) の集合です。ここで、$s(x) は $x$ から最も近い整数への距離を表します。

ブラマンジェ曲線より下の部分 (下図のピンク色の部分) の面積は $\frac{1}{2}$ に等しくなります。

<img alt="円 C が示されたブラマンジェ曲線の図" src="https://cdn.freecodecamp.org/curriculum/project-euler/a-scoop-of-blancmange.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

Let $C$ be the circle with center ($\frac{1}{4}$,$\frac{1}{2}$) and radius $\frac{1}{4}$, shown in black in the diagram.

$C$ に囲まれ、かつブラマンジェ曲線より下の部分の面積を求めなさい。 回答は、四捨五入して小数第 8 位まで求め、0.abcdefgh の形式にすること。

# --hints--

`scoopOfBlancmange()` は `0.11316017` を返す必要があります。

```js
assert.strictEqual(scoopOfBlancmange(), 0.11316017);
```

# --seed--

## --seed-contents--

```js
function scoopOfBlancmange() {

  return true;
}

scoopOfBlancmange();
```

# --solutions--

```js
// solution required
```
