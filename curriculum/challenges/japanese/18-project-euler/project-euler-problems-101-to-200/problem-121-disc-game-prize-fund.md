---
id: 5900f3e51000cf542c50fef8
title: '問題 121: 円盤ゲームの賞金額'
challengeType: 1
forumTopicId: 301748
dashedName: problem-121-disc-game-prize-fund
---

# --description--

袋の中に、赤い円盤 1 枚と青い円盤 1 枚が入っています。 In a game of chance a player takes a disc at random and its color is noted. ターンごとに円盤が袋に戻され、赤い円盤が 1 枚追加され、またプレイヤーが無作為に円盤を 1 枚取ります。

プレイヤーは 1 ポンド払ってゲームに参加し、ゲーム終了時に赤い円盤よりも青い円盤を多く取っていたら勝ちです。

このゲームが 4 ターン行われた場合、プレイヤーの勝率はちょうど 11/120 なので、胴元が確率的に損失を出さないようにこのゲームの勝利に割り当てるべき賞金額は、最大 10 ポンドです。 なお、支払いは 1 ポンド単位であり、ゲームをプレイするために支払った最初の 1 ポンドも含まれています。したがってこの例では、プレイヤーが実際に得る利益は 9 ポンドになります。

15 ターンが行われる 1 回のゲームに割り当てるべき最大賞金額を求めなさい。

# --hints--

`discGamePrize()` は `2269` を返す必要があります。

```js
assert.strictEqual(discGamePrize(), 2269);
```

# --seed--

## --seed-contents--

```js
function discGamePrize() {

  return true;
}

discGamePrize();
```

# --solutions--

```js
// solution required
```
