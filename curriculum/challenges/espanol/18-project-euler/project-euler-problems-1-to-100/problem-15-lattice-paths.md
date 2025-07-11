---
id: 5900f37b1000cf542c50fe8e
title: 'Problema 15: Trayectorias en una cuadrícula'
challengeType: 1
forumTopicId: 301780
dashedName: problem-15-lattice-paths
---

# --description--

Comenzando en la esquina superior izquierda de una cuadrícula 2x2, y estando permitido solo moverse hacia la izquierda y hacia abajo, hay exactamente 6 trayectorias para alcanzar la esquina inferior derecha.

<img alt="a diagram of 6 2 by 2 grids showing all the routes to the bottom right corner" src="https://cdn-media-1.freecodecamp.org/project-euler/1Atixoj.gif" style="background-color: white; padding: 10px; display: block; margin-right: auto; margin-left: auto; margin-bottom: 1.2rem;" />

¿Cuántas trayectorias de este tipo hay en una cuadrícula de `gridSize` (tamaño) dado?

# --hints--

`latticePaths(4)` debe devolver un número.

```js
assert.isNumber(latticePaths(4));
```

`latticePaths(4)` debe devolver 70.

```js
assert.strictEqual(latticePaths(4), 70);
```

`latticePaths(9)` debe devolver 48620.

```js
assert.strictEqual(latticePaths(9), 48620);
```

`latticePaths(20)` debe devolver 137846528820.

```js
assert.strictEqual(latticePaths(20), 137846528820);
```

# --seed--

## --seed-contents--

```js
function latticePaths(gridSize) {

  return true;
}

latticePaths(4);
```

# --solutions--

```js
function latticePaths(gridSize) {
  let paths = 1;

  for (let i = 0; i < gridSize; i++) {
    paths *= (2 * gridSize) - i;
    paths /= i + 1;
  }
  return paths;
}
```
