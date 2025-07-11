---
id: 5900f51b1000cf542c51002e
title: '問題 431: 空間が平方数であるサイロ'
challengeType: 1
forumTopicId: 302102
dashedName: problem-431-square-space-silo
---

# --description--

農場主のフレッドは、農場にサイロを新設するための手配をしました。彼は四角い物への執着が強く、丸い物を見つけるとひどく落ち込みます。 サイロを新設した会社の代表者クエンティンは、円柱状のサイロしか製造していないと説明しましたが、ただしサイロは四角い土台の上に載っていると指摘しました。 それでもフレッドは不快感を抱き、サイロを農場から撤去するよう求めました。

クエンティンは機転を利かせて次のことを説明しました。サイロの上から粒状のものが投入されるとき、円錐状の斜面ができ、その際に斜面と水平な線によって自然にできる角度は安息角と呼ばれます。 For example if the angle of repose, $\alpha = 30°$, and grain is delivered at the center of the silo then a perfect cone will form towards the top of the cylinder. 直径 6 m のこのサイロの場合、無駄になる空間の体積は約 32.648388556 m<sup>3</sup> です。 However, if grain is delivered at a point on the top which has a horizontal distance of $x$ metres from the center then a cone with a strangely curved and sloping base is formed. クエンティンはフレッドに図を見せました。

<img alt="円柱の最上部に向けて完全な円錐が作られることを示す図" src="https://cdn.freecodecamp.org/curriculum/project-euler/square-space-silo.png" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

無駄になる空間の体積 (単位: 立方メートル) を $V(x)$ で表します。 $x = 1.114\\,785\\,284$ の場合 (偶然にも、小数点以下の桁数が 3 の 平方数すなわち 9)、無駄になる空間の体積は $V(1.114\\,785\\,284) \approx 36$ となります。 この問題に対して考えられる解の範囲内に、他の選択肢がちょうど 1 つあります。それは、$V(2.511\\,167\\,869) \approx 49$ です。 これで、(平方数と四角形の両方を意味する) "square" がサイロの主になり、輝く栄誉の中で穀物の山の頂に座しているかのようになります。

この的確な解決法にフレッドの表情が喜びで輝きました。しかしクエンティンの図と計算を詳しく調べてみると、喜びが再び落胆に変わりました。 フレッドは、 6 m はサイロの直径ではなく半径であり、さらに穀物の安息角は 40 度であるとクエンティンに指摘しました。 しかし、クエンティンが今回のサイロに対する解決策一式を見つけられれば、フレッドは喜んでサイロをこのまま保有するはずです。

機転の利くクエンティンが、苛立たしいほど気難しい農場主フレッドの四角い物への欲求を満たそうとする場合について、無駄な空間が平方数となるすべての可能な選択肢に対する $x$ の値を決定し、$\sum x$ を小数第 9 位まで求めなさい。

# --hints--

`squareSpaceSilo()` は `23.386029052` を返す必要があります。

```js
assert.strictEqual(squareSpaceSilo(), 23.386029052);
```

# --seed--

## --seed-contents--

```js
function squareSpaceSilo() {

  return true;
}

squareSpaceSilo();
```

# --solutions--

```js
// solution required
```
