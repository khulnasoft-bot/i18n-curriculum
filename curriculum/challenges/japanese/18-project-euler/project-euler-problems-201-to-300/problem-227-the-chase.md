---
id: 5900f44f1000cf542c50ff61
title: '問題 227: チェイス'
challengeType: 1
forumTopicId: 301870
dashedName: problem-227-the-chase
---

# --description--

「チェイス」とは、2 つのサイコロと偶数人のプレイヤーで遊ぶゲームです。

プレイヤーはテーブルの周りに座ります。ゲームの開始時、互いに対面に座っている 2 人がサイコロを 1 つずつ持っています。 それぞれのターンで、サイコロを持っている 2 人がそれを振ります。

If the player rolls a 1, he passes the die to his neighbor on the left.

If the player rolls a 6, he passes the die to his neighbor on the right.

それ以外の場合、次のターンまでサイコロをそのまま持っています。

サイコロが振られてプレイヤー間を移動するうちに 1 人のプレイヤーがサイコロを 2 つとも持ったら、そのプレイヤーは負け、ゲームは終わります。

100 人のプレイヤーでこのゲームをすると何回目のターンまで続くかについて、その期待値を求めなさい。 回答は、四捨五入して有効数字 10 桁にすること。

# --hints--

`theChase()` は `3780.618622` を返す必要があります。

```js
assert.strictEqual(theChase(), 3780.618622);
```

# --seed--

## --seed-contents--

```js
function theChase() {

  return true;
}

theChase();
```

# --solutions--

```js
// solution required
```
