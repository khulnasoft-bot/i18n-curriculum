---
id: 5900f42f1000cf542c50ff40
title: 'Problem 194: Colored Configurations'
challengeType: 1
forumTopicId: 301832
dashedName: problem-194-coloured-configurations
---

# --description--

ユニット A: <img alt="graph unit A" src="https://cdn.freecodecamp.org/curriculum/project-euler/coloured-configurations-1.png" style="display: inline-block; background-color: white; padding: 10px;" /> と B: <img  alt="graph unit B" src="https://cdn.freecodecamp.org/curriculum/project-euler/coloured-configurations-2.png" style="display: inline-block; background-color: white; padding: 10px;" /> からなる図形を考えます。このユニットを次の図のように、垂直方向の辺に沿って接着します。<img alt="graph with four units glued along the vertical edges" src="https://cdn.freecodecamp.org/curriculum/project-euler/coloured-configurations-3.png" style="display: inline-block; background-color: white; padding: 10px;" />

A configuration of type $(a,b,c)$ is a graph thus built of $a$ units A and $b$ units B, where the graph's vertices are colored using up to $c$ colors, so that no two adjacent vertices have the same color. 上図の連結ユニットは (2,2,6) 型の構成の例です。実は、これはすべての $c ≥ 4 に対する (2,2,c) 型の構成です。

$(a,b,c)$ 型の構成の数を $N(a,b,c)$ とします。 例えば、$N(1,0,3) = 24$, $N(0,2,4) = 92928$, $N(2,2,3) = 20736$ です。

$N(25,75,1984)$ の下位 8 桁を求めなさい。

# --hints--

`coloredConfigurations()` は `61190912` を返す必要があります。

```js
assert.strictEqual(coloredConfigurations(), 61190912);
```

# --seed--

## --seed-contents--

```js
function coloredConfigurations() {

  return true;
}

coloredConfigurations();
```

# --solutions--

```js
// solution required
```
