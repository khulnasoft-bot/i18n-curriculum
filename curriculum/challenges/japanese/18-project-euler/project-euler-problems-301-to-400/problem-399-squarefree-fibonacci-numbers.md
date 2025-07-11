---
id: 5900f4fc1000cf542c51000e
title: '問題 399: 無平方フィボナッチ数'
challengeType: 1
forumTopicId: 302064
dashedName: problem-399-squarefree-fibonacci-numbers
---

# --description--

以下は最初の 15 個のフィボナッチ数です。

$$1,1,2,3,5,8,13,21,34,55,89,144,233,377,610$$

8 は 4 で割り切れ、144 は 4 と 9 で割り切れるので、8 と 144 は無平方ではないことがわかります。

したがって、最初の 13 個の無平方フィボナッチ数は次のようになります。

$$1,1,2,3,5,13,21,34,55,89,233,377, 610$$

下に示す数は $200$ 番目の無平方フィボナッチ数です。971183874599339129547649988289594072811608739584170445 この数の下位 16 桁は 1608739584170445 であり、科学的記数法ではこれを `9.7e53` と表すことができます。

$100\\,000\\,000$ 番目の無平方フィボナッチ数を求めなさい。 回答は、下位 16 桁の後にカンマが続き、その後にその数を科学的記数法で表したもの (小数第 1 位に四捨五入) が続く文字列にすること。 $200$ 番目の無平方フィボナッチの場合、回答は `1608739584170445,9.7e53` という形になります。

** 注: ** この問題では、すべての素数 $p$ について、$p$ で割り切れる最初のフィボナッチ数は $p^2$ では割り切れないものと仮定します (これは、ウォール予想の一部です)。 この仮定は、素数 $≤ 3 \times {10}^{15}$ に対して確認されていますが、一般的には証明されていません。

上述の予想が誤りである場合、この問題の想定回答は $100\\,000\\,000$ 番目の無平方フィボナッチ数であると保証されず、正しくは、そのような数の下界のみを表すものとなります。

# --hints--

`squarefreeFibonacciNumbers()` は文字列を返す必要があります。

```js
asset.isString(squarefreeFibonacciNumbers());
```

`squarefreeFibonacciNumbers()` は文字列 `1508395636674243,6.5e27330467` を返す必要があります。

```js
assert.strictEqual(squarefreeFibonacciNumbers(), '1508395636674243,6.5e27330467');
```

# --seed--

## --seed-contents--

```js
function squarefreeFibonacciNumbers() {

  return true;
}

squarefreeFibonacciNumbers();
```

# --solutions--

```js
// solution required
```
